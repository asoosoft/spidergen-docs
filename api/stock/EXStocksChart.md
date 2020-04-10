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

### upEndDegree



* **Type**: ``
* **Default**: ``

<br/>

### dotDegree



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

### colorObj



* **Type**: ``
* **Default**: ``

<br/>

### maKeyArr



* **Type**: ``
* **Default**: ``

<br/>

### maKeyLen



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

### SIGAIDX



* **Type**: ``
* **Default**: ``

<br/>

### GOGAIDX



* **Type**: ``
* **Default**: ``

<br/>

### JEOGAIDX



* **Type**: ``
* **Default**: ``

<br/>

### JONGGAIDX



* **Type**: ``
* **Default**: ``

<br/>

### DEALQTIDX



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

### dwGrpMaxAm



* **Type**: ``
* **Default**: ``

<br/>

### dwGrpMinAm



* **Type**: ``
* **Default**: ``

<br/>

### pos



* **Type**: ``
* **Default**: ``

<br/>

### drawBackType



* **Type**: ``
* **Default**: ``

<br/>

### drawTextType



* **Type**: ``
* **Default**: ``

<br/>

### drawChartType



* **Type**: ``
* **Default**: ``

<br/>

### drawSubGrpFuncs



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

### init()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### extractColorObj()



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

### changeBtnStyle()



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

### setMAInfo()



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

### reCalcWidth()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### settingDrawSubGrp()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getData()



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

### drawBackText()



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

### drawGraph()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawAvgLine()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawSubLine()



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

### drawBackType0()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType0()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawMaxMinType0()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawChartType0()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### ()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcMaxMinChartType0()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBackType1()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType1()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawMaxMinType1()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawChartType1()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcMaxMinChartType1()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBackType2()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType2()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawMaxMinType2()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawChartType2()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcMaxMinChartType2()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBackType3()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType3()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType3()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawChartType3()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcMaxMinChartType3()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setChartMode()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBackType4()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType4()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawMaxMinType4()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawChartType4()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcMaxMinChartType4()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBackType5()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType5()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawMaxMinType5()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawChartType5()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcMaxMinChartType5()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBackType6()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType6()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawMaxMinType6()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawChartType6()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcMaxMinChartType6()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBackType7()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawTextType7()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawMaxMinType7()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawChartType7()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### calcMaxMinChartType7()



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

### ()



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

### makeChartCanvasData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### makeUpDownData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

###makeMoveAvgData ()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### makeDptData()



* **
**: 


* **Usage**: 
```js

```

<br/>

###makeMacdObvData ()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### makeRSIData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### makeStochasticData()



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

### setQueryData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
