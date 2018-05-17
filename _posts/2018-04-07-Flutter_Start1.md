---
layout: post
title: Flutter 시작하기 - 1
description: Flutter Android Studio에서 Widget 변경 및 확인하는 방법
category: android
tags: [Flutter]
---

Flutter를 사용하면서 좋은점은 Widget을 변경하면 변경하는 즉시 변경된게 적용이 되는점이 장점입니다.

처음으로 프로젝트를 만들고 실행을 하게되면 아래와 같은 화면이 실행됩니다.

<img src="{{ '/assets/img/Flutter_post_1/Flutter_Start1_1.PNG' | prepend: site.baseurl }}" alt="">

Floating 버튼을 누르면 1씩 증가하는 기능을 합니다.

<img src="{{ '/assets/img/Flutter_post_1/Flutter_Start2_1.png' | prepend: site.baseurl }}" alt="">

위 화면의 'You have pushed the button this many times:'
부분을 'Hellow World'로 바꿔 보겠습니다.

<img src="{{ '/assets/img/Flutter_post_1/Flutter_Start3_1.png' | prepend: site.baseurl }}" alt="">

이렇게 변경을 하고나서 저장을 하게 되면 실행화면에서 'Hellow World' 가 표시됩니다.

<img src="{{ '/assets/img/Flutter_post_1/Flutter_Start4.png' | prepend: site.baseurl }}" alt="">

Flutter는 Widget을 위와 같이 랜더링을 확인할수있습니다.

<img src="{{ '/assets/img/Flutter_post_1/Flutter_Start6_1.PNG' | prepend: site.baseurl }}" alt="">

화면의 오른쪽 화면처럼 Flutter Inspector에서 현재 실행중인 Widget을 확인할수있습니다.

Render Tree 옆 빨간색으로 체크를 해놓은곳에 체크를 해주어야 실행된 앱에서 랜더링을 확인할수 있습니다.

Flutter Inspector가 없다 리본 메뉴에서 View -> Tools Window 에서 추가 하실수 있습니다.

감사합니다!
