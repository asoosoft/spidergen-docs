# EXJisooChart
> **Extends** [`BaseChart`](./BaseChart.md)

지수를 표현하는 차트

<br/>

## Properties

### delegator \<Object>

데이터의 인덱스상 끝에 다다른 경우 발생하는 추가 요청 이벤트를 받을 객체

<br/>

### divisionVal \<Number>

지수차트 데이터를 나눗셈할 값

<br/>

### preScale \<Number>

현재 차트가 그려진 scale 값

* `default` 1

<br/>

### rateVal \<Number>

차트의 확대 축소 값을 계산하기 위한 값

* `default` 1

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

<!-- ### speed \<Number> -->

<!-- 스크롤 이동 속도 -->

<!-- <br/> -->

### mStartTime \<Number>

터치를 시작한 시간. 스크롤 이동 속도를 구하는데 사용된다.

<br/>

### mOldTime \<Number>

터치를 끝낸 시간

<br/>

### mStartX \<Number>

터치를 시작한 X좌표

<br/>

### mEndX \<Number>

터치를 끝낸 X좌표

<br/>

### mScrollLR \<Boolean>

스크롤 이동 시 방향을 구분하는 값

<br/>

### timer \<Number>

autoScroll 호출 시 setTimeout 의 리턴값인 timeoutID 를 저장하는 변수

<br/>

### startIdx \<Number>

현재 표현되고 있는 데이터의 시작 위치값

<br/>

### startLineX \<Number>

값이 표현되는 영역이 아닌 차트만 표현되는 영역의 시작 X좌표

<br/>

### endIdx \<Number>

현재 표현되고 있는 데이터의 끝 위치값

<br/>

### BAR_CNT \<Number>

현재 표현되고 있는 데이터의 갯수

<br/>

### prdCls \<Number> ( 0:월, 1:주, 2:일, 5:분, 7:틱 )

dateformat 구분값

<br/>

### dateformatFunc \<Function Array>

시간, 날짜 표시 함수를 저장하고 있는 배열

<br/>

### dateformat \<Function>

datetime 표시 형식

[dateformatFunc](#dateformatFunc) 목록 중 [prdCls](#prdCls-<Number>-\(-0:월,-1:주,-2:일,-5:분,-7:틱-\)) 구분값에 따라 시간, 날짜 표시 함수를 저장한다.

<br/>

### dashType \<Array>

차트 영역의 가로와 세로의 구분선을 그릴 때 사용되는 대시배열

<br/>

### TEXT_SIZE \<Number>

텍스트 사이즈

<br/>


### colorObj \<Object>

컬러 정보 객체
```js
{
	BACK: StockColor.BACK, 
	TEXT: StockColor.TEXT,
	DOT: StockColor.DOT,
	DIVLINE: StockColor.DIVLINE,
	LINE: StockColor.LINE,
	START: StockColor.START,
	END: StockColor.END
}
```

<br/>

### ROW_CNT \<Number>

금액 로우 간격 나누기 계산용 변수 

* `default` 14

<br/>

### AM_R_WIDTH \<Number>

상단,하단 오른쪽 금액영역 너비

* `default` 100

<br/>

### AM_L_WIDTH \<Number>

상단,하단 왼쪽 금액영역 너비

* `default` 0

<br/>

### MAX_BAR_W \<Number>

최대로 확대할 수 있는 봉의 너비

* `default` 80

<br/>

### DEF_BAR_W \<Number>

기본 봉 너비

* `default` 8

<br/>

### BAR_TERM \<Number>

봉차트간 간격

* `default` 0

<br/>

### upGrpMaxAm \<Number>

상단 차트 최대값

* `default` 0

<br/>

### upGrpMinAm \<Number>

상단 차트 최소값

* `default` 0

<br/>

### pos \<Object>

위치, 크기 관련된 정보를 저장하는 객체
```js
{ 
	cavasW: 0,          //전체 캔버스 너비
	cavasH: 0,          //전체 캔버스 높이
	grpW: 0,            //상단,하단 그래프영역 너비
	grpEX: 0,           //상단,하단 그래프영역 끝 X좌표
	dtXs: [],           //상단,하단 그래프 세로구분 X좌표 배열 [1, 2, 3번째]
	amYs: [],           //상단 그래프 금액 구분선 Y좌표 배열[금액1, 금액2, 금액3, 금액4, 금액5]
	amPad: 0,           //금액 오른쪽 정렬시 마진
	txtY: 0,            //텍스트 세로 중간 정렬을 위한 Y위치  

	upGrpSY: 0,         //상단 그래프 시작 Y좌표
	upDtY: 0,           //상단 그래프 Date 영역 Y
	upGrpEY: 0,         //상단 그래프 끝 Y좌표
	upGrpH: 0,          //상단 그래프 그리는 영역 높이

	upRateH:  0,        //상단 높이 비율

	barW: this.DEF_BAR_W, //봉차트 너비

	barTot: 0           //봉차트 너비에 봉과 봉사이의 간격을 더한값(한봉이 그려지는 영역)
};
```
<br/>

### compLeft \<Number>

엘리먼트의 Left 지점

<br/>

### middleX \<Number>

엘리먼트의 중간X 지점

<br/>
<br/>

## Methods

### drawGraph()

지수차트를 그린다.

<br/>

### resetData()

지수차트 데이터를 초기화한다.

<br/>

### setColors( colors )

지수차트의 색상을 셋팅한다.

* `colors` \<Object>

			색상객체
			TEXT: '#FFFFFF', //폰트색
			DOT: '#5d5d5d', //도트색
			LINE: '#F82008', //라인색
			START: '#00ff00', //그라디언트 시작색
			END: 'rgba(0, 250, 0, 0.0)' //그라디언트 끝색

<br/>

### setData( data )

지수차트 데이터를 셋팅한다.

* `data` \<Array> [[일시, 시가, 고가, 저가, 종가, 누적거래량, 누적거래 대금],...]

<br/>

### setDelegator( delegator )

delegator를 셋팅한다.

* `delegator` \<Object> 이벤트를 받을 객체

<br/>

### setDivisionVal( divisionVal )

지수차트 데이터를 나눗셈할 값을 셋팅한다.

* `divisionVal` \<Number> 나눗셈할 값

<br/>

### setTitle( title )

지수차트 타이틀 문구를 셋팅한다.

* `title` \<String> 타이틀 문구

<br/>

### init()

해당 차트 구성요소를 초기화하고 이벤트 초기화를 실행한다.

* `context` \<String> 컴포넌트 생성 및 초기화 정보
* `evtListener` \<String> context 에 매핑된 이벤트 수신자
\
<br/>

### initEvent()

터치이벤트와 줌이벤트를 셋팅한다.



<br/>

### updatePosition( pWidth, pHeight )

차트의 너비 및 높이를 업데이트한다.

* `pWidth` \<Number> 업데이트 할 너비
* `pHeight` \<Number> 업데이트 할 높이

<br/>

### setZoomEvent()

줌 이벤트를 셋팅한다. 확대 축소 비율은 점점 커진다.


<br/>

### getTitle()

차트 제목을 반환한다.

* **Returns** \<String>


<br/>

### calcPosition( elWidth, elHeight )

컴포넌트의 너비와 높이값을 이용하여 canvas에 들어갈 영역 x, y값을 셋팅한다.

* `elWidth` \<Number> 컴포넌트 너비
* `elHeight` \<Number> 컴포넌트 높이

<br/>

### setIsFirst( isFirst )

맨처음 데이터 호출 여부를 셋팅한다.

* `isFirst` \<Boolean> 호출 여부


<br/>

### getIsFirst()

맨처음 데이터인지 아닌지를 리턴한다.(true: 맨처음 데이터 / false: 추가된 데이터)

* **Returns** \<Boolean>

<br/>

### setPrdCls( prdCls )

일자 또는 시간일 경우에 따른 표현 포멧 함수를 셋팅한다.

* **prdCls** \<Number> 포멧 함수(dateformatFunc) 인덱스

<br/>

### setMaxMin()

차트 상단, 하단 최대최소 값과 높이 비율 값을 구한다.


<br/>

### draw()

지수차트 전체를 새로 그린다.

<br/>

### drawBackLine()

백그라운드 기본 라인을 그린다.

<br/>

### setBackLineColor(color, isRefresh)

백그라운드 컬러를 셋팅한다.

* `color` \<String> 백그라운드 컬러
* `isRefresh` \<Boolean> 새로고침 여부

<br/>

### setTextColor()

텍스트 컬러를 셋팅한다.

* `color` \<String> 백그라운드 컬러
* `isRefresh` \<Boolean> 새로고침 여부

<br/>

### setUpColor()

상승 컬러를 셋팅한다.

* `color` \<String> 백그라운드 컬러
* `isRefresh` \<Boolean> 새로고침 여부


<br/>

### setDownColor()

하락 컬러를 셋팅한다.

* `color` \<String> 백그라운드 컬러
* `isRefresh` \<Boolean> 새로고침 여부



<br/>

### isExistNextData()

데이터가 더 필요한지 체크한다.

* **Returns** \<Boolean>

<br/>

### getOffset()

현재 그리는 데이터 오프셋을 가져온다.


<br/>

### barWidthChange()

바의 너비를 바꾼다.


<br/>

### scrollLToR()

왼쪽에서 오른쪽으로 스크롤을 실행한다.

<br/>

### scrollRToL()

오른쪽에서 왼쪽으로 스크롤을 실행한다.

<br/>

### updateGraph()

현재 데이터로 차트를 갱신하여 표현한다.

<br/>

### zoomInOut()

계산된 rateVal에 따라 줌인, 줌아웃을 동작을 실행한다.

<br/>

### drawLongTabData(touchX)

롱탭시 안내선을 보여준다.

* `touchX` \<Number> 롱탭시 해당 터치 X좌표

<br/>

### autoScroll(speed)

자동스크롤을 설정한다.

* `speed` \<Number> 자동스크롤 속도

<br/>

### setTouchEvent()

스크롤 또는 롱탭 감지를 위해 이벤트를 등록한다.

<br/>

### addNewData(dataArr, keyArr)

새로운 차트 데이터를 추가한다.

* `dataArr` \<Array>  데이터 배열
* `keyArr` \<Array> 키 배열

<br/>

### drawLongTabLines()

롱탭한 위치의 X좌표, Y좌표를 가르키는 십자가모양의 선을 그린다.

<br/>

### setLongtabLineColor(color)

롱탭한 위치의 X좌표, Y좌표를 가르키는 십자가모양의 선의 색상을 지정한다.

* `color` \<String> 색상값

<br/>

### getLongtabLineColor()

롱탭한 위치의 X좌표, Y좌표를 가르키는 십자가모양의 선의 색상을 반환한다.

* **Returns** \<String> 

<br/>

### getMappingCount()

매핑가능한 개수를 리턴한다.

* **Returns** \<Array> 

<br/>

<!-- ### setQueryData() -->


<br/>
<br/>
