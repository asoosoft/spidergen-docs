<<<<<<< HEAD
# WebsocketIO
> **Extends**: `NetworkIO`

웹소켓 송수신 클래스

<br/>

## Properties


### isSSL

전송 계층 보안 여부

* **Type**: `Boolean`
* **Default**: 

<br/>

### protocols

서브 프로토콜. String 또는 String []

* **Type**: `String`
* **Default**: `''`

<br/>

### socket

WebSocket 인스턴스 저장 변수

* **Type**: `Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### isStart()

네트워크 접속 여부. WebSocket 인스턴스의 저장여부로 판단한다.

* **Returns**: Boolean

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
if(netIo.isStart()) return;
```

<br/>

### sendData( data, callback )

웹소켓을 통해 데이터를 전송한다.

* **Parameters**: 
	* **`data`** {String} UInt8Array 전송 데이터
	* **`callback`** {String} 콜백함수

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
var data = new Uint8Array([116, 101, 115, 116]);
var callback = function(result){ if(!result) alert('test 송신실패') };
netIo.sendData(data, callback);
```

<br/>

### startIO( address, port )

웹소켓 네트워크 접속을 시작한다.

* **Parameters**: 
	* **`address`** {String} 주소
	* **`port`** {String} 포트번호

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
netIo.startIO('127.0.0.1', 80);
```

<br/>

### stopIO( isClosed )

웹소켓 네트워크 연결을 해제한다.

* **Parameters**: 
	* **`isClosed`** {String} 자체 중단 여부 (false: 자체중단, true: 사용자중단)

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
netIo.stopIO();
```

<br/>

### setProtocols()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
=======
# WebsocketIO
> **Extends**: `NetworkIO`

웹소켓 송수신 클래스

<br/>

## Properties


### isSSL

전송 계층 보안 여부

* **Type**: `Boolean`
* **Default**: 

<br/>

### protocols

서브 프로토콜. String 또는 String []

* **Type**: `String`
* **Default**: `''`

<br/>

### socket

WebSocket 인스턴스 저장 변수

* **Type**: `Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### isStart()

네트워크 접속 여부. WebSocket 인스턴스의 저장여부로 판단한다.

* **Returns**: Boolean

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
if(netIo.isStart()) return;
```

<br/>

### sendData( data, callback )

웹소켓을 통해 데이터를 전송한다.

* **Parameters**: 
	* **`data`** {String} UInt8Array 전송 데이터
	* **`callback`** {String} 콜백함수

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
var data = new Uint8Array([116, 101, 115, 116]);
var callback = function(result){ if(!result) alert('test 송신실패') };
netIo.sendData(data, callback);
```

<br/>

### startIO( address, port )

웹소켓 네트워크 접속을 시작한다.

* **Parameters**: 
	* **`address`** {String} 주소
	* **`port`** {String} 포트번호

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
netIo.startIO('127.0.0.1', 80);
```

<br/>

### stopIO( isClosed )

웹소켓 네트워크 연결을 해제한다.

* **Parameters**: 
	* **`isClosed`** {String} 자체 중단 여부 (false: 자체중단, true: 사용자중단)

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
netIo.stopIO();
```

<br/>

### setProtocols()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
>>>>>>> bc729ae47e04917eefd0eaed80c7b915b82b4564
