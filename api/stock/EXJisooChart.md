# EXJisooChart
> **Extends**: `AComponent`

.

<br/>

## Properties

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

### frwName



* **Type**: ``
* **Default**: ``

<br/>

### preScale



* **Type**: ``
* **Default**: ``

<br/>

### rateVal



* **Type**: ``
* **Default**: ``

<br/>

### zoomState



* **Type**: ``
* **Default**: ``

<br/>

### lastDist



* **Type**: ``
* **Default**: ``

<br/>

### scollSX



* **Type**: ``
* **Default**: ``

<br/>

### scollEX



* **Type**: ``
* **Default**: ``

<br/>

### speed



* **Type**: ``
* **Default**: ``

<br/>

### mStartTime



* **Type**: ``
* **Default**: ``

<br/>

### mOldTime



* **Type**: ``
* **Default**: ``

<br/>

### mStartX



* **Type**: ``
* **Default**: ``

<br/>

### mEndX



* **Type**: ``
* **Default**: ``

<br/>

### mScrollLR



* **Type**: ``
* **Default**: ``

<br/>

### timer



* **Type**: ``
* **Default**: ``

<br/>

### offset



* **Type**: ``
* **Default**: ``

<br/>

### startIdx



* **Type**: ``
* **Default**: ``

<br/>

### startLineX



* **Type**: ``
* **Default**: ``

<br/>

### endIdx



* **Type**: ``
* **Default**: ``

<br/>

### BAR_CNT



* **Type**: ``
* **Default**: ``

<br/>

### prdCls



* **Type**: ``
* **Default**: ``

<br/>

### dateformatFunc



* **Type**: ``
* **Default**: ``

<br/>

### dateformat



* **Type**: ``
* **Default**: ``

<br/>

### dashType



* **Type**: ``
* **Default**: ``

<br/>

### TEXT_SIZE



* **Type**: ``
* **Default**: ``

<br/>

### defColorObj



* **Type**: ``
* **Default**: ``

<br/>

### colorObj



* **Type**: ``
* **Default**: ``

<br/>

### touchEvent



* **Type**: ``
* **Default**: ``

<br/>

### isFirst



* **Type**: ``
* **Default**: ``

<br/>

### ROW_CNT



* **Type**: ``
* **Default**: ``

<br/>

### AM_R_WIDTH



* **Type**: ``
* **Default**: ``

<br/>

### AM_L_WIDTH



* **Type**: ``
* **Default**: ``

<br/>

### MAX_BAR_W



* **Type**: ``
* **Default**: ``

<br/>

### DEF_BAR_W



* **Type**: ``
* **Default**: ``

<br/>

### BAR_TERM



* **Type**: ``
* **Default**: ``

<br/>

### upGrpMaxAm



* **Type**: ``
* **Default**: ``

<br/>

### upGrpMinAm



* **Type**: ``
* **Default**: ``

<br/>

### pos



* **Type**: ``
* **Default**: ``

<br/>

### compLeft



* **Type**: ``
* **Default**: ``

<br/>

### middleX



* **Type**: ``
* **Default**: ``

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

### setTitle( title )

타이틀 문구를 셋팅합니다.

* **Parameters**: 
	* **`title`** {String} 타이틀 문구

<br/>

### init()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### initEvent()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### updatePosition()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setZoomEvent()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getTitle()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcPosition()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setIsFirst()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getIsFirst()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setPrdCls()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setMaxMin()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### draw()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBackLine()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setBackLineColor()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setTextColor()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setUpColor()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setDownColor()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### isExistNextData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getOffset()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### barWidthChange()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollLToR()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollRToL()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### updateGraph()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### zoomInOut()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawLongTabData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### autoScroll()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setTouchEvent()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### addNewData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawLongTabLines()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setLongtabLineColor()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getLongtabLineColor()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getQueryData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getMappingCount()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setQueryData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
