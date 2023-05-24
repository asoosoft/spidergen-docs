# BaseChart
> **Extends** [`AComponent`](./../afc/AComponent.md)



<br/>

## Class Variables

<br/>

## Instance Variables

### canvas \<HTMLCanvasElement>

캔버스 엘리먼트 객체

<br/>

### ctx \<CanvasRenderingContext2D>

캔버스의 드로잉 컨텍스트

<br/>

### data \<Array>

드로잉 데이터

<br/>

### pos \<Object>

드로잉 포지션 객체

<br/>

### eleW \<Number>

캔버스를 감싸고 있는 element 너비

<br/>

### eleH \<Number>

캔버스를 감싸고 있는 element 높이

<br/>

### compLeft \<Number>

element의 left 위치 값

<br/>

### middleX \<Number>

element의 middle X 값

<br/>

### colorObj \<Object>

차트가 필요한 컬러 정보. 상속받는 차트가 필요한 컬러 정보를 셋팅해야 함

<br/>

### decimalExp \<Number>

실수 데이터를 표현할 때 소수점 아래 자리 수

<br/>
<br/>

## Class Methods

<br/>

## Instance Methods

### setColors( colors, isDraw )

차트 색상을 colorObj 에 세팅한다.

* `colors` \<Object> 색상 정보
* `isDraw` \<Boolean> 다시 그리기 여부

<br/>

### updatePositon(pWidth, pHeight)

캔버스 포지션을 변경한다.(각 차트들이 재구현 해야함)

* `pWidth` \<Number> 부모뷰의 넓이
* `pHeight` \<Number> 부모뷰의 높이

<br/>

### updateGraph()

정보 갱신후 차트를 update함(각 차트들이 재구현 해야함)

<br/>

### resetDraw()

차트 드로우 리셋(각 차트들이 재구현 해야함)

<br/>

### draw()

차트 드로우(각 차트들이 재구현 해야함)

<br/>

### setDecimal( exp )

실수 데이터를 표현할 때 소수점 아래 자리 수를 지정한다.

* `exp` \<Number> 소수점 아래 자리수

<br/>