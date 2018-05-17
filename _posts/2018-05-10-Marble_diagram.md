---
layout: post
title: Marble Diagram
description: RxJava Programming을 위한 marble diagram
category: Java&Kotlin
tags: [Java, Kotlin, 이론, ReactiveX]
---

`ReactiveX (RX)` `Java`를 공부를 시작하게 되면서
마블 다이어그램이라는 것을 필연적으로 접하게 되었지만..

처음에는 이 그림이 무엇을 의미하는지 전혀 모르고 있었습니다!

`RxJava` 를 해야된다면 알아야 할 `마블 다이어그램` 을 알게된 내용을 공유하고자 합니다.

<img src="{{ '/assets/img/Marble_diagram/marbleDiagram1.png' | prepend: site.baseurl }}" alt="">

공부를 하려고 찾아 보셨다면 한번쯤은 보게 되었을 다이어그램입니다.

맨 위에 실선으로 오른쪽 방향으로 가는 선의 의미는
 아이템을이 발행되는 순서를 의미하며 다이어그램 상으로는 빨간 별 표시부터 보라색의 마름모 표시까지 순서대로 발행을 의미합니다.

실선의 가장 마지막 단계에 있는 선은 완료를 의미합니다.

<img src="{{ '/assets/img/Marble_diagram/marbleDiagram2.png' | prepend: site.baseurl }}" alt="">

수학에서 표시하는 함수의 표시입니다.

다이어그램 상의 flip 라는 부분이 해당하는 부분이라 생각하시면 될거 같습니다.

어떠한 값이 주어지면 정해진 동작을 하고 난 뒤 반환값을 가지게 됩니다.

위에 flip는 뒤집는다는 의미로 위 실선의 그림의 도형이 아래 실선에서는 뒤집혀서 나오게 됩니다.


위 실선의 도형이 순서대로 반환을 받다가 `X` 표시가 나오게 되는데

해당 `X` 표시는 에러를 의미합니다.

에러가 발생된 뒤에 도형들은 반환되지 않고 종료가 됩니다.

<img src="{{ '/assets/img/Marble_diagram/marbleDiagram3.png' | prepend: site.baseurl }}" alt="">

위 다이어 그램은 RxJava에 Zip 함수입니다.

첫번째 실선에서는 모형을 두번째 실선에서는 색상을 조합하여 반환을 받게되는 함수입니다.

비교적 간단한 다이어그램만 가지고 예를 들었습니다.

처음에는 이게 무엇을 의미하는지 이해가 힘들었지만 내용을 알고나니 훨씬 수월하게 이해할수 있게 되었습니다.

이글이 도움이 되셨으면 좋겠습니다.

감사합니다!
