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

### maxCount

미니차트 그리는 최대 수

* **Type**: `Number`
* **Default**: `360`

<br/>

### frwName



* **Type**: ``
* **Default**: ``

<br/>

### colorMode



* **Type**: ``
* **Default**: ``

<br/>

### dateKey



* **Type**: ``
* **Default**: ``

<br/>

### valueKey



* **Type**: ``
* **Default**: ``

<br/>

### priceArr



* **Type**: ``
* **Default**: ``

<br/>

### timeArr



* **Type**: ``
* **Default**: ``

<br/>

### timeEnd



* **Type**: ``
* **Default**: ``

<br/>

### mode



* **Type**: ``
* **Default**: ``

<br/>

### termW



* **Type**: ``
* **Default**: ``

<br/>

### isRealMode



* **Type**: ``
* **Default**: ``

<br/>

### maxAm



* **Type**: ``
* **Default**: ``

<br/>

### minAm



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

### pos



* **Type**: ``
* **Default**: ``

<br/>

### updateTime



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### draw()

미니차트를 그립니다.

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

### init()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setMaxCount()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setColorMode()



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

### setKeys()



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

### checkDrawPossible()



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

### setMaxMin()



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

### clearGraph()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setMode()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### tempDraw()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### fillRoundedRect()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBack()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawHLine()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawOnly()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawBoth()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### drawGradient()



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
