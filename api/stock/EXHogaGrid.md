# EXHogaGrid
> **Extends**: [AGrid](../afc/AGrid.js)

호가를 표현하는 그리드. 형태는 아래와 같다.

1열 | 2열 | 3열
:--- | :---: | ---:
거래량 | 매수호가N | 빈공간
... | ... | ...
거래량 | 매수호가1 | 빈공간
빈공간 | 매도호가1 | 거래량
... | ... | ...
빈공간 | 매도호가N | 거래량

<br/>

## Properties

### frwName \<String>
stock

<br/>

### quoteCount \<Number>
호가 단계(5호가, 10호가)

<br/>

### rowLen \<Number>
호가가 적용된 로우의 개수

<br/>

### colLen \<Number>
호가를 표현할 컬럼의 개수

<br/>

### btmRowCnt \<Number>
하단 데이터 영역의 로우 개수

<br/>

### basePrice \<Number>
호가의 색상을 구분하기 위한 기준가

<br/>

### basePriceKey \<String>
수신데이터에서 기준가를 가져오기 위한 키값

<br/>

### curPriceKey \<String>
수신데이터에서 현재가를 가져오기 위한 키값

<br/>

### currentCell \<jQuery Object>
jQuery 현재가셀을 저장하는 변수

<br/>

### currentPrice \<Number>
현재가

<br/>

### curPriceStyleArr \<Array>
현재가를 선택하는 스타일 배열[상승색, 보합색, 하락색]

<br/>

### upColor \<String>

기본 상승색(기본값 StockColor.UP_COLOR)

<br/>

### downColor \<String>

기본 하락색(기본값 DOWN_COLOR.UP_COLOR)

<br/>

### steadyColor \<String>

기본 보합색(기본값 STEADY_COLOR.UP_COLOR)

<br/>

### barSize \<String>

매도, 매수 잔량을 표시하는 바 높이(기본값 70%)

<br/>

### valArr \<Array>

호가그리드의 데이터 값들을 저장하고 있는 2차원 배열. 그리드 형태와 동일

<br/>

### rateMode \<Boolean>

호가 우측에 등락률 표시여부(기본값 false)

<br/>

### rateClass \<String>

호가 우측에 등락률 표현 클래스명

<br/>

### rateStyle \<String>

호가 우측에 등락률 표현 스타일 문자

<br/>

## Instance Method

### init()



<br/>

### clearContents()



<br/>

### resetGrid()



<br/>

### setBasePrice( basePrice )

기준가를 설정한다.

* `basePrice` \<Number>

<br/>

### setBasePriceKey( basePriceKey )

수신데이터에서 기준가를 뽑아올 키값을 설정한다.

* `basePriceKey` \<String>

<br/>

### setCurrentPrice( currentPrice )

현재가를 설정한다.

* `currentPrice` \<Number>

<br/>

### setCurPriceKey( keyName )

수신데이터에서 현재가를 뽑아올 키값을 설정한다.

* `keyName` \<String>

<br/>

### setUpColor( color )

호가 상승색을 설정한다.

* `color` \<String> #ff0000

<br/>

### setDownColor( color )

호가 하락색을 설정한다.

* `color` \<String> #0000ff

<br/>

### setSteadyColor( color )

호가 보합색을 설정한다.

* `color` \<String> #000000

<br/>

### getUpColor()

호가 상승색을 리턴한다.

* **Returns** \<String> #ff0000

<br/>

### getDownColor()

호가 하락색을 리턴한다.

* **Returns** \<String> #0000ff

<br/>

### getSteadyColor()

호가 보합색을 리턴한다.

* **Returns** \<String> #000000

<br/>

### setRateMode( enable )

호가 우측의 등락률 표현여부를 지정한다.

* `enable` \<Boolean> 

<br/>

### getRateMode()

호가 우측의 등락률 표현여부를 리턴한다.

* **Returns** \<Boolean>

<br/>

### selectCurrentCell( mapCell )

파라미터로 전달받은 셀을 현재가의 상승, 하락, 보합에 따라 셀에 클래스를 지정해준다.</br>
(호가가 현재가와 일치한 셀)

* `mapCell` \<HTMLTableCellElement> 호가와 현재가가 일치하는 셀 엘리먼트

<br/>

### setCurrentPriceStyleArr( styleArr )

현재가에 해당하는 셀에 추가할 상승, 하락, 보합의 클래스 목록을 지정한다.

* `styleArr` \<Array> [상승클래스, 하락클래스, 보합클래스]

<br/>

### setDecimal( exp )

호가의 소수점 아래 자리수를 지정한다.

* `exp` \<Number> 소수점 아래 자리수

```js
this.hogaGrid.setDecimal(4);
```

<br/>

### decimalFunc()

호가그리드 전용 마스크 함수

값이 없는 경우 '' 리턴, 그 외 소수점 아래 자리수 표현 처리

<br/>

### initBar()

호가 잔량을 표현하는 바를 초기화한다.

<br/>

### setBarSize( barSize )

호가 잔량을 표현하는 바의 높이를 지정한다.

* `barSize` \<String> 바 높이

<br/>

### getBarSize()

호가 잔량을 표현하는 바의 높이를 리턴한다.

* **Returns** \<String> 바 높이

<br/>

### setAskBarBgImg( bgImage )

매도 잔량바의 Background-image를 지정한다.

* `bgImage` \<String>

<br/>

### getAskBarBgImg()

매도 잔량바의 Background-image를 리턴한다.

* **Returns** \<String>

<br/>

### setBidBarBgImg( bgImage )

매수 잔량바의 Background-image를 지정한다.

* `bgImage` \<String>

<br/>

### getBidBarBgImg()

매수 잔량바의 Background-image를 리턴한다.

* **Returns** \<String>

<br/>

### setAskBarPositionX( pos )

매도 잔량바의 시작 위치 x 값을 지정한다.

* `pos` \<String> background-position-x

<br/>

### getAskBarPositionX()

매도 잔량바의 시작 위치 x 값을 리턴한다.

* **Returns** \<String> background-position-x

<br/>

### setAskBarPositionY( pos )

매도 잔량바의 시작 위치 y 값을 지정한다.

* `pos` \<String> background-position-y

<br/>

### getAskBarPositionY()

매도 잔량바의 시작 위치 y 값을 리턴한다.

* **Returns** \<String> background-position-y

<br/>

### setBidBarPositionX( pos )

매수 잔량바의 시작 위치 x 값을 지정한다.

* `pos` \<String> background-position-x

<br/>

### getAskBarPositionX()

매수 잔량바의 시작 위치 x 값을 리턴한다.

* **Returns** \<String> background-position-x

<br/>

### setAskBarPositionY( pos )

매수 잔량바의 시작 위치 y 값을 지정한다.

* `pos` \<String> background-position-y

<br/>

### getAskBarPositionY()

매수 잔량바의 시작 위치 y 값을 리턴한다.

* **Returns** \<String> background-position-y

<br/>

### setBottomRowCount( btmRowCnt )

호가를 하단에 표현될 로우의 개수를 지정한다.

* `btmRowCnt` \<Number> 

<br/>

### getBottomRowCount()

호가를 하단에 표현된 로우의 개수를 리턴한다.

* **Returns** \<Number>

<br/>

### setQuoteCount( cnt )

호가의 단계를 지정한다. 5호가, 10호가 등

* `cnt` \<Number>

<br/>

### getQuoteCount()

호가의 단계를 리턴한다. 5호가, 10호가 등

* **Returns** \<Number>

<br/>

### setDelegator( delegator )

델리게이터를 지정한다. quoteCount, bottomRowCount가 변경될 때 델리게이터의 change 이벤트를 호출한다.

* `delegator` \<Object>

<br/>

### toggleRateMode()

호가 우측에 등락률를 표현한다. 만약 등략률이 표현되어 있으면 제거한다.

<br/>

<!--
### setRateTag( value, ele )

호가셀 우측에 등락률 값을 표현하는 rateClass와 rateStyle이 적용된 태그를 추가한다.

* `value` \<String> 해당 셀의 호가
* `ele` \<HTMLTableCellElement> 셀 엘리먼트

<br/>
-->

### setData( dataArr )

호가 관련 데이터를 그리드에 표현한다.

* `dataArr` \<Array> 호가 관련 데이터

```js
this.hogaGrid.setData([{
    ask_remain5: 1000,  ask_hoga5: 3000,
    ask_remain4: 2000,  ask_hoga4: 2900,
    ask_remain3: 3000,  ask_hoga3: 2800,
    ask_remain2: 4000,  ask_hoga2: 2700,
    ask_remain1: 5000,  ask_hoga1: 2600,
                        bid_hoga1: 2500, bid_remain1: 5000, 
                        bid_hoga2: 2400, bid_remain2: 4000,
                        bid_hoga3: 2300, bid_remain3: 3000, 
                        bid_hoga4: 2200, bid_remain4: 2000, 
                        bid_hoga5: 2100, bid_remain5: 1000, 
    cur_price: 2500,    base_price: 2300
}]);
this.hogaGrid.setData([[
    1000,   3000, '',
    2000,   2900,
    3000,   2800,
    4000,   2700,
    5000,   2600,
    '',     2500, 5000,
            2400, 4000, 
            2300, 3000, 
            2200, 2000, 
            2100, 1000
]]);
```

<br/>