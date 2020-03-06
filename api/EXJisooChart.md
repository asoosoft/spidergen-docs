# EXJisooChart
> **Extends**: `AComponent`

.

<br/>

## Properties


### colorOpt

색상옵션

* **Type**: `Object`
* **Default**: 

<br/>

### data

지수차트 데이터

* **Type**: `Array`
* **Default**: `new Array()`

<br/>

### delegator

지수차트 데이터 추가 요청 이벤트를 받을 Class

* **Type**: `Object`
* **Default**: `null`

<br/>

### divisionVal

지수차트 데이터를 나눗셈할 값

* **Type**: `Number`
* **Default**: `100`

<br/>

### nextIqryDate

데이터 다음 조회 날짜

* **Type**: `String`
* **Default**: `''`

<br/>

### title

상단 타이틀 Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>

### upperContext

지수차트를 그리는 Canvas Context

* **Type**: `Object`
* **Default**: `null`

<br/>

### upperDom

지수차트를 그리는 Canvas

* **Type**: `Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### drawGraph()

지수차트를 그립니다.

<br/>

### resetData()

지수차트 데이터를 초기화합니다.

<br/>

### setColors( colors )

지수차트의 색상을 셋팅합니다.

* **Parameters**: 
	* **`colors`** {Object} 색상객체; TEXT: '#FFFFFF', //폰트색; DOT: '#5d5d5d', //도트색; LINE: '#F82008', //라인색; START: '#00ff00', //그라디언트 시작색; END: 'rgba(0, 250, 0, 0.0)' //그라디언트 끝색

<br/>

### setData( data )

지수차트 데이터를 셋팅합니다.

* **Parameters**: 
	* **`data`** {Array} [[전송일자, 시가, 고가, 저가, 종가, 누적거래량, 누적 거래 대금]...]

<br/>

### setDelegator( delegator )

delegator를 셋팅합니다.

* **Parameters**: 
	* **`delegator`** {Object} 이벤트를 받을 class

<br/>

### setDivisionVal( divisionVal )

지수차트 데이터를 나눗셈할 값을 셋팅합니다.

* **Parameters**: 
	* **`divisionVal`** {Number} 나눗셈할 값

<br/>

### setPosition()

지수차트를 그릴 위치를 계산합니다.

<br/>

### setTitle( title )

타이틀 문구를 셋팅합니다.

* **Parameters**: 
	* **`title`** {String} 타이틀 문구

<br/>
<br/>
