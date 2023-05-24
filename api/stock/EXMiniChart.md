# EXMiniChart
> **Extends**: [`BaseChart`](./BaseChart.md)

시간, 현재가 데이터를 라인차트로 표시한다.

X축은 시간, Y축은 현재가로 표시하며 설정한 값을 기준으로 위아래 선의 색상을 다르게 표시한다.

<br/>

## Properties


### basePrice \<Number>

미니차트 기준가

<br/>

### maxCount \<Number>

미니차트 그리는 값의 최대 개수

* `Default` 360

<br/>

### frwName \<String>

* `Default` "stock"

<br/>

### colorMode \<String>

색상 모드

* `Default` black 또는 white

<br/>

### dateKey \<Number> or \<String>

하나의 데이터에서 날짜 또는 시간을 표현하는 위치값 또는 키

* `Default` 0

<br/>

### valueKey \<Number> or \<String>

하나의 데이터에서 값을 표현하는 위치값 또는 키

* `Default` 1

<br/>

### priceArr \<2 dimensional Array>

차트를 그리기 위해 필요한 위치와 값을 저장하는 배열

[[최고값, Y위치값], [최저값, Y위치값], [기준값, Y위치값]] 

<br/>

### timeArr \<2 dimensional Array>

시간 데이터 배열 [[index, time], [index, time], ...]

<br/>

### mode \<String>

line, price 모드 선택값(좌측 Y축의 라벨의 표시여부, line이 Y축 라벨 표시X)

<br/>

### termW \<Number>

한개의 시간단위당 표현되는 넓이

<br/>

### maxAm \<Number>

데이터 중 최대값

<br/>

### minAm \<Number>

데이터 중 최소값

<br/>

### defColorObj \<Object>

기본 색상 정보 객체

<br/>

### colorObj \<Object>

설정된 색상 정보 객체

<br/>

### pos \<Object>

포지션 정보 저장 객체

<br/>

### updateTime \<Number>

실시간 TR 매핑했을 때 표시할 시간단위(예를 들어, 5분마다 라인 추가 표시)

- `Default` 300(60*5초, 5분)

<br/>
<br/>

## Methods

### draw()

미니차트를 그리는 함수

<br/>

### setColors( colors, isDraw )

미니차트의 색상을 셋팅한다.

* `color` \<Object> 세팅할 색상 객체
* `isDraw` \<Boolean> 셋팅 색상 바로 적용 여부 (true: 바로 적용, false: 미적용)

```js
this.setColors({
	dividerLine:	'#1f1f20',	//상단 그래프와 하단 텍스트 구분선 색; 
	baseLine:		'#c5c7ce',	//기준가 선 색; 
	text:			'#c5c7ce',	//하단 텍스트 색; 
	timeLine:		'#1f1f20',	//하단 텍스트 간격 선색; 
	up:				'#da2c03',	//상승 색; 
	down:			'#75b02c' 	//하락 색
}, true);
```

<br/>

### setData( data, basePrice )

미니차트 데이터를 셋팅한다.

* `data` \<Array> [종가, 종가...] ex) [1200, 1250...]
* `basePrice` \<Number> 기준가

<br/>

### setMaxCount(maxCount)

표현할 데이터의 최대 갯수를 셋팅한다.

* `maxCount` \<Number> 최대 갯수

<br/>

### setColorMode(colorMode)

차트 컬러모드를 변경한다. ( white, 그외 )

* `colorMode` \<String> 컬러

<br/>

### updatePosition(pWidth, pHeight)

차트의 너비 및 높이를 업데이트한다.

* `pWidth` \<Number> 업데이트 할 너비
* `pHeight` \<Number> 업데이트 할 높이

<br/>

### setKeys(dateKey, valueKey)

데이터에 대한 인덱스 또는 키를 셋팅한다.  

* `dateKey` \<Number> or \<String> 
* `valueKey` \<Number> or \<String> 

<br/>

### addNewData(newData)

차트 데이터를 추가한다.

* `newData` \<Array> 데이터 배열 [시간, 값]

<br/>

### checkDrawPossible()

그리기 가능한 상태인지를 체크한다.

* **Returns** \<Boolean>

<br/>

### calcPosition(elWidth, elHeight)

컴포넌트의 너비와 높이값을 이용하여 canvas에 들어갈 영역 x, y값을 셋팅한다.

* `elWidth` \<Number> 컴포넌트 너비
* `elHeight` \<Number> 컴포넌트 높이

<br/>

### setMaxMin()

차트를 그리기 위해 필요한 위치와 값을 계산하여 [priceArr](#pricearr-2-dimensional-array) 에 지정한다.

[[최고값, Y위치값], [최저값, Y위치값], [기준값, Y위치값]]

<br/>

### updateGraph()

현재 데이터로 차트를 갱신하여 표현한다.

<br/>

### clearGraph()

차트를 초기화한다.

<br/>

### setMode(mode)

차트의 [mode](#mode-string)를 설정한다.

* `mode` \<String> "line" 또는 "price"(좌측 Y축의 라벨의 표시여부, line이 Y축 라벨 표시X)

<br/>

### tempDraw()

데이터가 없을 때 표현하는 0값만 있는 차트를 그린다. 차트 데이터가 없거나 기준값이 없는 경우에 호출된다.

<br/>

### fillRoundedRect(x, y, w, h, r)

기준가를 표시할 때 배경으로 사용되는 사각형을 그린다.

* `x` \<Number> 시작 x좌표
* `y` \<Number> 시작 y좌표
* `w` \<Number> 도형 너비
* `h` \<Number> 도형 높이
* `r` \<Number> 도형 모서리 둥근 정도

<br/>

### drawBack()

차트 배경 및 시간 글자를 그린다.

<br/>

### drawHLine()

최대값, 최소값, 기준값으로 가로라인을 그린다.

<br/>

### drawOnly()

값이 기준가 대비 상승 또는 하락 한가지일 경우 차트를 그린다.

<br/>

### drawBoth()

값이 기준가 대비 상승과 하락이 섞인 경우 차트를 그린다.

<br/>

### drawGradient( gradSY, gradEY, gradColor )

상승 하락에 대한 그라디언트를 표현한다. 

* `gradSY` \<Number> 
* `gradEY` \<Number> 
* `gradColor` \<String>


<br/>

<!-- ### getMappingCount()

<br/>

### getQueryData()

<br/>

### setQueryData()

<br/>
-->
