# AScrollBar
> **Extends** [`AComponent`](./AComponent.md)

스크롤바 컴포넌트

<br/>

## Class Variables

<br/>

## Instance Variables

### countPerArea \<Number>

한 영역에 보여질 데이터 개수

<br/>

### dataCount \<Number>

스크롤 영역에 표현되는 데이터의 개수

<br/>

### isScrollVert \<Boolean>

스크롤바가 세로방향인지 가로방향인지 여부

* `Default` `true`

<br/>

### scrollGap \<Number>

하나의 데이터를 표현할 영역의 넓이. 보통 그리드에서 로우

<br/>

### scrollPadding \<Number>

스크롤 영역에서 제외할 상단 영역. 보통 그리드에서 헤더

<br/>

### $cntLo \<jQueryObject>

컨텐츠의 가상영역 1

<br/>

### $cntHi \<jQueryObject>

컨텐츠의 가상영역 2, 브라우저에 따라 1개로 데이터 개수를 모두 표현하지 못하므로 사용

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### addDataCount( count )

스크롤 영역에 표현되는 데이터의 개수를 가감한다.

* `count` \<Number> 가감할 수

<br/>

### addWheelArea( wheelArea )

휠 이벤트를 등록할 영역을 셋팅한다. 휠 이벤트 발생시 스크롤 바를 이동시킨다.

* `wheelArea` \<HTMLElement> 스크롤 바 이동시킬 엘리먼트

<br/>

### getCountPerArea()

한 영역에서 데이터가 표현되는 개수를 가져온다.

* **Returns** \<Number> 표현 개수

<br/>

### isScrollBottom()

스크롤바의 스크롤이 최하단에 위치했는지 여부를 가져온다.

* **Returns** \<Boolean> 최하단여부

<br/>

### isScrollLeft()

스크롤바의 스크롤이 좌측끝에 위치했는지 여부를 가져온다.

* **Returns** \<Boolean> 좌측 끝 여부

<br/>

### isScrollRight()

스크롤바의 스크롤이 우측끝에 위치했는지 여부를 가져온다.

* **Returns** \<Boolean> 우측 끝 여부

<br/>

### isScrollTop()

스크롤바의 스크롤이 최상단에 위치했는지 여부를 가져온다.

* **Returns** \<Boolean> 최상단여부

<br/>

### offsetBarPos( move )

스크롤바의 스크롤 영역을 이동시킨다.

* `move` \<Number> 스크롤 이동값

<br/>

### setDataCount( dataCount )

스크롤 영역에 표현되는 데이터의 개수를 세팅한다.

* `dataCount` \<Number> 데이터 개수

<br/>

### setScrollArea( scrlAreaHeight, scrollPadding, scrollGap, isBorder )

스크롤바가 표현해야할 스크롤 영역을 세팅한다.

* `scrlAreaHeight` \<Number> 스크롤 영역의 높이
* `scrollPadding` \<Number> 스크롤 영역에서 제외할 상단 영역. 보통 그리드에서 헤더
* `scrollGap` \<Number> 하나의 데이터를 표현할 영역의 넓이. 보통 그리드에서 로우
* `isBorder` \<Boolean>> 테두리 존재유무

```js
var scrlAreaHeight = grid.scrollArea.height(),
    scrollPadding = grid.hRowTmplHeight,
    scrollGap = grid.rowTmplHeight;

scrollBarV.addWheelArea(grid.element);
scrollBarV.setScrollArea(scrlAreaHeight, scrollPadding, scrollGap, true);
```

<br/>

### setScrollType( type )

스크롤바의 방향을 정한다.

* `type` \<String> 스크롤바 방향 "vert | hori"

<br/>
