# CompareChart
> **Extends**: [`BaseChart`](./BaseChart.md)



<br/>

## Properties

### frwName \<String>

프레임워크 이름 저장 변수

- `default` "stock"

<br/>

### isCandleChart  \<Boolean>

CandleChart 인지 여부 (true / false)

<br/>

### lineData \<Array>

비교할 데이터를 저장하는 배열

<br/>

### lineDataText \<Array>

비교할 데이터를 지칭하는 문자열을 저장하는 배열

<br/>

### lineDataColor \<Array>

> StockColor.js 의 StockColor.COMPARE_COLORS 참고

비교할 데이터의 선의 색상을 저장하고 있는 배열

<br/>

### lineRate \<Array>

비교할 데이터 각각의 현재 표시되는 데이터의 최대값, 값 1당 화면에 표시할 수 있는 높이(표시할 수 있는 높이가 80이라고 했을때, 데이터의 최대값이 100이고 최소값이 50이면 값1당 높이는 1.6)을 저장하는 배열

<br/>

### delegator \<Object>

데이터의 인덱스상 끝에 다다른 경우 발생하는 추가 요청 이벤트를 받을 객체

<br/>

### preScale \<Number>

현재 차트가 그려진 scale 값

* `Default`: 1

<br/>

### rateVal \<Number>

차트의 확대 축소 값을 계산하기 위한 값

* `Default`: 1

<br/>

### zoomState \<Number>

줌 상태를 표현하는 값

<br/>

### lastDist \<Number>

줌 동작시 touch1, touch2 간의 거리

<br/>

### scollSX \<Number>

스크롤 시작 위치

<br/>

### speed \<Number>

스크롤 이동 속도

<br/>

### mStartTime \<Number>

이동 시간을 구할 때 사용

<br/>

### mOldTime \<Number>

이동 시간을 구할 때 사용

<br/>

### mStartX \<Number>

이동거리를 구할 때 시작 위치

<br/>

### mEndX \<Number>

이동거리를 구할 때 끝나는 위치

<br/>

### mScrollLR \<Boolean>

스크롤 이동 방향을 구분하는 값

<br/>

### timer \<Function>

자동 스크롤을 위한 setTimeout 함수의 리턴값인 id 를 저장하는 변수

<br/>

### startIdx \<Number>

현재 표현되고 있는 데이터의 시작 위치값

<br/>

### startLineX \<Number>

차트 데이터를 그리는 시작 X위치

<br/>

### endIdx \<Number>

현재 표시할 데이터의 끝 위치값

<br/>

### BAR_CNT \<Number>

기본값: 50

<br/>

### subType \<Number>

서브 그래프 타입 (0~6)

<br/>

### prdCls \<Number>

0: 월, 1: 주, 2: 일, 5: 분, 7: 틱

<br/>

### dateformatFunc \<Array>

prdCls 의 구분에 따른 datetime 표시 format

```js
this.dateformatFunc = 
[
    afc.formatDate,
    afc.formatDate,
    afc.formatMonth,
    null,
    null,
    afc.formatDateTime,
    null,
    afc.formatTic
];
```

<br/>

### dateformat \<String>

<br/>

### dashType \<Array>

```js
this.dashType = [1.5,4];
```

<br/>

### TEXT_SIZE \<String>

기본값: '16px'

<br/>

### defColorObj \<Object>

```js
this.defColorObj = 
{
    BACK : StockColor.BACK,
    TEXT : StockColor.TEXT,        			//일반 폰트색
    DOT : StockColor.DOT,          			//도트색
    DIVLINE : StockColor.DIVLINE,  			//상단 하단 그래프 구분선색
    UP : StockColor.UP_COLOR,    			//현재가 상승색
    DOWN : StockColor.DOWN_COLOR			//현재가 하락색	
};
```

<br/>

### colorObj \<Obejct>

```js
this.colorObj = 
{
    BACK : StockColor.BACK,
    TEXT : StockColor.TEXT,			//일반 폰트색
    DOT : StockColor.DOT,			//도트색
    DIVLINE : StockColor.DIVLINE,	//상단 하단 그래프 구분선색
    UP : StockColor.UP_COLOR,		//현재가 상승색
    DOWN : StockColor.DOWN_COLOR	//현재가 하락색	
};
```

<br/>

### COLOR_ARR \<Array>

상승하락 색상

```js
this.COLOR_ARR = [ this.colorObj.DOWN, this.colorObj.UP, this.colorObj.DOWN ];
```

<br/>

### touchEvent \<null>

<br/>

### isFirst \<Boolean>

데이터를 맨처음 불러오는지 여부

<br/>

### ROW_CNT \<Number>

금액 로우 간격 나누기 계산용 변수

기본값: 18

<br/>

### AM_R_WIDTH \<Number>

상단, 하단 오른쪽 금액영역 너비

기본값: 100

<br/>

### AM_L_WIDTH \<Number>

상단, 하단 오니쪽 금액영역 너비

기본값: 0

<br/>

### MAX_BAR_W \<Number>

최대 봉 너비

기본값: 80

<br/>

### DEF_BAR_W \<Number>

기본 봉 너비

기본값: 8

<br/>

### BAR_TERM \<Number>

봉차트간 간격

기본값: 1

<br/>

### SIGAIDX \<Number>

시가인덱스

기본값: 1

<br/>

### GOGAIDX \<Number>

고가인덱스

기본값: 2

<br/>

### JEOGAIDX \<Number>

저가 인덱스

기본값: 3

<br/>

### JONGGAIDX \<Number>

종가 인덱스

기본값: 4

<br/>

### DEALQTIDX \<Number>

체결량 인덱스

기본값: 5

<br/>

### upGrpMaxAm \<Number>

상단 그래프 최대값

<br/>

### upGrpMinAm \<Number>

상단 그래프 최소값

<br/>

### pos \<Object>

포지션 관련된 객체

```js
this.pos = 
{     
    cavasW: 0,   //전체 캔버스 너비
    cavasH: 0,   //전체 캔버스 높이
    grpW: 0,     //상단,하단 그래프영역 너비
    grpEX: 0,    //상단,하단 그래프영역 끝 X좌표
    dtXs: [],    //상단,하단 그래프 세로구분 X좌표 배열 [1, 2, 3번째]
    amYs: [],    //상단 그래프 금액 구분선 Y좌표 배열[금액1, 금액2, 금액3, 금액4, 금액5]
    amPad: 0,    //금액 오른쪽 정렬시 마진
    txtY: 0,     //텍스트 세로 중간 정렬을 위한 Y위치  
    
    upGrpSY: 0,  //상단 그래프 시작 Y좌표
    upDtY: 0,    //상단 그래프 Date 영역 Y
    upGrpEY: 0,  //상단 그래프 끝 Y좌표
    upGrpH: 0,   //상단 그래프 그리는 영역 높이
    dwDtY: 0,    //하단 그래프 Date 영역 Y
    
    upRateH:  0, //상단 높이 비율
    
    barW: this.DEF_BAR_W, //봉차트 너비
    
    barTot: 0    //봉차트 너비에 봉과 봉사이의 간격을 더한값(한봉이 그려지는 영역)
}; 
```

<br/>

## Method

### extractColorObj()

차트 색상정보를 추출한다.

<br/>

### initEvent()

추후 setTouchEvent에서 touchEvent option 에 따라서 이벤트 처리하게 수정한다.

<br/>

### updatePosition( pWidth, pHeight )

그래프의 너비 및 높이를 업데이트한다.

- `pWidth` \<String> or \<Number> 변경할 그래프의 너비
- `pHeight` \<String> or \<Number> 변경할 그래프의 높이

<br/>

### setZoomEvent()

mouseup 또는 touchend 이벤트에 대한 이벤트 핸들러 함수를 zoomIn, zoomOut 버튼에 연결한다.

<br/>

### setDelegator( delegator )

Delegator 셋팅, 데이터를 더 필요로 할 때 이벤트를 날려준다.

- `delegator` \<Object> 이벤트 수신할 객체

<br/>

### calcPosition( elWidth, elHeight )

컴포넌트의 너비와 높이값을 이용하여 canvas 에 들어갈 영역 x, y 설정한다.

- `elWidth` \<String> or \<Number> 설정할 요소의 너비
- `elHeight` \<String> or \<Number> 설정할 요소의 높이

<br/>

### addCompareData( compareData )

비교할 데이터를 추가한다.

- `compareData` \<Array> [표시할 문자열, 데이터]

<br/>

### ( dataArr, keyArr )

데이터 설정한다.

- `dataArr` \<Array>
- `keyArr` \<Array>

```js
this.chart.setData([], []);
```

<br/>

### setIsFirst( isFirst )

맨 처음 데이터를 불러오는지 여부를 설정한다.

- `isFirst` \<boolean> 

<br/>

### getIsFirst()

맨 처음 데이터를 불러오지는 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### setPrdCls( prdCls )

일자 또는 시간일 경우에 따른 표현 포멧함수를 설정한다.

- `prdCls` \<Number> 0(월), 1(주), 2(일), 5(분), 7(틱)

<br/>

### resetData()

차트 드로잉데이터를 초기화한다.

<br/>

### draw()

차트 드로우 함수 모음

<br/>

### drawBackLine()

백그라운드 기본 라인을 그린다.

<br/>

### drawBackText()

상태에 따른 백그라운드 고정 텍스트를 그린다.

<br/>

### setMaxMin()

상하단 그래프 최대최소 값을 설정한다.

<br/>

### drawGraph()

그래프를 그리는 함수

<br/>

### drawCompareLine()

비교할 라인 선을 그린다.

<br/>

### isExistNextData()

데이터가 더 필요한지 확인한다.

- **Returns** \<Boolean>

<br/>

### getOffset()

현재 그리는 데이터 오프셋을 가져온다.

<br/>

### barWidthChange()

캔들의 너비와 캔들 간의 공백 넓이로 캔들 개수를 바꾼다.

<br/>

### scrollLToR( add )

왼쪽에서 오른쪽으로 스크롤 한다.

- `add` \<Number>

<br/>

### scrollRToL( add )

오른쪽에서 왼쪽으로 스크롤 한다.

- `add` \<Number>

<br/>

### updateGraph()

그래프를 업데이트한다.

<br/>

### zoomInOut()

줌 인아웃 하는 함수

<br/>

### drawLongTabData( touchX )

롱탭시 보여지는 상세 데이터를 표시한다.

- `touchX` \<Number>

<br/>

### autoScroll( speed )

자동스크롤을 설정한다.

* `speed` \<Number> 자동스크롤 속도

<br/>

### setTouchEvent()

스크롤 또는 롱탭 감지를 위해 이벤트를 등록한다.

<br/>

### addNewData( dataArr, keyArr )

- `dataArr` \<Array>
- `keyArr` \<Array>

<br/>

### drawLongTabLines()

롱탭 시 보여질 안내선 및 상세 데이터를 표시한다.

<br/>

### makeChartCanvasData( dataArr, keyArr )

차트 그리는 원시데이터를 생성한다.

- `dataArr` \<Array>
- `keyArr` \<Array>

<br/>

### makeUpDownData()

상승하락 구분 배열 데이터를 생성한다.

<br/>

### getMappingCount()

매핑 가능한 개수를 반환한다.

* **Returns** \<Array> or \<Number>

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>