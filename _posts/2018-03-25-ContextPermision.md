---
layout: post
title: Android Context
description: Android Context 타입 설명
category: android
tags: [이론]
---

## Context


<dl>
<dt>Application에 관하여 시스템이 관리하고 있는 정보에 접근</dt>
<dd> -> getPackageName(), getResource() 등의 함수 호출</dd>

<dt>시스템 서비스에서 제공하는 API를 호출 할 수 있는 기능</dt>
<dd> -> startActivity(), bindService() 등의 함수 호출</dd>
</dl>

위와 같이 Context는 API를 호출하거나 시스템을 호출할때 쓰입니다.


아래의 표를 참고하셔서 개발하는데 도움이 되셨으면 좋겠습니다.



|                            | Application | Activity | Service | Content Provider  | Broadcast Recevier |
|----------------------------|:-----------:|:--------:|:-------:|:-----------------:|:------------------:|
| show a Dialog              |     NO      |    YES   |   NO    |       NO          |         NO         |
| Start an Activity          |     NO      |    YES   |   NO    |       NO          |         NO         |
| Layout Inflation           |     NO      |    YES   |   NO    |       NO          |         NO         |
| Start a Service            |     YES     |    YES   |   YES   |       YES         |         YES        |
| Bind to a Service          |     YES     |    YES   |   YSE   |       YES         |         NO         |
| Send A Broadcast           |     YSE     |    YES   |   YSE   |       YES         |         YES        |
| Register BroadcastReceiver |     YES     |    YES   |   YES   |       YES         |         NO         |
| Load Resource Values       |     YES     |    YES   |   YES   |       YES         |         YES        |
