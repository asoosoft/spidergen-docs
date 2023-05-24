# EXTriangle
> **Extends** [`AComponent`](./../afc/AComponent.md)

상한, 상승, 보합, 하한, 하락 대비부호를 표현하는 컴포넌트

<br/>

## Properties

### frwName \<String>

* `default` stock

<br/>

### dir \<Number>

방향에 대한 값(0:보합, 1:상한, 2:상승, 3:보합, 4:하한, 5:하락, 6:상승, 7:상승, 8:하락, 9:하락)

<br/>

<!-- ### arrowEl \<HTMLDivElement> -->

<!-- 대비부호 표현 삼각형 DOM Element -->

<!-- <br/> -->

<!-- ### arrowBodyEl \<HTMLDivElement> -->

<!-- 대비부호 표현 몸통 DOM Element -->

<!-- <br/> -->

<!-- 
### arrowH \<Number>

화살표 높이

<br/>

### headH \<Number>

헤드 높이

<br/>

### bodyH \<Number>

바디 높이

<br/> -->

## Instance Methods

### initPos()

부호를 화면에 표현하기 위한 높이, 넓이 등의 정보를 추출한다.

<br/>

### setUpDownColor( upColor, downColor )

상승, 하락 색상을 지정한다.

* `upColor` \<String> 상승색 "#ff0000"
* `downColor` \<String> 하락색 "#0000ff"

<br/>

### setDirection( dir )

대비부호 방향을 셋팅한다.

* `dir` \<Number> 대비부호 값 (0:보합, 1:상한, 2:상승, 3:보합, 4:하한, 5:하락)

<br/>

### getDirection()

대비부호 방향을 리턴한다.

* **Returns** \<Number> 대비부호 값 (0:보합, 1:상한, 2:상승, 3:보합, 4:하한, 5:하락)

<br/>

### setData( data )

데이터를 세팅한다. setDirection 함수를 호출한다.

* `data` \<Number> 대비부호 값 (0:보합, 1:상한, 2:상승, 3:보합, 4:하한, 5:하락)

<br/>

### getData()

데이터를 리턴한다. getDirection 함수를 호출한다.

* **Returns** \<Number> 대비부호 값 (0:보합, 1:상한, 2:상승, 3:보합, 4:하한, 5:하락)

<br/>

<!-- 
### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. dataArr은 AQueryData 특정부분의 참조자이다. <br><br> ※ 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
* `keyArr` \<Array> [ key1, key3, key10 ]
* `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### updatePosition()



<br/>

### getMappingCount()



<br/> -->
