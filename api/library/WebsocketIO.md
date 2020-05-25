# WebsocketIO( listener, isSSL )
> **Extends** [`NetworkIO`](./NetworkIO.md)

* `listener` \<Object> 데이터 수신시 호출받을 이벤트 리스너
* `isSSL` \<Boolean> 전송 계층 보안 여부

웹소켓 송수신 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

### isSSL \<Boolean>

전송 계층 보안 여부

<br/>

### protocols \<String>

서브 프로토콜. String 또는 String []

<br/>

### socket [\<WebSocket>](https://developer.mozilla.org/ko/docs/Web/API/WebSocket)

WebSocket 인스턴스

<br/>
<br/>

## Methods

### isStart()

네트워크 접속 여부. WebSocket 인스턴스의 저장여부로 판단한다.

* **Returns** \<Boolean> 네트워크 접속 여부

```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
if(netIo.isStart()) return;
```

<br/>

### sendData( data, callback )

웹소켓을 통해 데이터를 전송한다.

* `data` \<Uint8Array> UInt8Array 전송 데이터
* `callback` \<Function> 콜백함수

```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
var data = new Uint8Array([116, 101, 115, 116]);
var callback = function(result){ if(!result) alert('test 송신실패') };
netIo.sendData(data, callback);
```

<br/>

### setProtocols( protocols )

서브 프로토콜을 지정한다.

* `protocols` \<String or Array> 서브 프로토콜. String 또는 String []

<br/>

### startIO( address, port )

웹소켓 네트워크 접속을 시작한다.

* `address` \<String> 주소
* `port` \<String> 포트번호

```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
netIo.startIO('127.0.0.1', 80);
```

<br/>

### stopIO( isClosed )

웹소켓 네트워크 연결을 해제한다.

* `isClosed` \<Boolean> 자체 중단 여부 (false: 자체중단, true: 사용자중단)

```js
var qm = new QueryManager('sample');
var netIo = new WebsocketIO(qm, false);
netIo.stopIO();
```

<br/>
<br/>
