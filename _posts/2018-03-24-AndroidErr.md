---
layout: post
title: Android 에러 종류 및 내용
description: Android Exception에러 종류와 내용
category: android
tags: [ERR]
---
<dl>
<dt>ClassNotFoundException</dt>
<dd>클래스를 찾지 못함</dd>
<dt>CloneNotSupportedException</dt>
<dd>인터페이스 미구현</dd>
<dt>IllegalAccessException</dt>
<dd>클래스 접근을 못함</dd>
<dt>InstantiationException</dt>
<dd>추상 클래스 또는 인터페이스를 인스턴스화 하고자 할때</dd>
<dt>InterruptedException</dt>
<dd>쓰레드가 중단 되었을때</dd>
<dt>NoSuchFieldException</dt>
<dd>지정된 필드가 없을때</dd>
<dt>NoSuchMethodException</dt>
<dd>지정된 메소드가 없을때</dd>
<dt>[IOException] CharConversionException</dt>
<dd>문자 변환에서 예외가 발생했을때</dd>
<dt>[IOException] EOFException</dt>
<dd>파일의 끝에 도달했을때</dd>
<dt>[IOException] FileNotFoundException</dt>
<dd>파일이 발견되지 않았을때</dd>
<dt>[IOException] InterruptedIOException</dt>
<dd>입출력 처리가 중단 되었을때</dd>
<dt>[IOException][ObjectStreamException] InvalidClassException</dt>
<dd>시리얼라이즈 처리에 관한 문제가 클래스 안에 있을때</dd>
<dt>[IOException][ObjectStreamException] InvalidObjectException</dt>
<dd>시리얼라이즈된 오브젝트에서 입력 검증에 실패했을때</dd>
<dt>[IOException][ObjectStreamException] NotActiveException</dt>
<dd>스트림 환경이 액티브하지 않을 때 메소드를 호출했을때</dd>
<dt>[IOException][ObjectStreamException] NotSerializableException</dt>
<dd>오브젝트를 시리얼라이즈 할 수 없을때</dd>
<dt>[IOException][ObjectStreamException] OptionalDataException</dt>
<dd>오브젝트를 읽을때 기대 이외의 데이터와 만났을때</dd>
<dt>[IOException][ObjectStreamException] StreamCorruptedException</dt>
<dd>읽은 데이터 스트림이 파손되어 있을때</dd>
<dt>[IOException][ObjectStreamException] WriteAbortedException</dt>
<dd>기록중에 예외가 발생한 스트림을 읽었을때</dd>
<dt>[IOException] SyncFailedException</dt>
<dd>시스템 버퍼를 동기시키는 FileDescriptor.sync()의 호출 실패시</dd>
<dt>[IOException] UnsupportedEncodingException</dt>
<dd>지정된 문자 부호화 형식을 지원하고 있지 않을때</dd>
<dt>[IOException] UTFDataFormatException</dt>
<dd>부정한 UTF-8방식 문자열과 만났을때</dd>
<dt>[RuntimeException] ArithmeticException</dt>
<dd>제로제산 등의 산술 예외 발생시</dd>
<dt>[RuntimeException] ArrayStoreException</dt>
<dd>배열에 부정한 형태의 오브젝트를 저장하고자 할때</dd>
<dt>[RuntimeException] [IllegalArgumentException]</dt>
<dd>IllegalThreadStateException</dd>
<dt>[RuntimeException] [IllegalArgumentException]</dt>
<dd>NumberFormatException</dd>
<dt>[RuntimeException] IllegalMonitorStateException</dt>
<dd>모니터 상태가 부정일때</dd>
<dt>[RuntimeException] IllegalStateException</dt>
<dd>메소드가 요구된 처리를 하기에 적합한 상태에 있지 않을때</dd>
<dt>[RuntimeException] [IndexOutOfBoundException] ArrayIndexOutOfBoundsException</dt>
<dd>범위 밖의 배열 첨자 지정시</dd>
<dt>[RuntimeException] [IndexOutOfBoundException] StringIndexOutOfBoundsException</dt>
<dd>범위 밖의 String 첨자 지정시</dd>
<dt>[RuntimeException] NegativeArraySizeException</dt>
<dd>음의 크기로 배열 크기를 지정하였을때</dd>
<dt>[RuntimeException] NullPointerException</dt>
<dd>오브젝트로 접근했을때</dd>
<dt>[RuntimeException] SecurityException</dt>
<dd>보안 위반시</dd>
<dt>[RuntimeException] UnsupportedOperationException</dt>
<dd>지원되지 않는 메소드를 호출했을때</dd>

</dl>


<dl>
<dt>[LinkageError] ClassCircularityError</dt>
<dd>클래스 초기화중에 순환 참조를 검출시</dd>
<dt>[LinkageError] [ClassFormatError] UnsupportedClassVersionError</dt>
<dd>JVM이 지원되지 않는 버전의 번호를 가진 클래스 파일을 읽고자 할때</dd>
<dt>[LinkageError] ExceptionInInitializerError</dt>
<dd>정적 이니셜라이저로 예외가 발생시</dd>
<dt>[LinkageError] [IncompatibleClassChangeError] AbstracMethodError</dt>
<dd>추상 메소드를 호출했을때</dd>
<dt>[LinkageError] [IncompatibleClassChangeError] IllegalAccessError</dt>
<dd>접근할 수 없는 메소드와 필드를 사용하고자 했을때</dd>
<dt>[LinkageError] [IncompatibleClassChangeError] InstantiationError</dt>
<dd>인터페이스 또는 추상 클래스를 인스턴스화하고자 했을때</dd>
<dt>[LinkageError] [IncompatibleClassChangeError] NoSuchFieldError</dt>
<dd>지정한 필드가 존재하지 않을때</dd>
<dt>[LinkageError] [IncompatibleClassChangeError] NoSuchMethodError</dt>
<dd>지정한 메소드가 존재하지 않을때</dd>
<dt>[LinkageError] NoClassDefFoundError</dt>
<dd>클래스 정의가 발견되지 않았을때</dd>
<dt>[LinkageError] UnsatisfieldLinkError</dt>
<dd>클래스에 포함되는 링크 정보를 해결할 수 없을때</dd>
<dt>[LinkageError] VerifyError</dt>
<dd>클래스 파일안에 부적절한 부분이 있을때</dd>
<dt>ThreadDeath</dt>
<dd>쓰레드가 정지해야만 한다는 의미</dd>
<dt>[VirtualMachineError] InternalError</dt>
<dd>내부에러</dd>
<dt>[VirtualMachineError] OutOfMemoryError</dt>
<dd>메모리부족으로 메모리를 확보 못함</dd>
<dt>[VirtualMachineError] StackOverflowError</dt>
<dd>스택 오버 발생</dd>
<dt>[VirtualMachineError] UnknownError</dt>
<dd>심각한 예외발생</dd>
</dl>

출처 : http://kinjsp.pe.kr/lecture/exception.kin

출처: http://silverbullet.tistory.com/entry/Exception의-종류와-발생원인 [계속 계속 공부하자]
