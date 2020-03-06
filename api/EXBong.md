# EXBong
> **Extends**: `AComponent`

봉차트

<br/>

## Properties


### bongEl

봉 Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>

### downColor

봉 하락색

* **Type**: `String`
* **Default**: `: '#75b02c'`

<br/>

### isUp

봉 가로/세로 여부

* **Type**: `Boolean`
* **Default**: `false`

<br/>

### lineEl

봉의 중간 라인 Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>

### steadColor

봉 보함색

* **Type**: `String`
* **Default**: `'#dee0e9'`

<br/>

### upColor

봉 상승색

* **Type**: `String`
* **Default**: `'#da2c03'`

<br/>
<br/>

## Methods

### getAttr( key )

파라미터로 넘어온 키에 대응되는 속성 값을 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`key`** {String} 속성 키

<br/>

### resetData()

봉에 적용된 데이터를 초기화합니다.

<br/>

### setColor( color )

봉에 색상을 셋팅합니다.

* **Parameters**: 
	* **`color`** {String} 봉색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>

### setData( valueArr, prdyvrss )

봉에 데이터를 셋팅합니다.

* **Parameters**: 
	* **`valueArr`** {Array} [시가, 고가, 저가, 종가] ex) [1000, 3000, 900, 2000]
	* **`prdyvrss`** {Number} prdyvrss

<br/>

### setDirection( isPort )

봉 가로/세로 여부를 셋팅합니다.

* **Parameters**: 
	* **`isPort`** {Boolean} 가로/세로 여부(true: 가로 / false: 세로)

<br/>

### setDownColor( color )

봉 하락 색상을 셋팅합니다.

* **Parameters**: 
	* **`color`** {String} 하락색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>

### setSteadyColor( color )

봉 보합 색상을 셋팅합니다.

* **Parameters**: 
	* **`color`** {String} 보합색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>

### setUpColor( color )

봉 상승 색상을 셋팅합니다.

* **Parameters**: 
	* **`color`** {String} 상승색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>
<br/>
