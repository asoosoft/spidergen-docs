# EXBong
> **Extends**: [`AComponent`](./../afc/AComponent.md)

봉차트

<br/>

## Class Variables

<br/>

## Instance Variables

### lineEl \<HTMLSpanElement>

봉의 중간 선 Dom element.
<br/>

### bongEl \<HTMLSpanElement>

봉 몸통 Dom element

<br/>

### upColor \<String>

봉 상승색

- `default` "#da2c03"

<br/>

### downColor \<String>

봉 하락색

- `default` "#75b02c"

<br/>

### steadColor \<String>

봉 보함색

- `default` "#dee0e9"

<br/>

### isUp \<Boolean>

봉 상승(true)/하락(false) 여부

<br/>

### isPort \<Boolean>

봉 가로(false)/세로(true) 여부

- `default` true

<br/>

### defColor \<String>

봉 기본색상

- `default` "transparent"

<br/>

### si \<Number>

시가를 저장하는 변수

<br/>

### go \<Number>

고가를 저장하는 변수

<br/>

### je \<Number>

저가를 저장하는 변수

<br/>

### jo \<Number>

종가를 저장하는 변수

<br/>

### prdyvrss \<Number>

대비를 저장하는 변수

<br/>
<br/>

## Instance Methods

### init()

컴포넌트를 초기화한다.

<br/>

### initPos()

방향에 따라서 몸통과 선의 위치와 크기를 초기화한다. init에서 호출

<br/>

### setDirection( isPort )

봉 가로/세로 여부를 셋팅한다.

* `isPort` \<Boolean> 가로(false)/세로(true) 여부

<br/>

### setUpColor( color )

봉 상승 색상을 셋팅한다.

* `color` \<String> 상승색 ex) "#ff0000" or "rgba(255,0,0,1)"

<br/>

### setDownColor( color )

봉 하락 색상을 셋팅한다.

* `color` \<String> 하락색 ex) "#0000ff" or "rgba(0,0,255,1)"

<br/>

### setSteadyColor( color )

봉 보합 색상을 셋팅한다.

* `color` \<String> 보합색 ex) "#000000" or "rgba(0,0,0,1)"

<br/>

### setColor( color )

봉의 몸통과 선에 색상을 셋팅한다.

* `color` \<String> 봉색 ex) "#999999" or "rgba(0,0,0,1)"

<br/>

### resetData()

봉에 적용된 데이터를 초기화한다.

<br/>

### setData( valueArr, prdyvrss )

봉에 데이터를 셋팅한다.

* `valueArr` \<Array> [시가, 고가, 저가, 종가] ex) [1000, 3000, 900, 2000]
* `prdyvrss` \<Number> prdyvrss

```js
this.setData([25, 100, 0, 75]);
```
<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getMappingCount()

매핑가능한 개수를 리턴한다.

* **Returns** \<Number> or \<Array> ex. ["Open", "High", "Low", "Close", "Color"]

<br/>
<br/>
