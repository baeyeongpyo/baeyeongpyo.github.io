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
    android:layout_height="match_parent"
    tools:context=".Main2Activity">

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
```
