# HttpIO
> **Extends**: `NetworkIO`

XMLHttpRequest 객체로 HTTP를 통해 데이터를 송수신하는 클래스

<br/>

## Properties


### url

전송을 요청할 URL

* **Type**: `String`
* **Default**: `null`

<br/>
<br/>

## Methods

### isStart()

네트워크 접속 여부. 전송을 요청할 URL이 있는 경우 접속되었다고 판단한다.

* **Returns**: Boolean

* **Usage**: 
```js
var qm = new QueryManager();
var netIo = new HttpIO(qm);
if(netIo.isStart()) return;
```

<br/>

### sendData( data, callback )

데이터를 전송한다.

* **Parameters**: 
	* **`data`** {String} 전송할 데이터
	* **`callback`** {String} 콜백함수

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new HttpIO(qm, false);
var data = new Uint8Array([116, 101, 115, 116]);
var callback = function(result){ if(!result) alert('test 송신실패') };
netIo.sendData(data, callback);
```

<br/>

### startIO( url )

전송 url을 지정한다. 네트워크 접속 시작을 의미한다.

* **Parameters**: 
	* **`url`** {String} .

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new HttpIO(qm);
netIo.startIO('http://127.0.0.1/sample.jsp');
```

<br/>

### stopIO( isClosed )

전송 url을 초기화한다. 네트워크 접속 해제를 의미한다.

* **Parameters**: 
	* **`isClosed`** {String} 자체 중단 여부 (false: 자체중단, true: 사용자중단)

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new HttpIO(qm);
netIo.stopIO();
```

<br/>
<br/>
## Events


### onSendFail()

네트워크 전송에 실패했을 때 호출되는 리스너 메서드.

<br/>

