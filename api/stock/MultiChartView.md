# MultiChartView
> **Extends**: [ChartView](./ChartView.md)

--NOT USE

<br/>

## Properties

### frwName \<String>

<br/>

### selectedIndex \<Number>

현재 멀티차트 선택된 index

* `default` -1

<br/>

### firstItem \<>

0번째에 선택되어 있는 종목 저장

<br/>

### nextKeyArr \<>

종목별 각각의 넥스트키 저장 배열

<br/>

### nextDateArr \<>

종목별 각각의 넥스트날짜 저장 배열

<br/>

### realKeyArr \<>

리얼 키 저장 배열

<br/>

### tempIndex \<>

맨처음 조회시 index정보가 없을때 사용하는 임시 index변수

<br/>

### isDivideChart \<boolean>

차트 분할 여부

<br/>
<br/>

## Method

### loadChartLayout()

네이티브에 차트영역 할당을 명령한다.

<br/>

### setItemInfo( itemArr )

종목을 세팅하는 함수

* `itemArr` \<Array> 종목 정보 [ 단축코드, 종목명, 시장구분 ]

```js
this.multiChartView.setItemInfo(['005930', '삼성전자', 'KOSPI']);
```

<br/>

### setSearchType( type, term, btnUpdate )

차트의 검색타입을 설정(0:일주월,1:분,2:틱,3:해외지수)

* `type` \<Number> 검색 타입
* `term` \<String> 타입명
* `btnUpdate` \<Boolean> 버튼 업데이트 여부

<br/>

### makeRealKey( itemArr )

리얼키를 생성하여 리턴해주는 함수

* `itemArr` \<Array> 종목 정보 [ 단축코드, 종목명, 시장구분 ]

<br/>

### checkUnregisterReal()

특정 index의 종목이 변경 됐을시 체크하여 리얼해제

<br/>

### isExistRealKey( key )

현재 리얼맵에 리얼키가 존재하는지 확인

* `key` \<String> 리얼키

<br/>

### unregisterRealOne()



```js

```

<br/>

### unregisterReal()

멀티차트에 연결된 리얼데이터 해제

```js

```

<br/>

### setFixedData()

네이티브 차트에 전송할 header 고정 데이터 셋팅

```js

```

<br/>

### setSearchData()

네이티브 차트에 전송할 header 조회 데이터 셋팅

```js

```

<br/>

### updateOutputData()

네이티브 차트에 조회데이터를 업데이트하는 함수

```js

```

<br/>

### updateRealData()

네이티브 차트에 리얼 데이터를 업데이트하는 함수

```js

```

<br/>

### onRequestData()

네이티브 차트에서 데이터를 요청(저장된 차트를 불러와서 요청하는 경우)

```js

```

<br/>

### sendDataManage()

리얼데이터를 받기위해 전송하는 함수

```js

```

<br/>

### setDefaultAndMore()

초기화 및 연속 여부 셋팅

```js

```

<br/>

### onChangeAdjustedStock()

네이티브 차트에서 설정한 수정주가여부 적용함수

```js

```

<br/>

### sendChartData()



```js

```

<br/>

### onDivideChart()

차트 영역 개수가 변경됐을때 호출(맨 처음 시작시에도 호출)

```js

```

<br/>

### onSelectedChart()

멀티창에서 종목영역 하나를 선택했을 경우 오는 이벤트

```js

```

<br/>

### onRequestCodeControl()

종목을 선택하는 팝업 호출

```js

```

<br/>

### setData()



```js

```

<br/>

### setQueryData()



```js

```

<br/>

### onWindowResult()



```js

```

<br/>

### onConnSendQuery()



```js

```

<br/>