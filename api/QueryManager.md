# QueryManager
> **Extends**: 

네트웍 전문규약(query 파일)에 따라 데이터를 송수신하는 클래스

<br/>

## Properties


### errCodeMap

쿼리별로 특정 에러코드를 담고 있는 객체. 특정 쿼리의 에러코드인 경우 다른 처리를 하는 경우에 사용된다.<br/>{ 'tr0001': ['0001', '0002'], 'tr0002': ['1000', '1001'], .... }

* **Type**: `Object`
* **Default**: `{}`

<br/>

### errorData

네트웍 에러 정보를 담고 있는 객체 <br/>trName: '', //쿼리명 <br/>errCode: '', //메시지코드/오류코드 <br/>errMsg: '', //에러 메시지

* **Type**: `Object`
* **Default**: 

<br/>

### headerInfo

모든 전송에 대해서 헤더 버퍼에 기본적으로 셋팅할 정보를 담고 있는 객체

* **Type**: `Object`
* **Default**: `null`

<br/>

### isShowProgress

전송시 AIndicator를 보여줄지 여부

* **Type**: `Boolean`
* **Default**: `true`

<br/>

### netIo

io 전송 방식에 따른 객체

* **Type**: `Object`
* **Default**: `null`

<br/>

### packetId

패킷 구분 id

* **Type**: `Number`
* **Default**: `0`

<br/>

### packetInfo

수신 패킷 정보 객체<br/>{ packetType: 0, packetId: 0, menuNo: '', groupName: '', trName: '' }<br/>패킷타입, 패킷구분 id, 화면번호, 컴포넌트그룹명, 쿼리명

* **Type**: `Object`
* **Default**: 

<br/>

### queryCallbacks

패킷 구분 id별로 수신시 처리를 할 수 있는 정보를 담아두는 객체

* **Type**: `Object`
* **Default**: `{}`

<br/>

### queryListeners

IO 이벤트를 수신할 객체들을 모아둔 배열

* **Type**: `Array`
* **Default**: `[]`

<br/>

### rcvBuf

수신용 ABuffer 객체

* **Type**: `ABuffer`
* **Default**: `null`

<br/>

### realComps

리얼 데이터를 수신할 컴포넌트 모음. 리얼키에 해당하는 컴포넌트들을 배열로 저장한다.

* **Type**: `Object`
* **Default**: `{}`

<br/>

### realProcMap

실시간 등록, 해제를 하기 위한 정보를 담아두는 객체.

* **Type**: `Object`
* **Default**: `{}`

<br/>

### sendInfo

전송 패킷 정보 객체<br/>{ packetType: 0, packetId: 0, menuNo: '', groupName: '', trName: '' }<br/>패킷타입, 패킷구분 id, 화면번호, 컴포넌트그룹명, 쿼리명

* **Type**: `Object`
* **Default**: 

<br/>

### sndBuf

전송용 ABuffer 객체

* **Type**: `ABuffer`
* **Default**: `null`

<br/>

### timeoutSec

네트웍 타임아웃 시간(단위: 초)

* **Type**: `Number`
* **Default**: `15`

<br/>

### name



* **Type**: ``
* **Default**: ``

<br/>

### setHeaderInfo



* **Type**: ``
* **Default**: ``

<br/>

### publicKey



* **Type**: ``
* **Default**: ``

<br/>

### sessionKey



* **Type**: ``
* **Default**: ``

<br/>

### isVisibleUpdate



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### addQueryListener( listener )

쿼리 송수신 이벤트를 전달받을 리스너를 추가한다.<br/><br/># listener functions # <br/>function afterRecvBufferData(abuffer, packetSize, trName); 수신버퍼에 데이터를 수신한 후 바로 호출된다. <br/>function afterOutBlockData(queryData, groupName);  수신된 데이터를 AQueryData 에 채운 후 호출된다. <br/>function beforeInBlockBuffer(queryData, groupName); 전송버퍼에 데이터를 채우기 전에 호출된다. <br/>function beforeSendBufferData(abuffer, packetSize, trName);  전송버퍼의 데이터를 전송하기 바로 전에 호출된다.

* **Parameters**: 
	* **`listener`** {String} 쿼리 송수신 이벤트를 전달받을 리스너

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.addQueryListener(this);
```

<br/>

### addRealComp( dataKey, comp )

리얼 데이터를 수신할 컴포넌트를 추가한다. 이미 추가되어있는 경우 -1 을 반환하고, 추가가 된 경우 등록된 컴포넌트의 수를 반환한다.

* **Returns**: Number

* **Parameters**: 
	* **`dataKey`** {String} 리얼키
	* **`comp`** {String} 리얼 수신할 컴포넌트 객체

<br/>

### addSkipErrorCode( qryName, errorCode )

쿼리별 특정 에러코드를 저장하는 객체에 에러코드를 추가한다.

* **Parameters**: 
	* **`qryName`** {String} tr명
	* **`errorCode`** {String} 에러코드

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.addSkipErrorCode('sample01', '0001');
```

<br/>

### clearAllQueryCallback()

저장된 콜백을 전체를 제거한다.

<br/>

### clearRealProcess( queryName, menuNo, realQuery )

sendProcessWithReal 메서드를 호출하여 리얼등록한 정보를 제거한다.

* **Parameters**: 
	* **`queryName`** {String} 쿼리명
	* **`menuNo`** {String} 리얼 등록할 때 사용한 화면 번호. 일반적으로 containerId를 지정한다.
	* **`realQuery`** {String} 리얼 해제할 리얼쿼리명

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
qm.clearRealProcess('sample01', this.getContainerId(), 'realTr01');
```

<br/>

### getHeaderInfo( headerKey )

headerKey 에 매칭되는 헤더 정보를 리턴한다. headerKey 값을 생략하면 this.headerInfo 객체 자체를 리턴한다.

* **Returns**: String or Object

* **Parameters**: 
	* **`headerKey`** {String} .

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.setHeaderInfo({ testHeader: '1' });
var headerObj = qm.getHeaderInfo(); // { testHeader: '1' }
var headerStr = qm.getHeaderInfo('testHeader'); // '1'
```

<br/>

### getInDataOffset()

전송헤더 이후의 데이터 셋팅 오프셋을 반환한다.(추상함수)

* **Returns**: Number

<br/>

### getLastError( key )

key에 매칭되는 errorData 값을 리턴한다. key 값을 생략하면 errorData 객체 자체를 리턴한다.

* **Returns**: String or Object

* **Parameters**: 
	* **`key`** {String} .

* **Usage**: 
```js
var qm = new QueryManager('sample');
var errObj = qm.getLastError();
var errCode = qm.getLastError('errCode');
```

<br/>

### getLastPacketInfo()

key에 매칭되는 packetInfo 값을 리턴한다. key 값을 생략하면 packetInfo 객체 자체를 리턴한다.

* **Returns**: String Or Object

* **Usage**: 
```js
var qm = new QueryManager('sample');
var packetInfo = qm.getLastPacketInfo();
```

<br/>

### getOutDataOffset()

수신헤더 이후의 데이터 셋팅 오프셋을 반환한다.(추상함수)

* **Returns**: Number

<br/>

### getQueryCallback( key )

저장된 콜백 정보 중 key 값에 해당하는 정보를 찾아 반환한다.

* **Returns**: All

* **Parameters**: 
	* **`key`** {String} key 값

<br/>

### getRealComps( dataKey )

키에 해당하는 리얼 데이터를 수신할 컴포넌트 객체 목록을 반환한다.

* **Returns**: Array

* **Parameters**: 
	* **`dataKey`** {String} 리얼키

<br/>

### makeHeader( queryData, abuf, menuNo )

서버에 데이터를 송신하기 전에 호출되어 헤더 정보를 세팅한다. abuf 객체의 메서드들을 이용하여 세팅한다.

* **Parameters**: 
	* **`queryData`** {String} AQueryData 객체
	* **`abuf`** {Object} ABuffer 객체
	* **`menuNo`** {String} 화면명

<br/>

### makePacketId()

각 전문을 구분할 수 있는 id 를 리턴한다.

* **Returns**: Number

<br/>

### makeQueryData( aquery, isSend )

사용할 AQueryData(또는 상속받은 클래스) 객체를 생성하여 반환한다.(추상함수)

* **Returns**: AQueryData

* **Parameters**: 
	* **`aquery`** {String} AQuery 객체
	* **`isSend`** {String} 송수신 여부

<br/>

### onReceived( data, size )

데이터를 수신하면 호출되어 수신된 데이터를 처리한다. (추상함수)<br/># 개발 방법<br/>1. this.rcvBuf 를 생성한다. 생성방법은 상황에 따라 다름.<br/>this.rcvBuf.setBuffer(data);<br/>this.rcvBuf.setDataSize(size);<br/>	<br/>2. 패킷 타입과 패킷 아이디를 셋팅한다.<br/>this.packetInfo.packetType = this.rcvBuf.getByte(OS_COMM_CMD);<br/>this.packetInfo.packetId = this.rcvBuf.getByte(OS_COMM_ID);<br/><br/>3. 패킷 타입에 따라 처리 함수를 분기한다.<br/>switch(this.packetInfo.packetType) {<br/>    case 1: this.queryProcess();<br/>}

* **Parameters**: 
	* **`data`** {String} 데이터
	* **`size`** {String} 길이

<br/>

### printLastError( key )

key에 매칭되는 errorData 값을 콘솔화면에 출력한다. key 값을 생략하면 this.errorData 객체 전체를 출력한다.

* **Parameters**: 
	* **`key`** {String} .

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.printLastError();
qm.printLastError('errCode');
```

<br/>

### queryProcess()

전문을 수신하고 나서 처리하는 함수<br/>1.  패킷, 에러 정보를 세팅<br/>2. queryListener 들의 afterRecvBufferData 함수 호출<br/>3. getOutDataOffset 호출하여 데이터 위치 저장<br/>4. makeQueryData 함수 호출하여 queryData 객체 생성<br/>5. queryData 객체에 데이터 시작위치부터 데이터를 추출하여 세팅<br/>6. afterOutBlockData 함수 호출<br/>7. queryListener 들의 afterOutBlockData 함수 호출<br/>8. 전송 컨테이너의 컴포넌트 중 수신한 tr을 매핑한 컴포넌트들에게 데이터를 세팅

<br/>

### realDataToComp( key, queryData )

수신한 리얼 데이터를 리얼 등록한 컴포넌트들에게 전달한다.

* **Parameters**: 
	* **`key`** {String} 리얼키
	* **`queryData`** {String} AQueryData 객체

<br/>

### realProcess()

onReceive 함수 내에서 패킷 타입에 따라 분기하여 호출되는 함수<br/>#개발 방법<br/>1. 쿼리 네임을 얻어 queryData 를 생성한다.<br/>var qryName = this.rcvBuf.nextOriString(4),<br/>aquery = AQuery.getSafeQuery(qryName),<br/>queryData = this.makeQueryData(aquery);<br/>	<br/>2. queryData 객체에 값을 채우고 dataKey 값을 구한 후<br/>queryData.outBlockData(this.rcvBuf, offset);<br/><br/>3. realDataToComp 함수를 호출한다.

<br/>

### recv_log_helper()

수신한 전문에 대한 로그를 남긴다.

<br/>

### registerReal( aquery, realField, keyArr, compArr, updateType, callback )

해당 키에 대해 실시간 요청을 하지 않은 경우에만 실시간 데이터 수신을 하기 위해서 서버에 요청한다.<br/>내부적으로 리얼 컴포넌트들을 저장하고 각 컴포넌트의 updateType 내부변수에 updateType 값을 지정하고 없는 경우 0 으로 지정한다.<br/>updateType: 갱신 타입(-1/prepend, 0/update, 1/append)

* **Parameters**: 
	* **`aquery`** {String} AQuery 객체 또는 tr명
	* **`realField`** {String} 수신 데이터 중 리얼키가 있는 필드명
	* **`keyArr`** {Array} 리얼키 목록
	* **`compArr`** {Array} 컴포넌트 객체 목록
	* **`updateType`** {Number} 갱신 타입
	* **`callback`** {String} 콜백 함수

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
qm.registerReal('realTr01', 'codeField', ['cd01', 'cd02'], [this.realComp1, this.realComp2], 0,
function(queryData)
{
　// 수신시 처리
});
```

<br/>

### removeQueryListener( listener )

쿼리 송수신 이벤트 리스너를 제거한다.

* **Returns**: Object

* **Parameters**: 
	* **`listener`** {String} 쿼리 송수신 이벤트를 전달받을 리스너

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.removeQueryListener(this);
```

<br/>

### removeRealComp( dataKey, comp )

리얼 데이터 수신 목록에서 컴포넌트 객체를 제거한다. 목록에 없어 제거를 못한 경우 -1 을 반환하고, 제거 된 경우 등록되어있는 컴포넌트의 수를 반환한다.

* **Returns**: Number

* **Parameters**: 
	* **`dataKey`** {String} 리얼키
	* **`comp`** {String} 리얼 데이터 수신 목록에서 제거할 컴포넌트 객체

<br/>

### removeSkipErrorCode( qryName, errorCode )

쿼리별 특정 에러코드를 저장하는 객체에서 에러코드를 추가한다.

* **Parameters**: 
	* **`qryName`** {String} tr명
	* **`errorCode`** {String} 에러코드

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.removeSkipErrorCode('sample01', '0001');
```

<br/>

### sendBufferData( abuf, sendLen )

파라미터 abuf 의 데이터를 네트웍으로 전송한다.

* **Parameters**: 
	* **`abuf`** {String} 네트웍으로 전송할 ABuffer
	* **`sendLen`** {String} 전송할 길이

<br/>

### sendProcess( aquery, menuNo, groupName, beforeInBlockBuffer, afterOutBlockData )

전문을 송신에 대한 전반적인 처리를 하는 함수<br/>1. 전송 정보를 세팅<br/>2. makeQueryData 함수 호출하여 전송용 queryData 객체 생성 및 inBlock 객체 초기화<br/>3. 전송하는 컨테이너의 컴포넌트 중 송신할 tr을 매핑한 컴포넌트들의 데이터를 쿼리데이터에 세팅<br/>4. beforeInBlockBuffer 함수 호출<br/>5. getInDataOffset 호출하여 전송할 데이터를 세팅할 위치 저장<br/>6. makeHeader 호출하여 버퍼에 헤더 정보 세팅<br/>7. queryListener 들의 beforeSendBufferData함수 호출<br/>8. setQueryCallback 호출하여 패킷아이디를 키로 해서 콜백정보  저장<br/>9. 타임아웃시간이 있으면 타임아웃 함수 호출<br/>10. sorimachiSend 또는 sendBufferData 호출하여 서버에 데이터 전송

* **Returns**: Number

* **Parameters**: 
	* **`aquery`** {Object} AQuery 객체
	* **`menuNo`** {String} 데이터를 수신할 화면 번호를 지정한다. 일반적으로 containerId 를 지정한다.
	* **`groupName`** {String} 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
	* **`beforeInBlockBuffer`** {Function} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
	* **`afterOutBlockData`** {Function} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
var packetId = qm.sendProcess(AQuery.getSafeQuery('sample01'), this.getContainerId(), this.mappingComp.getGroupName(),
function(queryData) {
　var inBlock1 = queryData.getBlockData('InBlock1')[0];// 전송 전 처리
},
function(queryData) {
　var outBlock1 = queryData.getBlockData('OutBlock1'); // 수신 후 처리
});
```

<br/>

### sendProcessByComp( acomp, groupName, beforeInBlockFunc, afterOutBlockFunc )

acomp 에 맵핑된 query 정보로 데이터를 전송한다.

* **Returns**: Array

* **Parameters**: 
	* **`acomp`** {String} 쿼리 정보가 셋팅된 AComponent
	* **`groupName`** {String} 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
	* **`beforeInBlockFunc`** {Function} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
	* **`afterOutBlockFunc`** {String} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
var packetIdArr = qm.sendProcessByComp(this.sendComp, this.mappingComp.getGroupName(),
function(queryData) {
　var inBlock1 = queryData.getBlockData('InBlock1')[0];// 전송 전 처리
},
function(queryData) {
　var outBlock1 = queryData.getBlockData('OutBlock1'); // 수신 후 처리
});
```

<br/>

### sendProcessByComps( acomps, groupName, beforeInBlockFunc, afterOutBlockFunc )

acomps 에 맵핑된 query 정보로 데이터를 전송한다.

* **Returns**: Array

* **Parameters**: 
	* **`acomps`** {String} 쿼리 정보가 셋팅된 AComponent 배열
	* **`groupName`** {String} 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
	* **`beforeInBlockFunc`** {Function} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
	* **`afterOutBlockFunc`** {String} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
var sendCompArr = [this.sendComp1, this.sendComp2];
var packetIdArr = qm.sendProcessByComps(sendCompArr, this.mappingComp.getGroupName(),
function(queryData) {
　var inBlock1 = queryData.getBlockData('InBlock1')[0];// 전송 전 처리
},
function(queryData) {
　var outBlock1 = queryData.getBlockData('OutBlock1'); // 수신 후 처리
});
```

<br/>

### sendProcessByName( queryName, menuNo, groupName, beforeInBlockFunc, afterOutBlockFunc )

전송할 쿼리네임을 직접 지정하여 데이터를 전송한다.

* **Returns**: Array

* **Parameters**: 
	* **`queryName`** {String} 전송할 쿼리네임
	* **`menuNo`** {String} 데이터를 수신할 화면 번호를 지정한다. 일반적으로 containerId 를 지정한다.
	* **`groupName`** {String} 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
	* **`beforeInBlockFunc`** {Function} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
	* **`afterOutBlockFunc`** {String} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
var packetIdArr = qm.sendProcessByName('sample01', this.getContainerId(), this.mappingComp.getGroupName(),
function(queryData) {
　var inBlock1 = queryData.getBlockData('InBlock1')[0];// 전송 전 처리
},
function(queryData) {
　var outBlock1 = queryData.getBlockData('OutBlock1'); // 수신 후 처리
});
```

<br/>

### sendProcessByNames( queryNames, menuNo, groupName, beforeInBlockFunc, afterOutBlockFunc )

전송할 쿼리네임을 여러개 지정하여 데이터를 전송한다.

* **Returns**: Array

* **Parameters**: 
	* **`queryNames`** {String} 전송할 쿼리네임의 배열
	* **`menuNo`** {String} 데이터를 수신할 화면 번호를 지정한다. 일반적으로 containerId 를 지정한다.
	* **`groupName`** {String} 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
	* **`beforeInBlockFunc`** {Function} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
	* **`afterOutBlockFunc`** {String} 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
var qryNames = ['sample01', 'sample02'];
var packetIdArr = qm.sendProcessByNames(qryNames, this.getContainerId(), this.mappingComp.getGroupName(),
function(queryData) {
　var inBlock1 = queryData.getBlockData('InBlock1')[0];// 전송 전 처리
},
function(queryData) {
　var outBlock1 = queryData.getBlockData('OutBlock1'); // 수신 후 처리
});
```

<br/>

### sendProcessWithReal( queryName, menuNo, groupName, beforeInBlockBuffer, afterOutBlockData, option, realCallback )

전송할 쿼리네임을 직접 지정하여 데이터를 전송하고 데이터 수신시 데이터와 option 정보로 리얼을 등록한다.<br/>option = { realQuery:'', keyBlock:'InBlock1', realField:'', updateType: 0 }<br/>realQuery: 리얼쿼리명<br/>keyBlock: 리얼등록으로 등록할 키가 들어있는 블락명<br/>realField: 리얼등록으로 등록할 키가 들어있는 필드명<br/>updateType: 갱신 타입(-1/prepend, 0/update, 1/append)

* **Returns**: Array

* **Parameters**: 
	* **`queryName`** {String} 쿼리명
	* **`menuNo`** {String} 데이터를 수신할 화면 번호를 지정한다. 일반적으로 containerId 를 지정한다.
	* **`groupName`** {String} 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
	* **`beforeInBlockBuffer`** {Function} 콜백함수. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
	* **`afterOutBlockData`** {Function} 콜백함수. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.
	* **`option`** {Object} 리얼 등록을 위한 정보를 담고있는 객체
	* **`realCallback`** {String} 콜백 함수. 리얼 데이터를 수신했을 때 호출된다.

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
qm.sendProcessWithReal('sample01', this.getContainerId(), this.grpComp.getGroupName(),
function(queryData){
　// 데이터 전송시 처리
},
function(queryData){
　// 데이터 수신시 처리
},
{ realQuery:'realTr01', keyBlock:'InBlock1', realField:'codeField', updateType: 0 },
function(queryData)
{
　// 리얼 데이터 수신시 처리
});
```

<br/>

### sendRealSet( aquery, isSet, regArr )

리얼 등록, 해제 패킷을 전송한다. registerReal, unregisterReal 함수 내에서 호출한다.(추상함수)

* **Parameters**: 
	* **`aquery`** {String} AQuery 객체
	* **`isSet`** {Boolean} 등록 해제 여부
	* **`regArr`** {String} 리얼키 배열

<br/>

### send_log_helper()

송신할 전문에 대한 로그를 남긴다.

<br/>

### setErrorData( cbObj )

데이터 수신시 에러정보를 세팅하는 함수<br/>#개발 방법<br/>rcvBuf에서 에러데이터에 해당하는 정보를 뽑아 저장한다.<br/>this.errorData.errCode = this.rcvBuf.getString(OS_ERR_CODE, SZ_ERR_CODE);<br/>this.errorData.errMsg = this.rcvBuf.getString(OS_ERR_MSG, SZ_ERR_MSG);

* **Parameters**: 
	* **`cbObj`** {Object} 콜백 정보

<br/>

### setHeaderInfo( headerInfo )

헤더 버퍼에 채울 정보를 담고 있는 객체를 셋팅한다. 객체의 구조는 소스 참조.

* **Parameters**: 
	* **`headerInfo`** {String} .

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.setHeaderInfo({ testHeader: '1' });
var headerObj = qm.getHeaderInfo(); // { testHeader: '1' }
var headerStr = qm.getHeaderInfo('testHeader'); // '1'
```

<br/>

### setNetworkIo( netIo )

네트워크 송수신 역할을 하는 객체를 지정한다.

* **Parameters**: 
	* **`netIo`** {String} NetworkIO 객체

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm); // new WebsocketIO(qm);
qm.setNetworkIo(netIo);
```

<br/>

### setQueryBuffer( sendSize, recvSize, charSet, emptyChar, emptyNumChar )

쿼리 송수신에 사용할 송수신 버퍼를 생성하고 문자와 숫자를 세팅할 때 빈공간에 쓰일 값을 세팅한다. setQueryBuffer 를 호출해야만 송수신이 가능하다.

* **Parameters**: 
	* **`sendSize`** {String} 전송 버퍼 사이즈
	* **`recvSize`** {String} 수신 버퍼 사이즈
	* **`charSet`** {String} 문자열 인코딩 방식
	* **`emptyChar`** {Number} 문자 빈공간 채울 아스키 코드값
	* **`emptyNumChar`** {String} 숫자 빈공간 채울 아스키 코드값

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
```

<br/>

### setQueryCallback( key, callback )

key 값으로 콜백 정보를 등록한다.

* **Parameters**: 
	* **`key`** {String} .
	* **`callback`** {String} .

<br/>

### setTimeout( timeoutSec )

전송 후 수신 대기할 시간을 지정한다.

* **Parameters**: 
	* **`timeoutSec`** {String} 대기 시간(초)

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.setTimeout(15);
```

<br/>

### showProgress( isShow )

전송시 AIndicator를 보여줄지 여부값을 지정한다.

* **Parameters**: 
	* **`isShow`** {String} .

* **Usage**: 
```js
var qm = new QueryManager('sample');
qm.showProgress(false);
```

<br/>

### startManager( address, port )

네트워크 송수신을 시작한다. netIo의 startIO 메서드를 호출한다.

* **Parameters**: 
	* **`address`** {String} 주소
	* **`port`** {String} 포트 번호

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
```

<br/>

### stopManager()

네트워크 송수신을 중지한다. netIo 의 stopIO 를 호출한다.

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
qm.stopManager();
```

<br/>

### unregisterReal( aquery, keyArr, compArr )

특정 키에 대해 저장된 컴포넌트가 없으면 실시간 해제를 서버에 요청한다. <br/>특정 키에 저장된 컴포넌트들 중 해당하는 컴포넌트만 제거하고 각 컴포넌트의 updateType 값을 제거한다.

* **Parameters**: 
	* **`aquery`** {Object} AQuery 객체 또는 tr명
	* **`keyArr`** {Array} 리얼키 목록
	* **`compArr`** {Array} 컴포넌트 객체 목록

* **Usage**: 
```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
qm.unregisterReal('realTr01', ['cd01', 'cd02'], [this.realComp1, this.realComp2]);
```

<br/>

### getLastError()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onConnected()



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

### enableDTS()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onSendFail()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### isSkipErrorCode()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>

## Events


### afterOutBlockData( queryData, groupName )

수신된 데이터를 AQueryData에 채운 후 호출된다. addQueryListener 메서드로 등록한 리스너에 메서드가 있는 경우에만 호출된다.

* **Parameters**: 
	* **`queryData`** {AQueryData} 쿼리데이터 객체
	* **`groupName`** {String} 그룹명

### afterRecvBufferData( abuffer, packetSize, trName )

수신버퍼에 데이터를 수신한 후 바로 호출된다. addQueryListener 메서드로 등록한 리스너에 메서드가 있는 경우에만 호출된다.

* **Parameters**: 
	* **`abuffer`** {ABuffer} 수신 버퍼
	* **`packetSize`** {Number} 사이즈
	* **`trName`** {String} 쿼리명

### beforeInBlockBuffer( queryData, groupName )

전송버퍼에 데이터를 채우기 전에 호출된다. addQueryListener 메서드로 등록한 리스너에 메서드가 있는 경우에만 호출된다.

* **Parameters**: 
	* **`queryData`** {AQueryData} 쿼리데이터 객체
	* **`groupName`** {String} 그룹명

### beforeSendBufferData( abuffer, packetSize, trName )

전송버퍼의 데이터를 전송하기 바로 전에 호출된다. addQueryListener 메서드로 등록한 리스너에 메서드가 있는 경우에만 호출된다.

* **Parameters**: 
	* **`abuffer`** {ABuffer} 전송 버퍼
	* **`packetSize`** {Number} 사이즈
	* **`trName`** {String} 쿼리명

<br/>

