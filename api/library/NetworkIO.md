# NetworkIO
> **Extends**: `Object`

네트워크 송수신 클래스

<br/>

## Properties

### curCount

네트워크 재접속 시도한 횟수

* **Type**: `Number`
* **Default**: `0`

<br/>

### listener

네트워크 관련 이벤트를 전달받을 리스너

* **Type**: `Object`
* **Default**: `listener`

<br/>

### retryCount

네트워크 재접속 시도 가능 횟수

* **Type**: `Number`
* **Default**: `0`

<br/>

### retryTime

재접속을 최초로 시도한 시간(밀리초)

* **Type**: `Number`
* **Default**: `0`

<br/>

### selfClose



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### isStart()

네트워크 접속 여부

* **Returns**: Boolean

* **Usage**: 
```js
var qm = new QueryManager();
var netIo = new NetworkIO(qm);
if(netIo.isStart()) return;
```

<br/>

### onConnected( success )

네트워크 연결 요청에 대한 응답이다. 등록된 리스너의 onConnected(success) 함수를 호출한다.

* **Parameters**: 
	* **`success`** {String} 연결여부

<br/>

### onReceived( data, size )

데이터를 수신하였을 때 호출되는 함수. 리스너의 onReceived 함수를 호출한다. 상속받은 클래스에서 데이터 수신시 압축해제, 복호화, 패킷체인 등의 처리를 해야하는 경우 오버라이드하여 사용해야 한다.

* **Parameters**: 
	* **`data`** {All} 데이터
	* **`size`** {Number} 데이터 사이즈

<br/>

### sendData( data, callback )

데이터를 전송한다.(추상 함수)

* **Parameters**: 
	* **`data`** {String} 전송할 데이터
	* **`callback`** {String} 콜백함수

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
var data = new Uint8Array([116, 101, 115, 116]);
var callback = function(result){ if(!result) alert('test 송신실패') };
netIo.sendData(data, callback);
```

<br/>

### startIO( address, port )

네트워크 접속을 시작한다.(추상 함수)

* **Parameters**: 
	* **`address`** {String} 주소
	* **`port`** {String} 포트번호

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
netIo.startIO('127.0.0.1', 80);
```

<br/>

### stopIO( isClosed )

네트워크 접속을 해제한다.(추상 함수)

* **Parameters**: 
	* **`isClosed`** {String} 자체 중단 여부 (false: 자체중단, true: 사용자중단)

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
netIo.stopIO();
```

<br/>

### setIoListener()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### enableRetry()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onClosed()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>

## Events

### onClosed()

네트워크 연결이 끊어졌을 때 호출되는 리스너 메서드.

### onConnected( success )

네트워크 연결에 대한 결과가 나왔을 때 호출되는 리스너 메서드.

* **Parameters**: 
	* **`success`** {Boolean} 연결 여부

### onReceived( data, size )

데이터를 수신했을 때 호출되는 리스너 메서드.

* **Parameters**: 
	* **`data`** {All} 데이터
	* **`size`** {Number} 데이터 사이즈

<br/>

