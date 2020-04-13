# FixedGrid
> **Extends**: `AGrid`

.

<br/>

## Properties


### colorCellArr

대비부호에 따른 색상값을 적용할 Cell 배열

* **Type**: `Array`
* **Default**: `new Array()`

<br/>

### isAutoReset

데이터 수신시 자동 리셋여부

* **Type**: `Boolean`
* **Default**: `true`

<br/>

### isColorMode

대비부호에 따른 색상값 표현여부

* **Type**: `Boolean`
* **Default**: `false`

<br/>

### offsetCol

데이터를 셋팅할 Cell Offset

* **Type**: `Number`
* **Default**: `0`

<br/>

### offsetRow

데이터를 셋팅할 Row 객체

* **Type**: `Object`
* **Default**: `null`

<br/>

### vSignKey

대비부호의 키 값

* **Type**: `String`
* **Default**: `null`

<br/>
<br/>

## Methods

### resetGrid()

고정그리드의 값을 리셋합니다.

<br/>

### setAutoReset( isAutoReset )

데이터 수신시 자동리셋여부를 셋팅합니다.

* **Parameters**: 
	* **`isAutoReset`** {Boolean} 자동리셋여부

<br/>

### setColorCellInfo( cellArr, vSignKey )

색상을 표현할 셀 배열을 셋팅합니다.

* **Parameters**: 
	* **`cellArr`** {Array} 셀 배열 ex) 각 Row의 첫번째와 네번째 셀에만 색상을 표현하고 싶은 경우 [ 1, 0, 0, 1 ]
	* **`vSignKey`** {String} 대비부호 키값 ex) 'VRSS_SIGN'

<br/>
<br/>
