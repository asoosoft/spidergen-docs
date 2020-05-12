<<<<<<< HEAD
# SocketIO
> **Extends**: `NetworkIO`

네이티브(모바일) 소켓 송수신 클래스

<br/>

## Properties


### workerId

네이티브 송수신 인스턴스의 ID를 저장한다. 네이티브 인스턴스와 웹의 인스턴스의 매칭을 위해서 사용한다.

* **Type**: `Number`
* **Default**: `0`

<br/>
<br/>

## Methods

### isStart()

네트워크 접속 여부. 네이티브 네트워크 인스턴스의 ID 값을 저장한 경우(0 보다 큰 경우) 접속되었다고 판단한다.

* **Returns**: Boolean

* **Usage**: 
```js
var qm = new QueryManager();
var netIo = new SocketIO(qm);
if(netIo.isStart()) return;
```

<br/>

### sendData( data, callback )

네이티브를 통해서 데이터를 전송한다.

* **Parameters**: 
	* **`data`** {String} 전송할 데이터
	* **`callback`** {String} 콜백함수

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new SocketIO(qm);
var data = new Uint8Array([116, 101, 115, 116]);
var callback = function(result){ if(!result) alert('test 송신실패') };
netIo.sendData(data, callback);
```

<br/>

### startIO( address, port )

네이티브 네트워크 접속을 시작한다.(소켓 연결)

* **Parameters**: 
	* **`address`** {String} 주소
	* **`port`** {String} 포트번호

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new SocketIO(qm);
netIo.startIO('127.0.0.1', 80);
```

<br/>

### stopIO( isClosed )

네이티브 네트워크 접속을 해제한다.(소켓 해제)

* **Parameters**: 
	* **`isClosed`** {String} 자체 중단 여부 (false: 자체중단, true: 사용자중단)

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new SocketIO(qm);
netIo.stopIO();
```

<br/>

### SocketIO.onConnected()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### SocketIO.onClosed()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### SocketIO.onReceived()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
=======
# SocketIO
> **Extends**: `NetworkIO`

네이티브(모바일) 소켓 송수신 클래스

<br/>

## Properties


### workerId

네이티브 송수신 인스턴스의 ID를 저장한다. 네이티브 인스턴스와 웹의 인스턴스의 매칭을 위해서 사용한다.

* **Type**: `Number`
* **Default**: `0`

<br/>
<br/>

## Methods

### isStart()

네트워크 접속 여부. 네이티브 네트워크 인스턴스의 ID 값을 저장한 경우(0 보다 큰 경우) 접속되었다고 판단한다.

* **Returns**: Boolean

* **Usage**: 
```js
var qm = new QueryManager();
var netIo = new SocketIO(qm);
if(netIo.isStart()) return;
```

<br/>

### sendData( data, callback )

네이티브를 통해서 데이터를 전송한다.

* **Parameters**: 
	* **`data`** {String} 전송할 데이터
	* **`callback`** {String} 콜백함수

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new SocketIO(qm);
var data = new Uint8Array([116, 101, 115, 116]);
var callback = function(result){ if(!result) alert('test 송신실패') };
netIo.sendData(data, callback);
```

<br/>

### startIO( address, port )

네이티브 네트워크 접속을 시작한다.(소켓 연결)

* **Parameters**: 
	* **`address`** {String} 주소
	* **`port`** {String} 포트번호

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new SocketIO(qm);
netIo.startIO('127.0.0.1', 80);
```

<br/>

### stopIO( isClosed )

네이티브 네트워크 접속을 해제한다.(소켓 해제)

* **Parameters**: 
	* **`isClosed`** {String} 자체 중단 여부 (false: 자체중단, true: 사용자중단)

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new SocketIO(qm);
netIo.stopIO();
```

<br/>

### SocketIO.onConnected()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### SocketIO.onClosed()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### SocketIO.onReceived()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
>>>>>>> bc729ae47e04917eefd0eaed80c7b915b82b4564
