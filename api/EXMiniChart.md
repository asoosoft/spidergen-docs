# EXMiniChart
> **Extends**: `AComponent`

.

<br/>

## Properties


### basePrice

미니차트 기준가

* **Type**: `Number`
* **Default**: `0`

<br/>

### bottomTextArr

미니차트 하단 텍스트

* **Type**: `Array`
* **Default**: `[ '10', '12', '14' ]`

<br/>

### colorBackground

미니차트 배경색

* **Type**: `String`
* **Default**: `'transparent'`

<br/>

### colorOpt

색상옵션

* **Type**: `Object`
* **Default**: 

<br/>

### ctx

미니차트를 그리는 Canvas Context

* **Type**: `Object`
* **Default**: `null`

<br/>

### data

미니차트 데이터

* **Type**: `Array`
* **Default**: `null`

<br/>

### maxCount

미니차트 그리는 최대 수

* **Type**: `Number`
* **Default**: `360`

<br/>

### termMinute

미니차트 그리는 분 간격

* **Type**: `Number`
* **Default**: `5`

<br/>
<br/>

## Methods

### draw()

미니차트를 그립니다.

<br/>

### setBottomText( textArr )

미니차트 하단 텍스트를 셋팅합니다.

* **Parameters**: 
	* **`textArr`** {Array} 텍스트배열 ex) ['10', '12', '14']

<br/>

### setColors( colors, isDraw )

미니차트의 색상을 셋팅합니다.

* **Parameters**: 
	* **`colors`** {Object} 색상객체; dividerLine: '#1f1f20', //상단 그래프와 하단 텍스트 구분선 색; baseLine: '#c5c7ce', //기준가 선 색; text: '#c5c7ce', //하단 텍스트 색; timeLine: '#1f1f20', //하단 텍스트 간격 선색; up: '#da2c03', //상승 색; down: '#75b02c' //하락 색
	* **`isDraw`** {Boolean} 셋팅 색상 바로 적용 여부 (true: 바로 적용, false: 미적용)

<br/>

### setData( basePrice, data )

미니차트 데이터를 셋팅합니다.

* **Parameters**: 
	* **`basePrice`** {Number} 기준가
	* **`data`** {Array} [종가, 종가...] ex) [1200, 1250...]

<br/>

### setPosition()

미니차트를 그릴 위치를 계산합니다.

<br/>

### setTermValue( termMinute, maxCount )

미니차트 그리는 분 간격과 최대수를 셋팅합니다.

* **Parameters**: 
	* **`termMinute`** {Number} 분
	* **`maxCount`** {Number} 최대수

<br/>
<br/>
