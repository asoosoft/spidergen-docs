# HttpIO
> **Extends**: [`NetworkIO`](./NetworkIO.md)

XMLHttpRequest(XHR) 객체로 HTTP를 통해 데이터를 송수신하는 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

### url \<String>

전송을 요청할 URL

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### isStart()

네트워크 접속 여부. 전송을 요청할 URL이 있는 경우 접속되었다고 판단한다.

* **Returns** \<Boolean>

```js
var qm = new QueryManager();
var netIo = new HttpIO(qm);
if(netIo.isStart()) return;
```

<br/>

### sendData( data, callback )

문자열 또는 바이너리 배열 데이터를 전송한다. 전송 실패시 callback 이 호출된다.

* `data` \<String or Uint8Array> 전송할 데이터
* `callback` \<Function> 전송 실패시 호출되는 콜백함수

```js
var qm = new QueryManager('sample');
var netIo = new HttpIO(qm);
//var data = "{"input1":"test","input2":"send"}";
var data = new Uint8Array([116, 101, 115, 116]);
var callback = function(result){ if(!result) alert('test 송신실패') };
netIo.sendData(data, callback);
```

<br/>

### startIO( url )

전송 url을 지정한다. 네트워크 접속 시작을 의미한다.

* `url` \<String> 전송 url

```js
var qm = new QueryManager('sample');
var netIo = new HttpIO(qm);
netIo.startIO('http://127.0.0.1/sample.jsp');
```

<br/>

### stopIO()

전송 url을 초기화한다. 네트워크 접속 해제를 의미한다.

```js
var qm = new QueryManager('sample');
var netIo = new HttpIO(qm);
netIo.stopIO();
```

<br/>
<br/>