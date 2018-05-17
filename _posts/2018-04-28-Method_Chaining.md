---
layout: post
title: Method Chaining
description: Method Chaining ( Java & Kotlin )
category: Java&Kotlin
tags: [Java, Kotlin, 이론]
---


Code
``` java
        Chaining_java Chaining1 = new Chaining_java();
        Chaining1.Title("제목 1");
        Chaining1.Message("메세지 1");
        Chaining1.Tag("태그 1");
        Chaining1.Print();

        Chaining_java Chaining2 = new Chaining_java();
        Chaining2
          .Title("제목 2")
          .Message("메세지 2")
          .Tag("태그 2")
          .Print();
```
결과
```
====================================
제목 : 제목 1
====================================
메세지 : 메세지 1
====================================
태그 : 태그 1
====================================
제목 : 제목 2
===================================
메세지 : 메세지 2
====================================
태그 : 태그 2
```

위의 내용처럼 `Chaining1` 처럼 메소드 한번 사용할때마다 끊어 사용하는것을 대부분이 사용하는 방식입다.

사용해야할 메소드가 많다면 더욱 많은 내용을 사용해야 합니다.

하지만 `Chaining2`를 사용하면 결과는 같지만 코드는 좀더 간결하다는 장점이 있습니다.


```java

public class Chaining_java {
    String Text = "";

    public Chaining_java Title(String title){
        Text += "====================================\n";
        Text += String.format("제목 : %s\n",title);
        return this;
    }

    public Chaining_java Message(String Message){
        Text += "===================================\n";
        Text += String.format("제목 : %s\n",Message);
        return this;
    }

    public Chaining_java Tag(String Tag){
        Text += "====================================\n";
        Text += String.format("제목 : %s\n",Tag);
        return this;
    }
    public void Print(){
        System.out.println(Text);
    }
}
```

위 내용을 확인해보시면 `return this` 를 하게 되면 결과와 같은 값을 얻을수 있습니다.

메소드 안에 있는 내용을 실행하고 나서 자기 자신을 반환을 하게 되기 때문에 다시 메소드를 사용할수 있게 됩니다.

위 내용은 자바로 코드를 작성하였지만 코틀린이라면
```java
class Chaining_Kotlin {
    var Text : String = ""

    fun Title (Title : String ): Chaining_Kotlin = apply {
        Text += """
            |====================================
            |제목 : $Title"""}

    fun Message (Message : String ): Chaining_Kotlin = apply {
        Text += """
            |====================================
            |메세지 : $Message"""}

    fun Tag (Tag : String ): Chaining_Kotlin = apply {
        Text += """
            |====================================
            |태그 : $Tag """}

    fun Print(){
        println(Text.trimMargin())
    }
}
```

비슷하지만 조금더 간결한 코드로 동일한 동작을 하게 됩니다.
