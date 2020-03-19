# Application
> **Extends**: 

유일한 전역객체이며 응용프로그램을 관리한다.

<br/>

## Properties


### appContainer

응용프로그램 영역, body 태그 하위로 위치한다.

* **Type**: `HTML Object`
* **Default**: `null`

<br/>

### navigator

페이지 이동을 관리하는 메인 네비게이터 애플리케이션 생성시 기본적으로 생성된다.

* **Type**: `ANavigator`
* **Default**: `null`

<br/>

### orientation

현재 디바이스의 방향

* **Type**: `String`
* **Default**: `'portrait'`

<br/>
<br/>

## Methods

### getCurrentPage()

현재 화면에 보여지고 있는 페이지를 리턴한다.

* **Returns**: APage

<br/>

### getOrientation()

현재 디바이스의 방향을 얻어온다.

<br/>
<br/>
## Events


### onReady()

응용프로그램 구동이 가능한 상태임을 알림 index.html 의 리소스 로드가 완료되면 호출된다.

<br/>

