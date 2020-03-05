# SocketManager
> **Extends**: 

네이티브 소켓 플러그인과 연동하는 클래스

<br/>

## Properties


### listener

네트웍 송수신 이벤트 함수를 구현할 리스너 객체

* **Type**: `Object`
* **Default**: `listener`

<br/>

### workerId

네이티브 소켓 생성시 할당되는 고유 아이디

* **Type**: `Number`
* **Default**: `0`

<br/>
<br/>

## Methods

### getLocalAddress( callBack )

로컬 기기의 아이피 주소를 얻어온다.

* **Parameters**: 
	* **`callBack`** {Function} 아이피 정보를 전달받을 콜백 함수

<br/>

### isStart()

SocketManager 가 송수신 가능 상태인지를 리턴한다.

* **Returns**: Boolean

<br/>

### requestSend( data, resultCallback )

소켓에 데이터 전송을 요청한다. 바이너리 데이터인 경우 base64 문자열로 변환하여 호출해야 한다.

* **Parameters**: 
	* **`data`** {String} 전송할 문자열 데이터
	* **`resultCallback`** {Function} 전송 결과가 전달될 콜백함수

<br/>

### startManager( address, port )

네트워크 송수신을 시작한다. netIo의 startIO 메서드를 호출한다.

* **Parameters**: 
	* **`address`** {String} 접속할 주소
	* **`port`** {Number} 접속할 포트

<br/>

### stopManager()

SocketManager 를 종료한다. 즉, 소켓 접속을 종료하고 송수신 불가능 상태로 만든다.

<br/>
<br/>
## Events


### SocketManager.onClosed( workerId )

소켓 연결이 끊어지면 호출된다. listener 의 onClosed 함수를 호출해준다.

* **Parameters**: 
	* **`workerId`** {Number} 소켓을 구분짓는 고유 아이디

### SocketManager.onConnected( workerId, success )

소켓 연결이 성공하거나 실패하면 호출된다. listener 의 onConnected 함수를 호출해준다.

* **Parameters**: 
	* **`workerId`** {Number} 소켓을 구분짓는 고유 아이디
	* **`success`** {Boolean} 소켓 연결 성공 여부

### SocketManager.onReceived( workerId, strData )

소켓이 데이터를 수신하면 호출해 준다. listener 의 onReceived 함수를 호출해준다.

* **Parameters**: 
	* **`workerId`** {Number} 소켓을 구분짓는 고유 아이디
	* **`strData`** {String} 수신된 데이터

<br/>

