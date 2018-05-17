---
layout: post
title: Kotlin Anko로 개발하기 (3)
description: Kotlin의 Anko Library Layout
category: android
tags: [Kotlin, 이론]
---

## Anko Layout 사용하기

 XML을 Kotlin Code로 작성할수 있게 해주는 라이브러리입니다.
 실제로 Anko를 사용했을 경우와 안했을경우를 비교했었을때에 최대 600% 까지의 성능이 향상된것을 볼수 있습니다.
 간단한 뷰를 생성할때에는 체감상 느껴지지 않을수 있지만 뷰가 복잡해 질수록 성능의 향상을 체감할수 있게 될겁니다.

``` xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="TextView"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</android.support.constraint.ConstraintLayout>
```
위 Code는 XML Code 입니다.

### Anko라면?

``` kotlin
class AnkoActivity : AppCompatActivity() {
  override fun onCreate(savedInstanceState: Bundle?) {
      super.onCreate(savedInstanceState)
      val constraintlayoutID = R.id.ankoConstraintLayout
      constraintLayout{
          id = constraintlayoutID
          textView("Anko Hello").lparams(wrapContent, wrapContent){
              startToStart = constraintlayoutID
              endToEnd = constraintlayoutID
              topToTop = constraintlayoutID
              bottomToBottom = constraintlayoutID
          }
      }
  }
}
```
위 처럼 XML은 없어지고 Activity에서 작성이 가능합니다.

``` xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <item name="ankoConstraintLayout" type="id" />
</resources>
```
View ID는 values -> ids.xml 에서 위 처럼 설정해주면 됩니다.

하지만 Activity에 View를 그리는 것은 복잡하게(?) 보이므로 따로 클래스를 만들어서 빼주겠습니다.

``` kotlin
class AnkoActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(AnkoUIMaker(this).UiMake())
    }
}
```
위 Code는 Acitivity의 Code입니다.

``` kotlin
class AnkoUIMaker(val context: Context) {
    private val constraintlayoutID = R.id.ankoConstraintLayout
    fun UiMake(): View =
            context.constraintLayout {
                id = constraintlayoutID
                textView("Anko Hello").lparams(wrapContent, wrapContent) {
                    startToStart = constraintlayoutID
                    endToEnd = constraintlayoutID
                    topToTop = constraintlayoutID
                    bottomToBottom = constraintlayoutID
                }
            }
}
```
위 코드는 View를 생성하는 Class Code입니다.
XML을 대신해서 쓸수있는 Class 입니다.

이렇게 사용하게 되면 Kotlin Anko를 이용해서 View를 만들고 Java Code로 사용할수 있게 되었습니다.

``` java
public class AnkoActivity_java extends AppCompatActivity {
    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(new AnkoUIMaker(this).UiMake());
    }
}
```
위 Code는 java에서 작성된 Code입니다.
View는 Kotlin Anko에서 작성되었고 자바에서 받아서 사용했습니다.

Kotlin에서는 kotlin-android-extensions Plugin 을 사용하게 되면 findViewByid를 사용하지 않아도 되었습니다.

자바도 Anko를 사용하게 되면 FindViewByid를 사용하지 않아도 View를 사용할수 있습니다.

``` kotlin
class AnkoUIMaker(val context: Context) {
    private val constraintlayoutID = R.id.ankoConstraintLayout
    // 추가
    lateinit var textview : TextView
    fun UiMake(): View =
            context.constraintLayout {
                id = constraintlayoutID
                // 추가
                textview = textView("Anko Hello").lparams(wrapContent, wrapContent) {
                    startToStart = constraintlayoutID
                    endToEnd = constraintlayoutID
                    topToTop = constraintlayoutID
                    bottomToBottom = constraintlayoutID
                }
            }
}
```
위 Code는 UI를 생성하는 Class에서 `// 추가` 라는 주석의 아래 한줄을 추가 해주게 되면
``` java
public class AnkoActivity_java extends AppCompatActivity {
    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        AnkoUIMaker UImaker = new AnkoUIMaker(this);
        setContentView(UImaker.UiMake());
        UImaker.textview.setText( " Change Text " );
    }
}
```
TextView를 호출해서 사용이 가능합니다.
