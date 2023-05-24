# EXCenterPivotView
> **Extends**: [`AView`](./../afc/AView.md)

<br/>

## Properties

### frwName \<String>

프레임워크 이름 저장 변수

- `default` "stock"

<br/>

### leftGrid \<[AGrid](./../afc/AGrid.md)>

좌측 그리드

<br/>

### pivotGrid \<[AGrid](./../afc/AGrid.md)>

중간 그리드

<br/>

### rightGrid \<[AGrid](./../afc/AGrid.md)>

우측 그리드

<br/>
<br/>

## Method

### scrollSyncSet( scrollGrid, scrollView )

그리드와 뷰 간에 스크롤이 동기화 될 수 있도록 세팅한다.

- `scrollGrid` \<[AGrid](./../afc/AGrid.md)>
- `scrollView` \<[AView](./../afc/AView.md)>


<br/>

### scrollViewLeft()

좌측 뷰의 스크롤 위치를 가장 오른쪽 끝으로 이동시킨다.

<br/>

### addRow( leftData, pivotData, rightData )

좌측, 중간, 우측 그리드에 로우를 추가한다.

AGrid 의 addRow 를 참조

* `leftData` \<Array> 좌측그리드에 추가할 데이터
* `pivotData` \<Array> 중간그리드에 추가할 데이터
* `rightData` \<Array> 우측그리드에 추가할 데이터

* **Returns** \<Array> 추가된 로우 배열 [left, center, right] 순서

```js
var rowArr = this.cPivotView.addRow([1,2,3], ['center'], ['4,5,6']);
//rowArr[0], rowArr[1], rowArr[2]
```

<br/>

### prependRow( leftData, pivotData, rightData )

좌측, 중간, 우측 그리드의 상단에 로우를 추가한다.

AGrid 의 prependRow 를 참조

* `leftData` \<Array> 좌측그리드에 추가할 데이터
* `pivotData` \<Array> 중간그리드에 추가할 데이터
* `rightData` \<Array> 우측그리드에 추가할 데이터

* **Returns** \<Array> 추가된 로우 배열 [left, center, right] 순서

```js
var rowArr = this.cPivotView.prependRow([1,2,3], ['center'], ['4,5,6']);
//rowArr[0], rowArr[1], rowArr[2]
```

<br/>

### addHelper( grid, data, isPrepend )



* `grid` \<[AGrid](./../afc/AGrid.md)> 추가할 그리드
* `data` \<Array> 데이터
* `isPrepend` \<Boolean> 상단추가여부

<br/>

### removeRow( rowIdx )

rowIdx 에 해당하는 로우를 그리드에서 제거한다.

* `rowIdx` \<Number>

<br/>

### removeAll()

그리드의 모든 row 를 제거한다.

<br/>

### setAllGridSelect()


<br/>

### scrollTo( pos )

전체 그리드의 scrollTop 을 pos 위치로 스크롤 시킨다.

* `pos` \<Number> 스크롤의 위치값

```js
cPivotView.scrollTo(0);
cPivotView.scrollTo(50);
```

<br/>

### scrollOffset( offset )

전체 그리드의 현재 scrollTop 위치에서 offset 만큼 스크롤 시킨다.

* `offset` \<Number> 스크롤시킬 값

```js
cPivotView.scrollOffset(100);
cPivotView.scrollOffset(-100)
```


<br/>

### scrollIntoArea( row, isAlignTop )

파라미터로 넘어온 rowIdx 에 해당하는 로우가 보이도록 스크롤 시킨다.

* `row` \<Number> 로우 인덱스
* `isAlignTop` \<Boolean> row를 상단으로 해서 보일지 여부(false 일 경우 하단)

```js
//특정 로우가 보이도록 스크롤 시킨다.
cPivotView.scrollIntoArea(1);
```

<br/>

### scrollToTop()

전체 그리드의 스크롤 위치를 최상단으로 변경한다.

```js
cPivotView.scrollToTop();
```

<br/>

### scrollToBottom()

전체 그리드의 스크롤 위치를 최하단으로 변경한다.

```js
cPivotView.scrollToBottom();
```

<br/>

### scrollToCenter()

전체 그리드의 스크롤 위치를 중앙으로 변경한다.

```js
cPivotView.scrollToCenter();
```

<br/>
