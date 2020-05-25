# SocketIO( listener )
> **Extends** [`NetworkIO`](./NetworkIO.md)

* `listener` \<Object> 데이터 수신시 호출받을 이벤트 리스너

네이티브(모바일) 소켓 송수신 클래스

<!-- 
## Constructor Parameter

### new SocketIO( listener )

* `listener` \<Object> 소켓연결에 관한 이벤트를 수신할 리스너

<br/> -->

## Class Variables

<br/>

## Instance Variables

### workerId \<Number>

네이티브 송수신 인스턴스의 ID를 저장한다. 네이티브 인스턴스와 웹의 인스턴스의 매칭을 위해서 사용한다.

<br/>
<br/>

## Class Methods

### SocketIO.onConnected( workerId, success )

소켓연결의 결과를 알려주기 위해서 네이티브(Android, iOS)에서 호출하는 함수. 리스너의 onConnected 함수를 호출한다.

<br/>

### SocketIO.onClosed( workerId )

소켓연결이 해제되었을 때 네이티브(Android, iOS)에서 호출하는 함수. 리스너의 onClosed 함수를 호출한다.

<br/>

### SocketIO.onReceived( workerId, strData )

데이터를 수신하였을 때 네이티브(Android, iOS)에서 호출하는 함수. 리스너의 onReceived 함수를 호출한다.

<br/>
<br/>

## Instance Methods

### isStart()

네트워크 접속 여부. 네이티브 네트워크 인스턴스의 ID 값을 저장한 경우(0 보다 큰 경우) 접속되었다고 판단한다.

* **Returns** \<Boolean>

```js
var qm = new QueryManager();
var netIo = new SocketIO(qm);
if(netIo.isStart()) return;
```

<br/>

### sendData( data, callback )

네이티브를 통해서 데이터를 전송한다.

* `data` \<Uint8Array> 전송할 데이터 배열
* `callback` \<Function>> 실패시 호출받을 콜백함수

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

* `address` \<String> 주소
* `port` \<String> 포트번호

```js
var qm = new QueryManager('sample');
var netIo = new SocketIO(qm);
netIo.startIO('127.0.0.1', 80);
```

<br/>

### stopIO( isClosed )

네이티브 네트워크 접속을 해제한다.(소켓 해제)

* `isClosed` \<String> 자체 중단 여부 (true: 자체중단, false: 사용자중단)

```js
var qm = new QueryManager('sample');
var netIo = new SocketIO(qm);
netIo.stopIO();
```

<br/>
<br/>
