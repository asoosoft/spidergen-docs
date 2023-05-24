# ChartView
> **Extends**: [AView]



<br/>

## Properties

### frwName \<String>

기본값: 'stock'

<br/>

### delegator \<Object>

<br/>

### item \<Array>

<br/>

### isMultiChart \<Boolean>

<br/>

### selectBtn \<AComponent>

<br/>

### isInit \<Boolean>

<br/>

### sendItemArr \<Array>

<br/>

### isSending \<Boolean>

<br/>

### realQueryName \<String>

<br/>

### noSend \<Boolean>

<br/>

### noReal \<Boolean>

<br/>

### term \<Number>

분틱주기값

<br/>

### termMap \<Object>

```js
this.termMap = 
{
    '일': 1,
    '주': 2,
    '월': 3,
    '년': 5
};
```

<br/>

### termMap2 \<Object>

```js
this.termMap2 = 
{
    '1': '일',
    '2': '주',
    '3': '월',
    '5': '년'
};
```

<br/>

### termBtn \<AButton>

'일, 주, 월, 년' 을 주기로 조회하도록 설정하는 버튼

<br/>

### minBtn \<AButton>

'분' 을 주기로 조회하도록 설정하는 버튼

<br/>

### tickBtn \<AButton>

'초(틱)' 를 주기로 조회하도록 설정하는 버튼

<br/>

### termBtn2 \<AButton>

유동적인 주기(일, 분, 틱)로 조회하도록 설정하는 버튼

<br/>

### tickBtn2 \<AButton>

<br/>

### win \<AWindow>

<br/>

### beforeOptions \<Object>

변경하기 전 차트의 옵션 값

<br/>

### afterOptions \<Object>

변경한 후 차트의 옵션 값

<br/>

### chartConfig \<Object>

차트의 설정값

```js
this.chartConfig =
{
    useAdPrice: 0,
    minList: ['1:1','1:3','1:5','1:10','1:15','1:30','1:45','1:60'],
    tickList: ['1:1','1:3','1:5','1:10','1:20','1:30','1:60','1:120'],
    lastValue : [0,1],	//[type, termval]
    limitCnt: 200
};
```

<br/>

### searchType \<Number>

일주년월(0), 분(1), 틱(2)

<br/>

### nextKey \<Number>

<br/>

### nextDate \<String>

<br/>

### realData \<Object>

리얼 데이터 저장 목적 변수

<br/>

### mainKeyInfo \<Object>

아이템 구분을 위한 key 정보

<br/>

### itemBoxView \<AView>

메뉴 아이템을 담기 위한 View

<br/>

## Method

### isFIndex( item )

해외지수인지 확인한다.

- `item` \<Array>
- **Returns** \<Boolean>

<br/>

### setDelegator( delegator )

Delegator 셋팅, 데이터를 더 필요로 할 때 이벤트를 날려준다.

- `delegator` \<Object>

<br/>

### setRealQueryName( qryName )

차트의 리얼쿼리네임을 변경시킨다

- `qryName` \<Object>

<br/>

### setItemInfo( itemArr )

차트에 적용할 단축코드 및 시장분류코드, 종목명을 설정한다.


- `itemArr` \<Array> 

0번째 인덱스 단축코드, 1번째 인덱스 시장분류코드, 2번째 인덱스 종목명이 각각 들어있다.

<br/>

### updatePosition( width, height )

가로모드, 세로모드 일 경우 차트 사이즈를 변경한다.

- `width` \<String> or \<Number> 변경할 차트의 너비
- `height` \<String> or \<Number> 변경할 차트의 높이

<br/>

### setSearchType( type, term )

차트의 검색 타입을 설정한다.

- `type` \<Number> 0: 일주월, 1: 분, 2: 틱, 3: 해외지수
- `term` \<Number> 분틱 주기값

<br/>

### getSearchType()

차트의 검색타입을 반환한다.

- **Returns** \<Array>

<br/>

### onIndicatorSignalList( chartId, selectedDate, jsonData )

차트에서 실행되는 지표 데이터를 조회한다.

- `chartId` \<String> 적용할 ChartId
- `selectedDate` \<String> 선택된 날짜
- `jsonData` \<String> 선택된 항목의 데이터

<br/>

### onSignalDateChange( chartId, selectedDate )

시그널 차트에서 선택된 날짜를 받는다.

- `chartId` \<String> 적용할 ChartId
- `selectedDate` \<String> 선택된 날짜

<br/>

### showChart()

차트를 보이게 한다.

<br/>

### hideChart()

차트를 숨긴다.

<br/>

### settingBtns( btnArr, itemBoxView )

일주월분틱 버튼이 있으면 이벤트를 설정한다.

- `btnArr` \<Array> 0: termBtn, 1: minBtn, 2: tickBtn
- `itemBoxView` \<AView> 

<br/>

### settingBtns2()

일주월분틱 버튼이 있으면 이벤트를 설정한다(버튼이 2개인 경우)

- `btnArr` \<Array> 0: termBtn2, 1: tickBtn
- `itemBoxView` \<AView> 

<br/>

### setViewDataCount( nViewNum )

차트 설정값에 차트데이터의 길이를 저장한다.

- `nViewNum` \<Number> 

<br/>

### showWin()

일주월분틱의 상세 주기를 선택하는 윈도우를 생성하여 호출한다.

<br/>

### onTermBtnClick( comp, info )

일주월버튼 클릭이벤트 함수

- `comp` \<AComponent> 컴포넌트 객체
- `info` \<null> null

<br/>

### onTermBtn2Click( comp, info )

일주월분틱 클릭이벤트 함수

- `comp` \<AComponent> 컴포넌트 객체
- `info` \<null> null

<br/>

### onMinBtnClick( comp, info )

분버튼 클릭이벤트 함수

- `comp` \<AComponent> 컴포넌트 객체
- `info` \<null> null

<br/>

### onTickBtnClick( comp, info )

틱버튼 클릭이벤트

- `comp` \<AComponent> 컴포넌트 객체
- `info` \<null> null

<br/>

### onTickBtn2Click( comp, info )

틱버튼 클릭이벤트2 (분, 틱)

- `comp` \<AComponent> 컴포넌트 객체
- `info` \<null> null

<br/>

### initConfig()

차트 설정값에 의해 검색조건을 설정한다.

<br/>

### setChartOption( beforeOptions, afterOptions )

차트의 옵션값을 설정한다

- `beforeOptions` \<Object> 변경 전 옵션 값
- `afterOptions` \<Object> 변경 후 옵션 값

<br/>

### loadChartConfig()

차트에 설정값을 로드하여 전역에 저장한다.

<br/>

### getChartConfig()

차트에 설정값을 반환한다.

- **Returns** \<Object> 전역에 저장된 chartConfig

<br/>

### setMoreData(isMore)

데이터를 계속 읽을지 말지를 결정한다.

- `isMore` \<Boolean> true / false

<br/>

### loadChartLayout()

네이티브에 차트영역 할당을 명령한다.

<br/>

### onChartInit()

네이티브 차트가 준비된 시점에 호출되는 이벤트

<br/>

### setFixedData(fixData)

네이티브 차트에 전송할 header 고정 데이터를 설정한다.

- `fixData` \<Object>

<br/>

### setSearchData(searchData)

네이티브 차트에 전송할 header 조회 데이터를 설정한다.

- `searchData` \<Object>

<br/>

### onGetPeriodInfo()

분틱시 선택할 수 있는 상세 숫자를 반환한다.

- **Returns** \<String>

<br/>

### openDlg(comp, dlgType)

다이얼로그를 띄운다.

- `comp` \<AComponent> 컴포넌트 객체
- `dlgType` \<String> 띄울 팝업의 종류

<br/>

### clearChart()

네이티브 차트를 클리어한다.

<br/>

### updateOutputData( tempData )

네이트 차트에 조회데이터를 업데이트한다.

- `tempData` \<Object> 업데이트 할 데이터

<br/>

### updateRealData()

네이티브 차트에 리얼데이터를 업데이트한다.

<br/>

### resetBtnState()

버튼(termBtn, minBtn, tickBtn, termBtn2)들을 초기화한다.

<br/>

### onRequestData( requestArr, selectedIndex )

저장한 차트를 불러와서 요청하는 경우 네이트 차트에서 데이터를 요청한다.

- `requestArr` \<Array>
- `selectedIndex` \<Number> 

<br/>

### requestData( requestArr, selectedIndex )

한건 한건의 데이터를 요청한다.

- `requestArr` \<Array> 0: 종목코드, 1: 종목명, 2: 시장구분, 3: 주기, 4: 분틱주기값
- `selectedIndex` \<Number>

<br/>

### sendDataManage()

리얼데이터를 받기위해서 전송하는 함수

<br/>

### onScrollEnd()

스크롤이 끝날 때 차트데이터를 더 요청하는 함수

### setDefaultAndMore( isMore )

초기화 및 연속여부를 설정한다.

- `isMore` \<Boolean> true(연속) / false(비연속)

<br/>

### sendChartData( isMore )

차트데이터를 요청한다

* `isMore` \<Boolean> 다음 데이터 조회 여부
```js

```

<br/>

### onChangePeriodOnStorage()
```js

```

<br/>

### onChangeAdjustedStock()

```js

```

<br/>

### setLastValue()
```js

```

<br/>

### unregisterReal()
```js

```

<br/>

### destroyChart()
```js

```

<br/>

### setAccrueName( arrResult )

투자자 차트 형태 설정

* `arrResult`:  \<Array> 투자자 차트 형태
```js

```

<br/>

### setAccrueData( arrResult )

투자자 차트 데이터 설정(스크립트에서 직접 밀어넣을때 사용)

* `arrResult`:  \<boolean> names + "=" + datas

```js

```

<br/>

### setShowCrossLine( arrResult )

십자선 표시

* `arrResult`:  \<Array> names + "=" + datas

```js

```

<br/>

### setTimeZone( arrResult )

타임존 설정 함수

* `arrResult`:  \<Array> 

```js

```

<br/>

### setDivideNum( params )

차트의 Multi Index 설정

```js

```

<br/>

### saveConfigInfo()

```js

```

<br/>

### setPeriod()





```js

```

<br/>

### setMarketCategory()





```js

```

<br/>

### onRequestMarketIndicatorName()





```js

```

<br/>

### func1()





```js

```

<br/>

### func2()





```js

```

<br/>

### func3()





```js

```

<br/>

### func4()





```js

```

<br/>

### func5()





```js

```

<br/>

### func6()





```js

```

<br/>

### func7()





```js

```

<br/>

### onWindowResult()





```js

```

<br/>

### landscape2portrait()





```js

```

<br/>

### portrait2landscape()





```js

```

<br/>

### onConfigViewPanalChange()





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

### getMappingCount()





```js

```

<br/>