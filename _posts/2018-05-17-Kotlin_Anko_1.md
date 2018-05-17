---
layout: post
title: Kotlin Anko로 개발하기 (1)
description: Kotlin의 Anko Library 소개
category: android
tags: [Kotlin, 이론]
---

## Anko란?

Kotlin으로 작성된 DSL ( Domain-specific-Language) 입니다.
기존에 Android에서는 View를 디자인 할때 XML Layout을 통해서 표현하였습니다.
Anko의 공식적으로 발표된 자료에는 Android 개발을 좀더 쉽고 빠르게 개발할수 있는 라이브러리라고 소개되어 있습니다.
기존의 XML 을 사용하게 되면 Java코드로 변환하는 작업을 하게 되면서 CPU나 배터리 소모를 하고 코드의 재활용이 불편하다는 단점이 있습니다.
Anko는 이한 단점을 라이브러리로 가독성은 높이고 XML 파싱에 따른 오버헤드를 없앨 수 있습니다.

### Anko 기능

공식 GitHub에는 크게 4가지로 나눠져있습니다.
 * Anko Commons
 * Anko Loayouts
 * Anko SQLite
 * Anko Coroutines


### Anko Commons

 Dialog와 Toast 등의 유틸 클래스의 모음집입니다.
 Toast Message를 띄우거나 Dialog창을 사용할때 간단하게 작성할수 있도록 도움을 줍니다.

### Anko Coroutines

 Kotlinx.corutines 라이브러리를 기본으로한 유틸리티입니다.

### Anko SQLite

 Android SQLite 용 쿼리 DSL 및 파서 컬렉션

### Anko Layouts

 XML을 Kotlin Code로 작성할수 있게 해주는 라이브러리입니다.
 실제로 Anko를 사용했을 경우와 안했을경우를 비교했었을때에 최대 600% 까지의 성능이 향상된것을 볼수 있습니다.
 간단한 뷰를 생성할때에는 체감상 느껴지지 않을수 있지만 뷰가 복잡해 질수록 성능의 향상을 체감할수 있게 될겁니다.


### Bulid 추가

 우선 Anko 를 사용하려면 `Gradle`추가 작업이 필요합니다.
 작성하는 시점( 2018 - 05 - 17 ) 에서는 `'0.10.5'`버전까지 사용할수 있습니다.

 ```
dependencies {
    implementation "org.jetbrains.anko:anko:$anko_version"
}
```
Anko의 모든 기능을 사용을 하려면 위와 같이 설정을 하면됩니다.

하지만 일부의 기능을 사용하기를 원한다면 원하는 부분만 사용 가능합니다.

```
// Anko Commons
dependencies {
    implementation "org.jetbrains.anko:anko-commons:$anko_version"
    }
```

```
// Anko Layout
dependencies {
    implementation "org.jetbrains.anko:anko-sdk25:$anko_version"
     // sdk15, sdk19, sdk21, sdk23 are also available
    implementation "org.jetbrains.anko:anko-appcompat-v7:$anko_version"
    }
```

```
//Anko Layout, Coroutine
dependencies {
    implementation "org.jetbrains.anko:anko-sdk25-coroutines:$anko_version"
    implementation "org.jetbrains.anko:anko-appcompat-v7-coroutines:$anko_version"
    }
```

```
// Anko SQLite
dependencies {
    implementation "org.jetbrains.anko:anko-sqlite:$anko_version"
    }
```

그 외에 추가적으로 사용가능한 라이브러리도 있습니니다.
```
dependencies {
    // Appcompat-v7 (only Anko Commons)
    implementation "org.jetbrains.anko:anko-appcompat-v7-commons:$anko_version"

    // Appcompat-v7 (Anko Layouts)
    implementation "org.jetbrains.anko:anko-appcompat-v7:$anko_version"
    implementation "org.jetbrains.anko:anko-coroutines:$anko_version"

    // CardView-v7
    implementation "org.jetbrains.anko:anko-cardview-v7:$anko_version"

    // Design
    implementation "org.jetbrains.anko:anko-design:$anko_version"
    implementation "org.jetbrains.anko:anko-design-coroutines:$anko_version"

    // GridLayout-v7
    implementation "org.jetbrains.anko:anko-gridlayout-v7:$anko_version"

    // Percent
    implementation "org.jetbrains.anko:anko-percent:$anko_version"

    // RecyclerView-v7
    implementation "org.jetbrains.anko:anko-recyclerview-v7:$anko_version"
    implementation "org.jetbrains.anko:anko-recyclerview-v7-coroutines:$anko_version"

    // Support-v4 (only Anko Commons)
    implementation "org.jetbrains.anko:anko-support-v4-commons:$anko_version"

    // Support-v4 (Anko Layouts)
    implementation "org.jetbrains.anko:anko-support-v4:$anko_version"

    // ConstraintLayout
    implementation "org.jetbrains.anko:anko-constraint-layout:$anko_version"
}
```

위의 추가적인 라이브러리 내용에 보면 ConstraintLayout, RecyclerView등은 별도로 추가를 해서 사용 해야합니다.

 버전 변경이나 추가 라이브러리는 변경 될수도 있으니 Kotlin Anko 공식 GitHub 페이지를 참고하시면 되겠습니다.

 [Kotlin Anko GitHub]  

[Kotlin Anko GitHub]: https://github.com/Kotlin/anko
