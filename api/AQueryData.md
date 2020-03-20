# AQueryData
> **Extends**: 

네트웍 송수신 버퍼의 내용을 쿼리파일 포맷에 맞게 객체화 하는 클래스

<br/>

## Properties


### aquery

AQuery 객체를 저장한다.

* **Type**: `Object`
* **Default**: `aquery`

<br/>

### contiKey

데이터의 연속 구분값. 다음 조회에 대한 정보를 세팅한다.

* **Type**: `String`
* **Default**: `null`

<br/>

### flagObj

송수신에 대한 flag 정보를 세팅하는 객체

* **Type**: `Object`
* **Default**: `{}`

<br/>

### headerInfo

헤더 버퍼에 셋팅할 정보를 담고 있는 객체. AQueryData는 매 전송시마다 생성되므로 하나의 전송에만 세팅된다.

* **Type**: `Object`
* **Default**: `{}`

<br/>

### isReal

수신된 queryData 가 리얼인지 조회인지 여부

* **Type**: `Boolean`
* **Default**: `false`

<br/>

### queryObj

데이터 객체

* **Type**: `Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### enableLazyUpdate()

lazy flag 를 세팅한다. 수신한 데이터를 매핑된 컴포넌트에 반영하는 것을 나중에 처리하고 싶을 때 호출한다.<br/>1. afterOutBlockData 함수에서 queryData.enableLazyUpdate 함수를 호출하고 queryData를 저장한다.<br/>2. 매핑된 컴포넌트에 반영하고 싶은 시점에 저장했던 queryData의 lazyUpdate 함수를 호출한다.

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
var thisObj = this;
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
},
function(queryData) {
　queryData.enableLazyUpdate();
　thisObj.queryData = queryData;
});
// 다른 시점의 다른 함수내부에서 호출
this.queryData.lazyUpdate();
```

<br/>

### getBlockData( blockName )

블락명에 해당하는 쿼리데이터를 반환한다.

* **Returns**: Array

* **Parameters**: 
	* **`blockName`** {String} 블락명

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
　var inBlock1 = queryData.getBlockData('InBlock1');
},
function(queryData) {
　var outBlock1 = queryData.getBlockData('OutBlock1');
});
```

<br/>

### getContiKey()

데이터의 연속 구분값을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
var thisObj = this;
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
　var inBlock1 = queryData.getBlockData('InBlock1');
　queryData.setContiKey(thisObj.contiKey);
},
function(queryData) {
　thisObj.contiKey = queryData.getContiKey();
});
```

<br/>

### getFlag( flagName )

flagName에 매칭되는 flag 값을 리턴한다. flagName 값을 생략하면 flagObj 객체 자체를 리턴한다.

* **Returns**: String Or Boolean Or Object

* **Parameters**: 
	* **`flagName`** {String} .

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
var thisObj = this;
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
},
function(queryData) {
　var flagObj = queryData.getFlag();
});
```

<br/>

### getQueryName()

AQueryData 에 매칭된 쿼리네임을 반환한다. 매칭된 aquery 객체가 없으면 null을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
　var qryName = queryData.getQueryName();
},
function(queryData) {
　var qryName = queryData.getQueryName();
});
```

<br/>

### getQueryObj()

쿼리데이터를 담고 있는 queryObj 객체를 반환한다.

* **Returns**: Object

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
},
function(queryData) {
　var qryObj = queryData.getQueryObj();
});
```

<br/>

### inBlockBuffer( abuf, offset )

쿼리데이터를 전송 버퍼에 넣는다.

* **Parameters**: 
	* **`abuf`** {String} 송신 버퍼 객체
	* **`offset`** {String} 데이터 시작 위치

<br/>

### inBlockOccurs( block )

쿼리의 각 블락정보로 인블락의 사이즈를 구하여 반환한다.

* **Returns**: Number

* **Parameters**: 
	* **`block`** {String} 쿼리 블락 정보 객체

<br/>

### inBlockPrepare()

쿼리데이터 객체 안에 블락명을 키로 한 배열을 만들고, 그 안에 블락 정보는 있지만 데이터는 비어있는 객체을 만든다.

<br/>

### outBlockData( abuf, offset )

수신된 데이터를 버퍼에서 꺼내 쿼리데이터 형식으로 뽑아낸다.

* **Parameters**: 
	* **`abuf`** {String} 수신 버퍼 객체
	* **`offset`** {String} 데이터 시작 위치

<br/>

### outBlockOccurs( block, prevData )

쿼리의 각 블락정보와 블락의 이전 블락정보로 아웃블락의 사이즈를 구하여 반환한다.

* **Returns**: Number

* **Parameters**: 
	* **`block`** {String} 쿼리 블락 정보 객체
	* **`prevData`** {String} 이전 블락 정보 객체

<br/>

### printQueryData()

AQueryData 의 정보를 콘솔에 출력한다.

* **Returns**: String

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
　queryData.printQueryData();
},
function(queryData) {
　if(queryData) queryData.printQueryData();
});
```

<br/>

### searchBlockData( blockName )

쿼리데이터의 블락데이터 중 블락명이 파라미터 블락명과 일치하는 부분이 있는 데이터를 모두 블락명-데이터객체에 넣어 반환한다.

* **Returns**: Object

* **Parameters**: 
	* **`blockName`** {String} 블락명

<br/>

### setContiKey( contiKey )

데이터의 연속 구분값을 지정한다.

* **Parameters**: 
	* **`contiKey`** {String} .

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
var thisObj = this;
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
　queryData.setContiKey(thisObj.contiKey);
},
function(queryData) {});
```

<br/>

### setFlag( flagName, value )

flagObj에 flagName을 key로 하여 value값을 지정한다.

* **Parameters**: 
	* **`flagName`** {String} 플래그명
	* **`value`** {String} 플래그 값

* **Usage**: 
```js
var qm = new QueryManager('sample');
// setNetworkIo, startManager 등 전송 전에 호출하는 항목은 queryManager를 참고하세요.
var thisObj = this;
qm.sendProcessByName('sample01', this.getContainerId(), null,
function(queryData) {
　queryData.setFlag('zipFlag', '1');
},
function(queryData) {});
```

<br/>

### setHeaderInfo( headerInfo )

헤더 버퍼에 채울 정보를 담고 있는 객체를 셋팅한다. 객체의 구조는 소스 참조.

* **Parameters**: 
	* **`headerInfo`** {String} .

* **Usage**: 
```js
var queryData = new AQueryData(AQuery.getSafeQuery('sample01'));
queryData.setHeaderInfo({ testHeader: '2' });
```

<br/>

### setQuery( aquery )

AQuery 객체를 지정한다.

* **Parameters**: 
	* **`aquery`** {String} AQuery 객체

* **Usage**: 
```js
var queryData = new AQueryData();
queryData.setQuery(AQuery.getSafeQuery('sample01'));
```

<br/>

### setQueryObj( queryObj )

데이터 객체를 queryObj 변수에 지정한다.

* **Parameters**: 
	* **`queryObj`** {String} 데이터 객체

<br/>

### getQuery()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
