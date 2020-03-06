# HogaGrid
> **Extends**: `AGrid`

.

<br/>

## Properties


### basePrice

기준가

* **Type**: `Number`
* **Default**: `0`

<br/>

### btmCellCnt

하단 데이터 영역 cell 수

* **Type**: `Number`
* **Default**: `6`

<br/>

### btmRowCnt

하단 데이터 영역 row 수

* **Type**: `Number`
* **Default**: `2`

<br/>

### currentPrice

현재가

* **Type**: `Number`
* **Default**: `0`

<br/>

### endHalf

왼쪽 체결량 마지막 cell index

* **Type**: `Number`
* **Default**: `15`

<br/>

### lastRowIdx

상단 마지막 Row의 Index

* **Type**: `Number`
* **Default**: `20`

<br/>

### startHalf

오른쪽 체결량 시작 cell index

* **Type**: `Number`
* **Default**: `17`

<br/>
<br/>

## Methods

### clearContents()

내용과 잔량바를 초기화한다.

* **Usage**: 
```js
this.hogaGrid.clearContents();
```

<br/>

### getBarSize()

잔량바의 높이를 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var barSize = this.hogaGrid.getBarSize();
```

<br/>

### getDownColor()

데이터를 수신했을 때 호가와 기준가를 비교하여 하락일 때 표현되는 글자색상을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var color = this.hogaGrid.getDownColor();
```

<br/>

### getRateMode()

호가 옆에 등락률의 표현 여부를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var isRate = this.hogaGrid.getRateMode();
```

<br/>

### getSteadyColor()

데이터를 수신했을 때 호가와 기준가를 비교하여 보합일 때 표현되는 글자색상을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var color = this.hogaGrid.getStaedyColor();
```

<br/>

### getUpColor()

데이터를 수신했을 때 호가와 기준가를 비교하여 상승일 때 표현되는 글자색상을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var color = this.hogaGrid.getUpColor();
```

<br/>

### initBar()

잔량바를 초기화한다.

* **Usage**: 
```js
this.hogaGrid.initBar();
```

<br/>

### selectCurrentPrice()

현재가가 들어있는 셀을 표시합니다.

<br/>

### setBarSize( size )

잔량바의 높이를 지정한다.

* **Parameters**: 
	* **`size`** {String} 잔량바 높이

* **Usage**: 
```js
this.hogaGrid.setBarSize('50%');
this.hogaGrid.setBarSize('10px');
```

<br/>

### setBasePrice( basePrice )

기준가를 셋팅합니다.

* **Parameters**: 
	* **`basePrice`** {Number} 기준가

<br/>

### setBasePriceKey( basePriceKey )

데이터를 수신했을 때 기준가로 세팅할 필드명을 지정한다.

* **Parameters**: 
	* **`basePriceKey`** {String} 기준가 필드명

* **Usage**: 
```js
this.hogaGrid.setBasePriceKey('baseprice');
```

<br/>

### setCurPriceKey( keyName )

데이터를 수신했을 때 현재가로 세팅할 필드명을 지정한다.

* **Parameters**: 
	* **`keyName`** {String} 현재가 필드명

* **Usage**: 
```js
this.hogaGrid.setCurPriceKey('curprice');
```

<br/>

### setCurrentPrice( currentPrice )

현재가를 지정한다

* **Parameters**: 
	* **`currentPrice`** {Number} 현재가

* **Usage**: 
```js
this.hogaGrid.setCurrentPrice(10000);
```

<br/>

### setCurrentPriceStyleArr( styleArr )

호가 중 현재가를 표현할 상승, 하락, 보합 css 클래스명을 배열로 지정한다.

* **Parameters**: 
	* **`styleArr`** {Array} 현재가 표현 css 클래스명 배열

* **Usage**: 
```js
this.hogaGrid.setCurrentPriceStyleArr(['curup', 'curdown', 'cursteady']);
```

<br/>

### setDownColor( downColor )

데이터를 수신했을 때 호가와 기준가를 비교하여 하락일 때 표현되는 글자색상을 지정한다.

* **Parameters**: 
	* **`downColor`** {String} 하락 글자 색상값

* **Usage**: 
```js
this.hogaGrid.setDownColor('#0000ff');
```

<br/>

### setRateMode( enable )

호가그리드 초기화시 호가 옆에 등락률의 표현 여부를 지정한다.

* **Parameters**: 
	* **`enable`** {Boolean} 등락률 표현 여부

* **Usage**: 
```js
this.hogaGrid.setRateMode(true);
this.hogaGrid.setRateMode(false);
```

<br/>

### setSteadyColor( steadyColor )

데이터를 수신했을 때 호가와 기준가를 비교하여 보합일 때 표현되는 글자색상을 지정한다.

* **Parameters**: 
	* **`steadyColor`** {String} 보합 글자 색상값

* **Usage**: 
```js
this.hogaGrid.setSteadyColor('#000000');
```

<br/>

### setUpColor( upColor )

데이터를 수신했을 때 호가와 기준가를 비교하여 상승일 때 표현되는 글자색상을 지정한다.

* **Parameters**: 
	* **`upColor`** {String} 상승 글자 색상값

* **Usage**: 
```js
this.hogaGrid.setUpColor('#ff0000');
```

<br/>

### toggleRateMode()

호가 옆에 등락률이 없으면 표현하고, 있으면 제거한다.

* **Usage**: 
```js
this.hogaGrid.toggleRateMode();
```

<br/>
<br/>
