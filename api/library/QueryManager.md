# QueryManager( name )
> **Extends**

* `name` \<String> 매니저를 구분짓는 이름

네트웍 전문규약(query 파일)에 따라 데이터를 송수신하는 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

### errCodeMap \<Object>

쿼리별로 특정 에러코드를 담고 있는 객체. 특정 쿼리의 에러코드인 경우 다른 처리를 하는 경우에 사용된다.<br/>{ 'tr0001': ['0001', '0002'], 'tr0002': ['1000', '1001'], .... }

* `Default` `{}`

<br/>

### errorData \<Object>

네트웍 에러 정보를 담고 있는 객체 <br/>trName: '', //쿼리명 <br/>errCode: '', //메시지코드/오류코드 <br/>errMsg: '', //에러 메시지

<br/>

### headerInfo \<Object>

모든 전송에 대해서 헤더 버퍼에 기본적으로 셋팅할 정보를 담고 있는 객체

<br/>

### isShowProgress \<Boolean>

전송시 AIndicator를 보여줄지 여부

* `Default` `true`

<br/>

### netIo \<Object>

io 전송 방식에 따른 객체

<br/>

### packetId \<Number>

패킷 구분 id

* `Default` `0`

<br/>

### packetInfo \<Object>

수신 패킷 정보 객체<br/>{ packetType: 0, packetId: 0, menuNo: '', groupName: '', trName: '' }<br/>패킷타입, 패킷구분 id, 화면번호, 컴포넌트그룹명, 쿼리명

<br/>

### queryCallbacks \<Object>

패킷 구분 id별로 수신시 처리를 할 수 있는 정보를 담아두는 객체

* `Default` `{}`

<br/>

### queryListeners \<Array>

IO 이벤트를 수신할 객체들을 모아둔 배열

* `Default` `[]`

<br/>

### rcvBuf [\<ABuffer>](./../afc/ABuffer.md)

수신용 ABuffer 객체

<br/>

### realComps \<Object>

리얼 데이터를 수신할 컴포넌트 모음. 리얼키에 해당하는 컴포넌트들을 배열로 저장한다.

* `Default` `{}`

<br/>

### realProcMap \<Object>

실시간 등록, 해제를 하기 위한 정보를 담아두는 객체.

* `Default` `{}`

<br/>

### sendInfo \<Object>

전송 패킷 정보 객체<br/>{ packetType: 0, packetId: 0, menuNo: '', groupName: '', trName: '' }<br/>패킷타입, 패킷구분 id, 화면번호, 컴포넌트그룹명, 쿼리명

<br/>

### sndBuf [\<ABuffer>](./../afc/ABuffer.md)

전송용 ABuffer 객체

<br/>

### timeoutSec \<Number>

네트웍 타임아웃 시간(단위: 초)

* `Default` `15`

<br/>

### name \<String>

쿼리매니저를 구분하는 이름

<br/>

### isVisibleUpdate \<Boolean>

컴포넌트가 보이는 경우만 데이터를 업데이트를 하는 옵션

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### addQueryListener( listener )

쿼리 송수신 이벤트를 전달받을 리스너를 추가한다.
<br/><br/># listener functions # <br/>function afterRecvBufferData(abuffer, packetSize, trName); 수신버퍼에 데이터를 수신한 후 바로 호출된다. <br/>function afterOutBlockData(queryData, groupName);  수신된 데이터를 AQueryData 에 채운 후 호출된다. <br/>function beforeInBlockBuffer(queryData, groupName); 전송버퍼에 데이터를 채우기 전에 호출된다. <br/>function beforeSendBufferData(abuffer, packetSize, trName);  전송버퍼의 데이터를 전송하기 바로 전에 호출된다.

* `listener` \<String> 쿼리 송수신 이벤트를 전달받을 리스너

```js
var qm = new QueryManager('sample');
qm.addQueryListener(this);
```

<br/>

### addRealComp( dataKey, comp )

리얼 데이터를 수신할 컴포넌트를 추가한다. 이미 추가되어있는 경우 -1 을 반환하고, 추가가 된 경우 등록된 컴포넌트의 수를 반환한다.

* `dataKey` \<String> 리얼키
* `comp` \<[AComponent](../afc/AComponent.md)> 리얼 수신할 컴포넌트 객체
* **Returns** \<Number> 등록된 컴포넌트의 수

<br/>

### addSkipErrorCode( qryName, errorCode )

쿼리별 특정 에러코드를 저장하는 객체에 에러코드를 추가한다.

* `qryName` \<String> tr명
* `errorCode` \<String> 에러코드

```js
var qm = new QueryManager('sample');
qm.addSkipErrorCode('sample01', '0001');
```

<br/>

### clearAllQueryCallback()

저장된 콜백정보 전체를 제거한다.

<br/>

### clearRealProcess( queryName, menuNo, realQuery )

sendProcessWithReal 메서드를 호출하여 리얼등록한 정보를 제거한다.

* `queryName` \<String> 쿼리명
* `menuNo` \<String> 리얼 등록할 때 사용한 화면 번호. 일반적으로 containerId를 지정한다.
* `realQuery` \<String or Array> 리얼 해제할 리얼쿼리명 또는 배열

```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
qm.clearRealProcess('sample01', this.getContainerId(), 'realTr01');
```

<br/>

### enableDTS()

필드 데이터형이 double 이지만 문자열로 리턴받기를 원할 경우 호출한다.

<br/>

### getHeaderInfo( headerKey )

headerKey 에 매칭되는 헤더 정보를 리턴한다. headerKey 값을 생략하면 headerInfo 객체 자체를 리턴한다.

* `headerKey` \<String> .
* **Returns** \<String or Object> 헤더정보

```js
var qm = new QueryManager('sample');
qm.setHeaderInfo({ testHeader: '1' });
var headerObj = qm.getHeaderInfo(); // { testHeader: '1' }
var headerStr = qm.getHeaderInfo('testHeader'); // '1'
```

<br/>

### getInDataOffset()

전송헤더 이후의 데이터 셋팅 오프셋을 반환한다.(추상함수)

* **Returns** \<Number> 데이터 세팅 오프셋

<br/>

### getLastError( key )

key에 매칭되는 errorData 값을 리턴한다. key 값을 생략하면 errorData 객체 자체를 리턴한다.

* `key` \<String> 키값
* **Returns** \<String or Object>

```js
var qm = new QueryManager('sample');
var errObj = qm.getLastError();
var errCode = qm.getLastError('errCode');
```

<br/>

### getLastPacketInfo( key )

key에 매칭되는 packetInfo 값을 리턴한다. key 값을 생략하면 packetInfo 객체 자체를 리턴한다.

* `key` \<String> 키값
* **Returns** \<String or Object>

```js
var qm = new QueryManager('sample');
var packetInfo = qm.getLastPacketInfo();
```

<br/>

### getOutDataOffset()

수신헤더 이후의 데이터 셋팅 오프셋을 반환한다.(추상함수)

* **Returns** \<Number> 데이터 세팅 오프셋

<br/>

### getQueryCallback( key )

저장된 콜백 정보 중 key 값에 해당하는 정보를 가져온다.

* **Returns** \<All> 보통 콜백함수

* `key` \<String> key 값

<br/>

### getRealComps( dataKey )

키에 해당하는 리얼 데이터를 수신할 컴포넌트 객체 목록을 반환한다.

* `dataKey` \<String> 리얼키
* **Returns** \<Array> 리얼 수신 컴포넌트 목록

<br/>

### isSkipErrorCodee( qryName, errorCode )

쿼리별 특정 에러코드를 저장하는 객체에 에러코드가 있는지 확인한다.

* `qryName` \<String> tr명
* `errorCode` \<String> 에러코드
* **Returns** \<Boolean> skip 여부

```js
var qm = new QueryManager('sample');
qm.isSkipErrorCodee('sample01', '0001'); //true or false
```

<br/>

### makeHeader( queryData, abuf, menuNo )

서버에 데이터를 송신하기 전에 호출되어 헤더 정보를 세팅한다. abuf 객체의 메서드들을 이용하여 세팅한다.

* `queryData` [\<AQueryData>](../afc/AQueryData.md) AQueryData 객체
* `abuf` [\<ABuffer>](../afc/ABuffer.md) ABuffer 객체
* `menuNo` \<String> 화면명

<br/>

### makePacketId()

각 전문을 구분할 수 있는 id 를 생성하여 리턴한다.

* **Returns** \<Number> 패킷아이디

<br/>

### makeQueryData( aquery, isSend )

사용할 AQueryData(또는 상속받은 클래스) 객체를 생성하여 반환한다.(추상함수)

* `aquery` [\<AQuery>](../afc/AQuery.md) AQuery 객체
* `isSend` \<Boolean> 송수신 여부
* **Returns** \<[AQueryData](../afc/AQueryData.md)> 생성한 AQueryData 객체

<br/>

### onClosed()

연결이 끊어졌을 때 호출되는 함수

<br/>

### onConnected( success )

연결에 성공하거나 실패했을 때 호출되는 함수

* `success` \<Boolean> 연결 성공여부

<br/>

### onSendFail()

전송 실패시 호출되는 함수

<br/>

### onReceived( data, size )

데이터를 수신하면 호출되어 수신된 데이터를 처리한다. (추상함수)

* `data` \<String> 데이터
* `size` \<String> 길이

```js
//----------------------------------------------------
//1. this.rcvBuf 를 생성한다. 생성방법은 상황에 따라 다름.
this.rcvBuf.setBuffer(data);
this.rcvBuf.setDataSize(size);

//2. 패킷 타입과 패킷 아이디를 셋팅한다.
this.packetInfo.packetType = this.rcvBuf.getByte(OS_COMM_CMD);
this.packetInfo.packetId = this.rcvBuf.getByte(OS_COMM_ID);

//3. 패킷 타입에 따라 처리 함수를 분기한다.
switch(this.packetInfo.packetType)
{
	case 1: this.queryProcess();
}
//----------------------------------------------------
```

<br/>

### printLastError( key )

key에 매칭되는 errorData 값을 콘솔화면에 출력한다. key 값을 생략하면 errorData 객체 전체를 출력한다.

* `key` \<String> 키값
* **Returns** \<String> 출력 문자열

```js
var qm = new QueryManager('sample');
qm.printLastError();
qm.printLastError('errCode');
```

<br/>

### queryProcess( recvObj )

전문을 수신하고 나서 처리하는 함수
<br/>1.  패킷, 에러 정보를 세팅<br/>2. queryListener 들의 afterRecvBufferData 함수 호출<br/>3. getOutDataOffset 호출하여 데이터 위치 저장<br/>4. makeQueryData 함수 호출하여 queryData 객체 생성<br/>5. queryData 객체에 데이터 시작위치부터 데이터를 추출하여 세팅<br/>6. afterOutBlockData 함수 호출<br/>7. queryListener 들의 afterOutBlockData 함수 호출<br/>8. 전송 컨테이너의 컴포넌트 중 수신한 tr을 매핑한 컴포넌트들에게 데이터를 세팅

* `recvObj` \<Object> recvObj 는 json 형식 수신시 넘어온다.

<br/>

### realDataToComp( key, queryData )

수신한 리얼 데이터를 리얼 등록한 컴포넌트들에게 전달한다.

* `key` \<String> 리얼키
* `queryData` [\<AQueryData>](../afc/AQueryData.md) AQueryData 객체

<br/>

### realProcess()

onReceive 함수 내에서 패킷 타입에 따라 분기하여 호출되는 함수

```js
//----------------------------------------------------
//1. 쿼리 네임을 얻어 queryData 를 생성한다.
var qryName = this.rcvBuf.nextOriString(4),
	aquery = AQuery.getSafeQuery(qryName),
	queryData = this.makeQueryData(aquery);

//2. queryData 객체에 값을 채우고 dataKey 값을 구한 후
queryData.outBlockData(this.rcvBuf, offset);

//3. realDataToComp 함수를 호출한다.
//this.realDataToComp(key, queryData);
//----------------------------------------------------
```

<br/>

### recv_log_helper()

수신된 전문 로그 남기는 함수(추상함수)

<br/>

### registerReal( aquery, realField, keyArr, compArr, updateType, callback )

해당 키에 대해 실시간 요청을 하지 않은 경우에만 실시간 데이터 수신을 하기 위해서 서버에 요청한다.<br/>내부적으로 리얼 컴포넌트들을 저장하고 각 컴포넌트의 updateType 내부변수에 updateType 값을 지정하고 없는 경우 0 으로 지정한다.<br/>updateType: 갱신 타입(-1/prepend, 0/update, 1/append)

* `aquery` \<String or [AQuery](../afc/AQuery.md)> tr명 또는 AQuery 객체
* `realField` \<String> 수신 데이터 중 리얼키가 있는 필드명
* `keyArr` \<Array> 리얼키 목록
* `compArr` \<Array> 컴포넌트 객체 목록
* `updateType`\<Number> 갱신 타입(-1/prepend, 0/update, 1/append)
* `callback` \<Function>> 콜백 함수

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

* `listener` \<String> 쿼리 송수신 이벤트를 전달받을 리스너
* **Returns** \<Object>

```js
var qm = new QueryManager('sample');
qm.removeQueryListener(this);
```

<br/>

### removeRealComp( dataKey, comp )

리얼 데이터 수신 목록에서 컴포넌트 객체를 제거한다. 목록에 없어 제거를 못한 경우 -1 을 반환하고, 제거 된 경우 등록되어있는 컴포넌트의 수를 반환한다.

* `dataKey` \<String> 리얼키
* `comp` \<[AComponent](../afc/AComponent.md)> 리얼 데이터 수신 목록에서 제거할 컴포넌트 객체
* **Returns** \<Number> 등록된 컴포넌트의 수

<br/>

### removeSkipErrorCode( qryName, errorCode )

쿼리별 특정 에러코드를 저장하는 객체에서 에러코드를 제거한다.

* `qryName` \<String> tr명
* `errorCode` \<String> 에러코드

```js
var qm = new QueryManager('sample');
qm.removeSkipErrorCode('sample01', '0001');
```

<br/>

### sendBufferData( buf )

파라미터 abuf 의 데이터를 네트웍으로 전송한다.

* `buf` [\<ABuffer>](../afc/ABuffer.md) 네트웍으로 전송할 ABuffer

<br/>

### sendProcess( aquery, menuNo, groupName, beforeInBlockBuffer, afterOutBlockData )

전문을 송신에 대한 전반적인 처리를 하는 함수<br/>1. 전송 정보를 세팅<br/>2. makeQueryData 함수 호출하여 전송용 queryData 객체 생성 및 inBlock 객체 초기화<br/>3. 전송하는 컨테이너의 컴포넌트 중 송신할 tr을 매핑한 컴포넌트들의 데이터를 쿼리데이터에 세팅<br/>4. beforeInBlockBuffer 함수 호출<br/>5. getInDataOffset 호출하여 전송할 데이터를 세팅할 위치 저장<br/>6. makeHeader 호출하여 버퍼에 헤더 정보 세팅<br/>7. queryListener 들의 beforeSendBufferData함수 호출<br/>8. setQueryCallback 호출하여 패킷아이디를 키로 해서 콜백정보  저장<br/>9. 타임아웃시간이 있으면 타임아웃 함수 호출<br/>10. sorimachiSend 또는 sendBufferData 호출하여 서버에 데이터 전송


* `aquery` \<Object> AQuery 객체
* `menuNo` \<String> 데이터를 수신할 화면 번호를 지정한다. 일반적으로 containerId 를 지정한다.
* `groupName` \<String> 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
* `beforeInBlockBuffer` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
* `afterOutBlockData` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.
* **Returns** \<Number> 패킷아이디

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

### sendProcessByComp( acomp, groupName, beforeInBlockFunc, afterOutBlockFunc, afterUpdateComponent )

acomp 에 맵핑된 query 정보로 데이터를 전송한다.

* `acomp` \<[AComponent](../afc/AComponent.md)> 쿼리 정보가 셋팅된 AComponent
* `groupName` \<String> 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
* `beforeInBlockFunc` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
* `afterOutBlockFunc` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.
* `afterUpdateComponent` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터가 수신되고 컴포넌트에 세팅된 후이다.
* **Returns** \<Number> 패킷아이디

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

### sendProcessByComps( acomps, groupName, beforeInBlockFunc, afterOutBlockFunc, afterUpdateComponent )

acomps 에 맵핑된 query 정보로 데이터를 전송한다.

* `acomps` \<[AComponent](../afc/AComponent.md) Array> 쿼리 정보가 셋팅된 AComponent 배열
* `groupName` \<String> 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
* `beforeInBlockFunc` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
* `afterOutBlockFunc` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.
* `afterUpdateComponent` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터가 수신되고 컴포넌트에 세팅된 후이다.
* **Returns** \<Array> 패킷 아이디 배열

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

### sendProcessByName( queryName, menuNo, groupName, beforeInBlockFunc, afterOutBlockFunc, afterUpdateComponent )

전송할 쿼리네임을 직접 지정하여 데이터를 전송한다.

* `queryName` \<String> 전송할 쿼리네임
* `menuNo` \<String> 데이터를 수신할 화면 번호를 지정한다. 일반적으로 containerId 를 지정한다.
* `groupName` \<String> 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
* `beforeInBlockFunc` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
* `afterOutBlockFunc` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.
* `afterUpdateComponent` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터가 수신되고 컴포넌트에 세팅된 후이다.
* **Returns** \<Number> 패킷아이디

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

### sendProcessByNames( queryNames, menuNo, groupName, beforeInBlockFunc, afterOutBlockFunc, afterUpdateComponent )

전송할 쿼리네임을 여러개 지정하여 데이터를 전송한다.

* `queryNames` \<String> 전송할 쿼리네임의 배열
* `menuNo` \<String> 데이터를 수신할 화면 번호를 지정한다. 일반적으로 containerId 를 지정한다.
* `groupName` \<String> 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
* `beforeInBlockFunc` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
* `afterOutBlockFunc` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.
* `afterUpdateComponent` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터가 수신되고 컴포넌트에 세팅된 후이다.
* **Returns** \<Array> 패킷아이디 배열

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

### sendProcessWithReal( queryName, menuNo, groupName, beforeInBlockBuffer, afterOutBlockData, afterUpdateComponent, option, realCallback )

전송할 쿼리네임을 직접 지정하여 데이터를 전송하고 데이터 수신시 데이터와 option 정보로 리얼을 등록한다.<br/>option = { realQuery:'', keyBlock:'InBlock1', realField:'', updateType: 0 }<br/>realQuery: 리얼쿼리명<br/>keyBlock: 리얼등록으로 등록할 키가 들어있는 블락명<br/>realField: 리얼등록으로 등록할 키가 들어있는 필드명<br/>updateType: 갱신 타입(-1/prepend, 0/update, 1/append)

* **Returns** \<Array>

* `queryName` \<String> 쿼리명
* `menuNo` \<String> 데이터를 수신할 화면 번호를 지정한다. 일반적으로 containerId 를 지정한다.
* `groupName` \<String> 그룹네임이 지정된 컴포넌트만 데이터를 수신하고 싶을 경우 셋팅한다.
* `beforeInBlockBuffer` \<Function> 콜백함수. 호출되는 시점은 데이터의 송수신 플로우의 beforeInBlockBuffer 와 같다.
* `afterOutBlockData` \<Function> 콜백함수. 호출되는 시점은 데이터의 송수신 플로우의 afterOutBlockFunc 와 같다.
* `afterUpdateComponent` \<Function> 콜백함수를 파라미터로 셋팅한다. 호출되는 시점은 데이터가 수신되고 컴포넌트에 세팅된 후이다.
* `option` \<Object> 리얼 등록을 위한 정보를 담고있는 객체
* `realCallback` \<String> 콜백 함수. 리얼 데이터를 수신했을 때 호출된다.

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
function(queryData){
　// 컴포넌트에 세팅후 처리
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

* `aquery` [\<AQuery>](../afc/AQuery.md) AQuery 객체
* `isSet` \<Boolean> 등록 해제 여부
* `regArr` \<Array> 리얼키 배열

<br/>

### send_log_helper()

송신할 전문 로그 남기는 함수(추상함수)

<br/>

### setErrorData( cbObj )

데이터 수신시 에러정보를 세팅하는 함수(추상함수)

* `cbObj` \<Object> 콜백 정보

```js
//----------------------------------------------------
//* rcvBuf에서 에러데이터에 해당하는 정보를 뽑아 저장한다.
this.errorData.errCode = this.rcvBuf.getString(OS_ERR_CODE, SZ_ERR_CODE);
this.errorData.errMsg = this.rcvBuf.getString(OS_ERR_MSG, SZ_ERR_MSG);
//		...
//		etc
//----------------------------------------------------
```

<br/>

### setHeaderInfo( headerInfo )

헤더 버퍼에 채울 정보를 담고 있는 객체를 셋팅한다. 객체의 구조는 소스 참조.

* `headerInfo` \<Object> 헤더 정보 객체

```js
var qm = new QueryManager('sample');
qm.setHeaderInfo({ testHeader: '1' });
var headerObj = qm.getHeaderInfo(); // { testHeader: '1' }
var headerStr = qm.getHeaderInfo('testHeader'); // '1'
```

<br/>

### setNetworkIo( netIo )

네트워크 송수신 역할을 하는 객체를 지정한다.

* `netIo` [\<NetworkIO>](./NetworkIO.md) NetworkIO 객체

```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm); // new WebsocketIO(qm);
qm.setNetworkIo(netIo);
```

<br/>

### setQueryBuffer( sendSize, recvSize, charSet, emptyChar, emptyNumChar )

쿼리 송수신에 사용할 송수신 버퍼를 생성하고 문자와 숫자를 세팅할 때 빈공간에 쓰일 값을 세팅한다. setQueryBuffer 를 호출해야만 송수신이 가능하다.

* `sendSize` \<Number> 전송 버퍼 사이즈
* `recvSize` \<Number> 수신 버퍼 사이즈
* `charSet` \<String> 문자열 인코딩 방식
* `emptyChar`\<Number or String> 문자 빈공간 채울 아스키 코드값
* `emptyNumChar` \<Number or String> 숫자 빈공간 채울 아스키 코드값

```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
```

<br/>

### setQueryCallback( key, callback )

key 값으로 콜백 정보를 등록한다.

* `key` \<String> key(packetId)
* `callback` \<All> 보통 콜백함수

<br/>

### setTimeout( timeoutSec )

전송 후 수신 대기할 시간을 지정한다.

* `timeoutSec` \<Number> 대기 시간(초)

```js
var qm = new QueryManager('sample');
qm.setTimeout(15);
```

<br/>

### showProgress( isShow )

전송시 AIndicator를 보여줄지 여부값을 지정한다.

* `isShow` \<Boolean> AIndicator 사용여부

```js
var qm = new QueryManager('sample');
qm.showProgress(false);
```

<br/>

### startManager( address, port )

네트워크 송수신을 시작한다. netIo의 startIO 메서드를 호출한다.

* `address` \<String> 주소
* `port` \<String> 포트 번호

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

* `aquery` \<String | [AQuery](../afc/AQuery.md)> tr명 또는 AQuery 객체
* `keyArr` \<Array> 리얼키 목록
* `compArr` \<Array> 컴포넌트 객체 목록

```js
var qm = new QueryManager('sample');
var netIo = new NetworkIO(qm);
qm.setNetworkIo(netIo);
qm.setQueryBuffer(1024, 1024, 'euc-kr', 0x20, 0x30);
qm.startManager('127.0.0.1', 80);
qm.unregisterReal('realTr01', ['cd01', 'cd02'], [this.realComp1, this.realComp2]);
```

<br/>
<br/>

## Events

### afterOutBlockData( queryData, groupName )

수신된 데이터를 AQueryData에 채운 후 호출된다. addQueryListener 메서드로 등록한 리스너에 메서드가 있는 경우에만 호출된다.

* `queryData` \<AQueryData> 쿼리데이터 객체
* `groupName` \<String> 그룹명

### afterRecvBufferData( abuffer, packetSize, trName )

수신버퍼에 데이터를 수신한 후 바로 호출된다. addQueryListener 메서드로 등록한 리스너에 메서드가 있는 경우에만 호출된다.

* `abuffer` \<ABuffer> 수신 버퍼
* `packetSize`\<Number> 사이즈
* `trName` \<String> 쿼리명

### beforeInBlockBuffer( queryData, groupName )

전송버퍼에 데이터를 채우기 전에 호출된다. addQueryListener 메서드로 등록한 리스너에 메서드가 있는 경우에만 호출된다.

* `queryData` \<AQueryData> 쿼리데이터 객체
* `groupName` \<String> 그룹명

### beforeSendBufferData( abuffer, packetSize, trName )

전송버퍼의 데이터를 전송하기 바로 전에 호출된다. addQueryListener 메서드로 등록한 리스너에 메서드가 있는 경우에만 호출된다.

* `abuffer` \<ABuffer> 전송 버퍼
* `packetSize`\<Number> 사이즈
* `trName` \<String> 쿼리명

<br/>

