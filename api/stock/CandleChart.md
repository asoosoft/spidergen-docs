# CandleChart
> **Extends**: [`BaseChart`](./BaseChart.md)


<br/>

## Properties

### frwName \<String>

기본값: 'stock'

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

### upEndDegree \<Number>
기본값: 13

<br/>

### dotDegree \<Array>
기본값: [1, 4, 7, 10]

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

- `Default` 50

<br/>

### subType \<Number>

서브 그래프 타입 0~6 까지 <br/>
기본값: 0

<br/>

### prdCls \<Number>

0: 월, 1: 주, 2: 일, 5: 분, 7: 틱 <br/>
기본값: 0

<br/>

### dateformatFunc \<Array>

prdCls 구분에 따라서 날짜를 표시한다.

```js
this.dateformatFunc = [
    afc.formatMonth, afc.formatDate, afc.formatDate,
    null, null, afc.formatTime, null, afc.formatTime
];
```

<br/>

### dateformat \<Object>

dateformatFunc 에서 가져온 값

<br/>

### dashType \<Array>

기본값: [1.5, 4]

<br/>

### TEXT_SIZE \<String>

기본값: 16px

<br/>

### defColorObj \<Object>

기본 값은 다음과 같다.

```js
this.defColorObj = {
    BACK : StockColor.BACK,
    TEXT : StockColor.TEXT,			//일반 폰트색
    DOT : StockColor.DOT,			//도트색
    DIVLINE : StockColor.DIVLINE,	//상단 하단 그래프 구분선색
    UP : StockColor.UP_COLOR,		//현재가 봉상승색
    DOWN : StockColor.DOWN_COLOR,	//현재가 봉하락색
    UPBG : StockColor.LAST[1],		//현재가 글자배경 상승색
    DOWNBG : StockColor.LAST[2],	//현재가 글자배경 하락색
    UPTEXT : StockColor.TEXT_CURR,	//현재가 글자 상승색
    DOWNTEXT : StockColor.TEXT_CURR,//현재가 글자 하락색
    VOLUME : StockColor.VOLUME,		//거래량 막대그래프 색상
};
```

>StockColor.js 파일 참고

<br/>

### colorObj \<Object>

```js
기본 값은 다음과 같다.

this.defColorObj = {
    BACK : StockColor.BACK,
    TEXT : StockColor.TEXT,			//일반 폰트색
    DOT : StockColor.DOT,			//도트색
    DIVLINE : StockColor.DIVLINE,	//상단 하단 그래프 구분선색
    UP : StockColor.UP_COLOR,		//현재가 봉상승색
    DOWN : StockColor.DOWN_COLOR,	//현재가 봉하락색
    UPBG : StockColor.LAST[1],		//현재가 글자배경 상승색
    DOWNBG : StockColor.LAST[2],	//현재가 글자배경 하락색
    UPTEXT : StockColor.TEXT_CURR,	//현재가 글자 상승색
    DOWNTEXT : StockColor.TEXT_CURR,//현재가 글자 하락색
    VOLUME : StockColor.VOLUME,		//거래량 막대그래프 색상
};
```

>StockColor.js 파일 참고

<br/>

### maKeyArr \<Array>

기본값: new Array(5, 20, 60)

<br/>

### COLOR_ARR \<Array>

상승하락 색상

기본값: [colorObj.DOWN, colorObj.UP, colorObj.DOWN]

<br/>

### CURRENT_BGCOLOR_ARR \<Array>

마지막 종가 배경 색상

기본값: [colorObj.DOWNBG, colorObj.UPBG, colorObj.DOWNBG]

<br/>

### CURRENT_COLOR_ARR \<Array>

마지막 종가 글자 색상

기본값: [colorObj.DOWNTEXT, colorObj.UPTEXT, colorObj.DOWNTEXT]

<br/>

### COLOR_SET \<String>

텍스트 묶음

기본값: StockColor.SUB_COLORS[0]
>[StockColor.js] 참고

<br/>

### SUB_TEXT_SET \<Array>

```js
기본 값은 다음과 같다.

this.SUB_TEXT_SET =
[
    ['MA5', 'MA20', 'MA60'],
    ['OBV'],
    ['MACD(12,26)', 'Signal(9)'],
    ['Slow%K(5,3)', 'Slow%D(3)'],
    ['Fast K(5)', 'Fast D(3)'],
    ['이격도(10)'],
    ['RSI(12)', 'Signal']
];
```

<br/>

### SUB_COLOR_SET \<String>

기본값: StockColor.SUB_COLORS
>[StockColor.js] 참고

<br/>

### touchEvent \<Boolean>

<br/>

### isFirst \<Boolean>

<br/>

### ROW_CNT \<Number>

금액 로우 간격 나누기 계산용 변수

기본값: 20

<br/>

### AM_R_WIDTH \<Number>

상단, 하단 오른쪽 금액영역 너비

기본값: 100

<br/>

### AM_L_WIDTH \<Number>

상단, 하단 왼쪽 금액영역 너비

<br/>

### MAX_BAR_W \<Number>

최대 봉 너비

기본값: 80

<br/>

### DEF_BAR_W \<Number>

기본 봉 너비

기본값: 8

<br/>

### MIN_BAR_W \<Number>

최소 봉 너비

기본값: 8

<br/>

### BAR_TERM \<Number>

봉차트간 간격

<br/>

### SIGAIDX \<Number>

시가 인덱스

기본값: 1

<br/>

### GOGAIDX \<Number>

고가 인덱스

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

### dwGrpMaxAm \<Number>

하단 그래프 최대값

<br/>

### dwGrpMinAm \<Number>

하단 그래프 최소값

<br/>

### pos \<Object>

포지션에 관련된 객체

```js
기본 값은 다음과 같다.

this.pos =
{
    cavasW : 0,		//전체 캔버스 너비
    cavasH : 0,		//전체 캔버스 높이
    grpW : 0,		//상단,하단 그래프영역 너비
    grpEX : 0,		//상단,하단 그래프영역 끝 X좌표
    dtXs : [],		//상단,하단 그래프 세로구분 X좌표 배열 [1, 2, 3번째]
    amYs : [],		//상단 그래프 금액 구분선 Y좌표 배열[금액1, 금액2, 금액3, 금액4, 금액5]
    amPad : 0,		//금액 오른쪽 정렬시 마진
    txtY : 0,		//텍스트 세로 중간 정렬을 위한 Y위치

    upGrpSY : 0,	//상단 그래프 시작 Y좌표
    upDtY : 0,		//상단 그래프 Date 영역 Y
    upGrpEY : 0,	//상단 그래프 끝 Y좌표
    upGrpH : 0,		//상단 그래프 그리는 영역 높이
    kbnY : 0,		//상단,하단 그래프 구분Y
    dwGrpSY : 0,	//하단 그래프 시작 Y좌표
    dwDtY : 0,		//하단 그래프 Date 영역 Y
    dwGrpEY : 0,	//하단 그래프 끝 Y좌표
    dwGrpH : 0,		//하단 그래프 그리는 영역 높이

    dw80Y : 0,		//하단 80퍼센트 높이
    dw20Y : 0,		//하단 20퍼센트 높이

    upRateH : 0,	//상단 높이 비율
    dwRateH : 0,	//하단 높이 비율

    barW : this.DEF_BAR_W, //봉차트 너비

    barTot : 0		//봉차트 너비에 봉과 봉사이의 간격을 더한값(한봉이 그려지는 영역)
};
```

<br/>

### drawSubGrpFuncs \<Array>

```js
기본 값은 다음과 같다.

this.drawSubGrpFuncs = [
    [this.drawBackType0, this.drawTextType0, this.drawMaxMinType0, this.drawChartType0, this.calcMaxMinChartType0], 
    [this.drawBackType1, this.drawTextType1, this.drawMaxMinType1, this.drawChartType1, this.calcMaxMinChartType1], 
    [this.drawBackType2, this.drawTextType2, this.drawMaxMinType2, this.drawChartType2, this.calcMaxMinChartType2], 
    [this.drawBackType3, this.drawTextType3, this.drawMaxMinType3, this.drawChartType3, this.calcMaxMinChartType3], 
    [this.drawBackType4, this.drawTextType4, this.drawMaxMinType4, this.drawChartType4, this.calcMaxMinChartType4], 
    [this.drawBackType5, this.drawTextType5, this.drawMaxMinType5, this.drawChartType5, this.calcMaxMinChartType5], 
    [this.drawBackType6, this.drawTextType6, this.drawMaxMinType6, this.drawChartType6, this.calcMaxMinChartType6], 
    [this.drawBackType7, this.drawTextType7, this.drawMaxMinType7, this.drawChartType7, this.calcMaxMinChartType7]
];
```

<br/>

### drawBackType \<Function>

하단 7개 그래프 백그라운드 그리는 함수 저장 변수

```js
this.drawBackType = this.drawSubGrpFuncs[this.subType][0];
```

<br/>

### drawTextType \<Function>

하단 7개 그래프 금액 그리는 함수 저장 변수

```js
this.drawTextType = this.drawSubGrpFuncs[this.subType][1];
```

<br/>

### drawMaxMinType \<Function>

하단 7개 그래프 그리는 함수 저장 변수

```js
this.drawMaxMinType = this.drawSubGrpFuncs[this.subType][2];
```

<br/>

### drawChartType \<Function>


```js
this.drawMaxMinType = this.drawSubGrpFuncs[this.subType][3];
```

<br/>

### calcMaxMinChartType \<Function>

```js
this.drawMaxMinType = this.drawSubGrpFuncs[this.subType][4];
```

<br/>

### compLeft \<Number>

엘리먼트의 left 지점

<br/>

### middleX \<Number>

엘리먼트의 중간X 지점

<br/>

### currentTickCount \<Number>

틱인 경우에 리얼 수신시 개수 체크하는 변수

<br/>

### tickCount \<Number>

틱인 경우에 리얼 수신시 기준 틱개수

기본값: 1

<br/>

## Method



### extractColorObj()

차트 색상정보를 추출한다.

<br/>

### initEvent()

추후 setTouchEvent에서 touchEvent option 에 따라서 이벤트 처리하게 수정한다.

<br/>

### changeBtnStyle( inStyle, outStyle )

버튼 스타일 수정한다.

- `inStyle` \<String> 스타일 클래스 이름
- `outStyle` \<String> 스타일 클래스 이름

<br/>

### updatePosition( pWidth, pHeight )

그래프의 너비 및 높이를 업데이트한다.

- `pWidth` \<String> or \<Number> 변경할 그래프의 너비
- `pHeight` \<String> or \<Number> 변경할 그래프의 높이

<br/>

### setZoomEvent( inComp, outComp )

mouseup 또는 touchend 이벤트에 대한 이벤트 핸들러 함수를 zoomIn, zoomOut 버튼에 연결한다.

- `inComp` \<AComponent>
- `outComp` \<AComponent>

<br/>

### setDelegator( delegator )

Delegator 셋팅, 데이터를 더 필요로 할 때 이벤트를 날려준다.

- `delegator` \<Object> 이벤트 수신할 객체

<br/>

### setMAInfo( keyArr, colorArr )

이동 평균선 정보를 설정한다.

- `keyArr` \<Array>
- `colorArr` \<Array>

<br/>

### calcPosition( elWidth, elHeight )

컴포넌트의 너비와 높이값을 이용하여 canvas 에 들어갈 영역 x, y 설정한다.

- `elWidth` \<String> or \<Number> 설정할 요소의 너비
- `elHeight` \<String> or \<Number> 설정할 요소의 높이

<br/>

### reCalcWidth( cnt )

캔들개수로 캔들넓이를 계산한다.

- `cnt` \<Number>

<br/>

### setData( dataArr, keyArr )

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

### setSubGrpType( index, isRefresh )

하단의 서브 그래프 타입을 호출하여 그래프를 업데이트한다.

- `index` \<Number>
- `isRefresh` \<boolean> 

<br/>

### settingDrawSubGrp()

서브타입을 기준으로 서브 차트를 그리기위한 함수를 설정한다.

<br/>

### getData()

- **Returns** \<Array>

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

그래프 그리기

<br/>

### drawAvgLine( color, preLine, x, y )

차트에 이동평균선을 그린다.

- `color` \<Stirng>
- `preLine` \<Object>
- `x` \<Number>
- `y` \<Number>

<br/>

### drawSubLine( color, preLine, x, y )

차트에 하단 그래프 라인을 그린다.

- `color` \<Stirng>
- `preLine` \<Object>
- `x` \<Number>
- `y` \<Number>

<br/>

### setBackLineColor( color, isRefresh )

차트에 백그라운드 컬러를 설정한다.

- `color` \<String>
- `isRefresh` \<Boolean>

<br/>

### setTextColor( color, isRefresh )

차트에 텍스트 컬러를 설정한다.

- `color` \<String>
- `isRefresh` \<Boolean>

<br/>

### setUpColor( color, isRefresh )

차트에 상승 컬러를 설정한다.

- `color` \<String>
- `isRefresh` \<Boolean>

<br/>

### setDownColor( color, isRefresh )

차트에 하락 컬러를 설정한다.

- `color` \<String>
- `isRefresh` \<Boolean>

<br/>

### drawBackType0()

차트에 거래량그래프 도트선을 그린다.

<br/>

### drawTextType0()

거래량그래프의 배경텍스트를 그린다.

<br/>

### drawMaxMinType0()

거래량그래프의 최대최소 텍스트를 그린다.

<br/>

### drawChartType0()

거래량그래프를 그린다.

<br/>

### calcMaxMinChartType0()

거래량그래프 내 MAX 값과 MIN 값을 계산한다.

<br/>

### drawBackType1()

OBV 그래프의 도트선을 그린다.

<br/>

### drawTextType1()

OBV 그래프의 배경 텍스트를 그린다.

<br/>

### drawMaxMinType1()

OBV 그래프의 최대최소 텍스트를 그린다.

<br/>

### drawChartType1()

OBV 그래프를 그린다.

<br/>

### calcMaxMinChartType1()

OBV 그래프 내 MAX 값과 MIN 값을 계산한다.

<br/>

### drawBackType2()

MACD 그래프의 도트선을 그린다.

<br/>

### drawTextType2()

MACD 그래프의 배경 텍스트를 그린다.

<br/>

### drawMaxMinType2()

MACD 그래프의 최대최소 텍스트를 그린다.

<br/>

### drawChartType2()

MACD 그래프를 그린다.

<br/>

### calcMaxMinChartType2()

MACD 그래프 내 MAX 값과 MIN 값을 구한다.

<br/>

### drawBackType3()

Slow 그래프의 도트선을 그린다.

<br/>

### drawTextType3()

Slow 그래프의 배경 텍스트를 그린다.

<br/>

### drawMaxMinType3()

Slow 그래프의 최대최소 텍스트를 그린다.

<br/>

### drawChartType3()

Slow 그래프를 그린다.

<br/>

### calcMaxMinChartType3()

Slow 그래프 내 MAX 값과 MIN 값을 구한다.

<br/>

### setChartMode( mode, isRefresh )

- `mode` \<Number>
- `isRefresh` \<Boolean>

<br/>

### drawBackType4()

Fast 그래프의 도트선을 그린다.

<br/>

### drawTextType4()

Fast 그래프의 배경 텍스트를 그린다.

<br/>

### drawMaxMinType4()

Fast 그래프의 최대최소 텍스트를 그린다.

<br/>

### drawChartType4()

Fast 그래프를 그린다.

<br/>

### calcMaxMinChartType4()

Fast 그래프의 MAX 값과 MIN 값을 구한다.

<br/>

### drawBackType5()

이격도 그래프의 도트선을 그린다.

<br/>

### drawTextType5()

이격도 그래프의 배경 텍스트를 그린다.

<br/>

### drawMaxMinType5()

이격도 그래프의 최대최소 텍스트를 그린다.

<br/>

### drawChartType5()

이격도 그래프를 그린다.

<br/>

### calcMaxMinChartType5()

이격도 그래프의 MAX 값과 MIN 값을 구한다.

<br/>

### drawBackType6()

RSI 그래프의 도트선을 그린다.

<br/>

### drawTextType6()

RSI 그래프의 배경 텍스트를 그린다.

<br/>

### drawMaxMinType6()

RSI 그래프의 최대최소 텍스트를 그린다.

<br/>

### drawChartType6()

RSI 그래프를 그린다.

<br/>

### calcMaxMinChartType6()

RSI 그래프의 MAX 값과 MIN 값을 구한다.

<br/>

### drawBackType7()

EMPTY 그래프의 도트선을 그린다.

<br/>

### drawTextType7()

EMPTY 그래프의 배경 텍스트를 그린다.

<br/>

### drawMaxMinType7()

EMPTY 그래프의 최대최소 텍스트를 그린다.

<br/>

### drawChartType7()

EMPTY 그래프를 그린다.

<br/>

### calcMaxMinChartType7()

EMPTY 그래프의 MAX 값과 MIN 값을 구한다.

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

### setLongTabEvent()

롱탭 터치 이벤트 설정한다.

<br/>

### addNewData( dataArr, keyArr )

- `dataArr` \<Array>
- `keyArr` \<Array>

<br/>

### addRealData( dataArr, keyArr )

- `dataArr` \<Array>
- `keyArr` \<Array>

<br/>

### updateRealData( data, keyArr )

- `data` \<Array>
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

### makeMoveAvgData()

단순이동 평균 배열 데이터를 생성한다.

<br/>

### makeDptData()

이격도 배열 데이터를 생성한다.

<br/>

### makeMacdObvData()

MACD 지수이동평균 배열 데이터를 생성한다.

<br/>

### makeRSIData()

RSI 배열 데이터를 생성한다.

<br/>

### makeStochasticData()

Stock-Fast ~ Stock-Slow 배열 데이터를 생성한다.

<br/>

### setLongtabLineColor( color )

- `color` \<String>: #000000 형식으로 설정한다.

<br/>

### getLongtabLineColor()

설정한 롱탭 라인 색을 반환한다.

- **Returns** \<String> color 값 반환

### getMappingCount()

매핑 가능한 개수를 반환한다.

- **Returns** \<Array> length 로 개수 확인

<br/>

### getQueryData()

설정된 QueryData 리턴한다.

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>





