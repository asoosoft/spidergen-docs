# NetworkIO( listener )
> **Extends** `Object`

* `listener` \<Object> 데이터 수신시 호출받을 이벤트 리스너

네트워크 송수신 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

### curCount \<Number>

네트워크 재접속 시도한 횟수

<br/>

### listener \<Object>

네트워크 관련 이벤트를 전달받을 리스너

<br/>

### retryCount \<Number>

네트워크 재접속 시도 가능 횟수

<br/>

### retryTime \<Number>

재접속을 최초로 시도한 시간(밀리초)

<br/>

### selfClose \<Boolean>

사용자가 아닌 시스템내에서 자체적으로 네트워크 접속을 해제했는지 여부 

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### isStart()

네트워크 접속 여부

* **Returns** \<Boolean>

```js
var qm = new QueryManager();
var netIo = new NetworkIO(qm);
if(netIo.isStart()) return;
```

<br/>

### onConnected( success )

네트워크 연결 요청에 대한 응답이다. 등록된 리스너의 onConnected(success) 함수를 호출한다.

* `success` \<Boolean>> 연결여부

<br/>

### onReceived( data, size )

데이터를 수신하였을 때 호출되는 함수. 리스너의 onReceived 함수를 호출한다. 상속받은 클래스에서 데이터 수신시 압축해제, 복호화, 패킷체인 등의 처리를 해야하는 경우 오버라이드하여 사용해야 한다.

* `data` \<All> 데이터
* `size` \<Number> 데이터 사이즈

<br/>

### sendData( data, callback )

데이터를 전송한다.(추상 함수)

* `data` \<All> 전송할 데이터
* `callback` \<Function> 전송실패 콜백함수

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

* `address` \<String> 주소
* `port` \<String> 포트번호

```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
netIo.startIO('127.0.0.1', 80);
```

<br/>

### stopIO( isClosed )

네트워크 접속을 해제한다.(추상 함수)

* `isClosed` \<String> 자체 중단 여부 (false: 사용자중단, true: 자체중단)

```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
netIo.stopIO();
```

<br/>

### setIoListener( listener )

리스너를 지정한다.

* `listener` \<Object> 리스너 객체

<br/>

### enableRetry( retryCount )

네트워크 재접속 시도 가능 횟수를 지정한다.

* `retryCount` \<Number> 재시도 횟수

<br/>

### onClosed()

네트워크 접속이 끊어졌을 때 호출하는 함수. 리스너의 onClosed 함수를 호출해준다.

<br/>
<br/>

## Events

### onClosed()

네트워크 연결이 끊어졌을 때 호출되는 리스너 메서드.

### onConnected( success )

네트워크 연결에 대한 결과가 나왔을 때 호출되는 리스너 메서드.

* `success` \<Boolean> 연결 여부

### onReceived( data, size )

데이터를 수신했을 때 호출되는 리스너 메서드.

* `data` \<All> 데이터
* `size` \<Number> 데이터 사이즈

<br/>

