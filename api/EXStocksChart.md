# EXStocksChart
> **Extends**: `AComponent`

.

<br/>

## Properties


### AM_L_WIDTH

주식차트 왼쪽 금액 너비(EPS차트일 경우)

* **Type**: `Number`
* **Default**: `0`

<br/>

### AM_R_WIDTH

주식차트 오른쪽 금액 너비

* **Type**: `Number`
* **Default**: `100`

<br/>

### BAR_CNT

주식차트 그릴 봉 개수

* **Type**: `Number`
* **Default**: `50`

<br/>

### BAR_TERM

봉과 봉 사이 간격

* **Type**: `Number`
* **Default**: `2`

<br/>

### COLOR_ARR

상승하락 색 배열

* **Type**: `Array`
* **Default**: 

<br/>

### COLOR_DIV

상단/하단 그래프 구분선 색

* **Type**: `String`
* **Default**: `'#909090'`

<br/>

### COLOR_DOT

도트색

* **Type**: `String`
* **Default**: `'#FFFFFF'`

<br/>

### COLOR_MINUS

하락색

* **Type**: `String`
* **Default**: `'#60F8F8'`

<br/>

### COLOR_NOR

일반 폰트색

* **Type**: `String`
* **Default**: `'#FFFFFF'`

<br/>

### COLOR_PLUS

상승색

* **Type**: `String`
* **Default**: `'#F82008'`

<br/>

### COLOR_SET

주식차트 상단 Text 색 배열

* **Type**: `Array`
* **Default**: `[ '#F82008', '#C98607', '#177E37' ]`

<br/>

### CURRENT_COLOR_ARR

우측 마지막 현재가 보여주는 상승하락 색 배열

* **Type**: `Array`
* **Default**: `[ '#07a3a3', '#a91505', '#07a3a3' ]`

<br/>

### DEF_BAR_W

기본 봉 너비

* **Type**: `Number`
* **Default**: `80`

<br/>

### delegator

주식차트 데이터 추가 요청 이벤트를 받을 Class

* **Type**: `Object`
* **Default**: `null`

<br/>

### MAX_BAR_W

최대 봉 너비

* **Type**: `Number`
* **Default**: `80`

<br/>

### prdCls

주식차트 조회 구분

* **Type**: `Number`
* **Default**: `0 (0:월, 1:주, 2:일, 5:분, 7틱)`

<br/>

### subType

주식차트 서브 그래프 타입

* **Type**: `Number`
* **Default**: 

<br/>

### SUB_COLOR_SET

주식차트 하단 보조차트 Text 색 배열

* **Type**: `Array`
* **Default**: 

<br/>

### SUB_TEXT_SET

주식차트 하단 보조차트 Text 배열

* **Type**: `Array`
* **Default**: 

<br/>

### TEXT_SET

주식차트 상단 Text 배열

* **Type**: `Array`
* **Default**: `[ 'MA5', 'MA20', 'MA60' ]`

<br/>

### upperContext

주식차트를 그리는 Canvas Context

* **Type**: `Object`
* **Default**: `null`

<br/>

### upperDom

주식차트를 그리는 Canvas

* **Type**: `Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### drawChart()

주식차트를 그립니다.

<br/>

### getIsFirst()

맨처음 데이터인지 아닌지를 리턴합니다.(true: 맨처음 데이터 / false: 추가된 데이터)

* **Returns**: Boolean

<br/>

### resetData()

주식차트 데이터를 리셋합니다.

<br/>

### setData( data )

주식차트 데이터를 셋팅합니다.

* **Parameters**: 
	* **`data`** {Array} [[일자, 시가, 고가, 저가, 종가, 거래량, 거래대금 ], ...]

<br/>

### setDelegator( delegator )

delegator를 셋팅합니다.

* **Parameters**: 
	* **`delegator`** {Object} 이벤트를 받을 class

<br/>

### setIsFirst( isFirst )

맨처음 데이터인지 아닌지를 셋팅합니다.

* **Parameters**: 
	* **`isFirst`** {Boolean} 처음호출여부

<br/>

### setPosition()

주식차트를 그릴 위치를 계산합니다.

<br/>

### setPrdCls( prdCls )

주식차트 조회 구분을 셋팅합니다.

* **Parameters**: 
	* **`prdCls`** {Number} 조회 구분(0:월, 1:주, 2:일, 5:분, 7틱)

<br/>

### setSubGrpType( index, isRefresh )

주식차트 서브그래프 타입을 셋팅합니다.

* **Parameters**: 
	* **`index`** {Number} 타입(0: 거래량, 1: OBV, 2:MACD, 3:Slow, 4:FAST, 5: 이격도, 6: RSI)
	* **`isRefresh`** {Boolean} 서브그래프 타입 셋팅 후 그래프 바로적용 여부

<br/>
<br/>
