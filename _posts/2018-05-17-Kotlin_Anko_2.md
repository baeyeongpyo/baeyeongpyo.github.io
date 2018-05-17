---
layout: post
title: Kotlin Anko로 개발하기 (2)
description: Kotlin의 Anko Library Commons
category: android
tags: [Kotlin, 이론]
---

## Anko Commons 사용하기

Anko Commons는
Dialog와 Toast 등의 유틸 클래스의 모음집입니다. Toast Message를 띄우거나 Dialog창을 사용할때 간단하게 작성할수 있도록 도움을 줍니다.

우선 코드를 비교하면

`Toast.makeText(this, "Basic Toast Message", Toast.LENGTH_SHORT).show()`
위와 같은 코드가 기존에 사용했던 방식이라면

### Anko라면?

`toast("Anko Toast Message")` 처럼 코드를 작성하면 아주 간단하게 사용할수 있습니다.

그 외에 코드도 비교를 해보겠습니다.

```
        val intent = Intent(this, Main2Activity::class.java).apply {
            putExtra("Data1" , "1")
            putExtra("Data2" , "1")
            putExtra("Data3" , "1")
            addFlags(Intent.FLAG_ACTIVITY_NEW_TASK)
        }
        startActivity(intent)
```
위 코드는 Kotlin 으로 작성된 코드입니다.
간단하게 Data를 넘겨주고 플래그 까지 추가한 Intent 입니다.

### Anko라면?

우선 순차적으로 새로운 Activity로 전환만 한다면
`startActivity<Main2Activity>()` 만으로도 끝납니다.

하지만 데이터를 추가한다면?
```
startActivity<Main2Activity>(
                "Data1" to "1",
                "Data2" to "2",
                "Data3" to "3")
```
위와 같은 Code 를 작성할수 있고 Flag를 사용해야 한다면?

```
        startActivity(intentFor<Main2Activity>(
                "Data1" to "1",
                "Data2" to "2",
                "Data3" to "3").newTask())
```

위와 같이 intentFor를 추가를 해야합니다.

확실히 기존의 방식과 비교를 하면 간단하게 사용이 가능합니다.

다른 Intent 중에 전화 기능은

`startActivity(Intent(Intent.ACTION_CALL, Uri.parse("tel:000-0000-0000")))`
  ->  `makeCall("tel:000-000-0000")`
이렇게 바뀌게 됩니다.

Anko Commons 에는 Logger의 기능도 있습니다.

클래스에 AnkoLogger를 implements 를 해주게 되면
현재 클래스 명이 Log Tag로 등록이 됩니다.

Tag명을 바꾸고 싶다면
`val ?? =  AnkoLogger(" ~~~ ")`를 사용하시면 됩니다.

AnkoLogger를 implements 를 하셨다면
사용해야하는 부분에서 `info("~~~~")`를 하게 되면 LogCat에 원하는 결과값을 보실수 있습니다.

Tag를 원하는 값으로 설정하신경우에는 `??.info(" ~~~~ ") `하면 됩니다.

Logger의 종류는 기존 Log와 동일하게 6가지를 사용합니다.

 * verbose()
 * debug()
 * info()
 * warn()
 * error()
 * wtf()
