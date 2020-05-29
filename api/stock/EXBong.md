# EXBong
> **Extends**: `AComponent`

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

봉 상승색 (기본값 : #da2c03)

<br/>

### downColor \<String>

봉 하락색 (기본값 : #75b02c)

<br/>

### steadColor \<String>

봉 보함색 (기본값 : #dee0e9)

<br/>

### isUp \<Boolean>

봉 상승(true)/하락(false) 여부 (기본값 : false)

<br/>

### isPort \<Boolean>

봉 가로(false)/세로(true) 여부 (기본값 : true)

<br/>

### defColor \<String>

봉 기본색상 (기본값 : transparent)

<br/>

### si \<Number>

시가

<br/>

### go \<Number>

고가

<br/>

### je \<Number>

저가

<br/>

### jo \<Number>

종가

<br/>

### prdyvrss \<Number>

대비

<br/>
<br/>

## Instance Methods

### init()
컴포넌트를 초기화합니다.

<br/>

### initPos()
방향에 따라서 몸통과 선의 위치와 크기를 초기화합니다. init에서 호출

<br/>

### setDirection( isPort )
봉 가로/세로 여부를 셋팅합니다.

* `isPort` \<Boolean> 가로(true)/세로(false) 여부

<br/>

### setUpColor( color )
봉 상승 색상을 셋팅합니다.

* `color` {String} 상승색 ex) '#999999' or 'rgba(255,0,0,1)'

<br/>

### setDownColor( color )

봉 하락 색상을 셋팅합니다.

* `color` {String} 하락색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>

### setSteadyColor( color )

봉 보합 색상을 셋팅합니다.

* `color` {String} 보합색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>

### setColor( color )
봉의 몸통과 선에 색상을 셋팅합니다.

* `color` \<String> 봉색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>

### resetData()
봉에 적용된 데이터를 초기화합니다.

<br/>

### setData( valueArr, prdyvrss )

봉에 데이터를 셋팅합니다.

* `valueArr` \<Array> [시가, 고가, 저가, 종가] ex) [1000, 3000, 900, 2000]
* `prdyvrss` \<Number> prdyvrss

```js
this.setData([25, 100, 0, 75]);
```
<br/>

### setQueryData()



```js

```

<br/>

### getQueryData()



```js

```

<br/>

### getMappingCount()

매핑가능한 개수를 리턴한다.

* **`return`** \<Number> or \<Array> ex. ['Open', 'High', 'Low', 'Close', 'Color']

<br/>
<br/>
