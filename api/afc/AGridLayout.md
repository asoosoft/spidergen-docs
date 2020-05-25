# AGridLayout
**Extends** [`ALayout`](ALayout.html#alayout)

insertView 함수를 호출하여 ViewDirection 방향으로 뷰를 추가한다.<br/>
추가하려는 뷰의 높이가 100% 이면 남은 공간 전체를 차지한다.<br/>
auto 나 픽셀을 직접 지정한 경우는 원하는 높이가 된다.

<br/>
<br/>

## Class Variables

<br/>
<br/>

## Instance Variables

<br/>
<br/>

## Instance Methods

### createLayout( rowCount, colCount, rowSizeArr, colSizeArr )

레이아웃의 틀을 생성한다.

- `rowCount` \<Number> 로우의 갯수
- `colCount` \<Number> 컬럼의 갯수
- `rowSizeArr` \<Array> 로우의 사이즈 배열
- `colSizeArr` \<Array> 컬럼의 사이즈 배열

<br/>

### getCell( row, col )

특정 포지션의 cell을 리턴한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- **Returns** \<HTML Object>

<br/>

### getCellAlign( row, col )

그리드 레이아웃 특정 위치의 셀의 text-align값을 리턴한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- **Returns** \<String>

<br/>

### getCellPadding( row, col )

특정 포지션 셀의 Padding 값을 리턴 한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- **Returns** \<Number>

<br/>

### getCellValign( row, col )

특정 포지션 셀의 verticalAlign값을 리턴한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- **Returns** \<String>

<br/>

### getColGroupItem( col )

그리드 레이아웃의 컬럼그룹을 리턴한다.

- `col` \<Number> 컬럼 인덱스

<br/>

### getColGroupItems()

그리드 레이아웃의 컬럼의 개수를 리턴한다.

- **Returns** \<number>

<br/>

### getCols()

컬럼의 개수를 리턴한다.

- **Returns** \<Number>

<br/>

### getColSize( col )

특정 컬럼의 너비값을 리턴한다.

- `col` \<Number>
- **Returns** \<Number> col 인덱스

<br/>

### getLayoutAlign()

레이아웃의 text-align값을 리턴한다.

- **Returns** \<String>

<br/>

### getLayoutComp( row, col )

특정 인덱스의 컴포넌트를 리턴한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- **Returns** \<AComponent>

<br/>

### getLayoutPadding()

레이아웃의 Padding 값을 리턴한다.

- **Returns** \<Number>

<br/>

### getRow( row )

특정 인덱스의 로우를 리턴한다.

- `row` \<Number> row 인덱스
- **Returns** \<Object>

<br/>

### getRows()

그리드 레이아웃 전체 로우의 개수를 리턴한다.

- **Returns** \<Number>

<br/>

### getRowSize( row )

특정 로우의 높이값을 리턴한다.

- `row` \<Number> row 인덱스
- **Returns** \<Number>

<br/>

### initLayoutComp( evtListener )

레이아웃 내부의 컴포넌트들을 초기화 한다.

- `evtListener` \<Object> context에 매핑된 이벤트 수신자

<br/>

### insertCol( col, isAfter )

특정 컬럼 앞, 또는 뒤에 새로운 컬럼을 삽입합니다.

- `col` \<Number> col 인덱스
- `isAfter` \<Boolean> 앞인지 뒤인지 여부

<br/>

### insertRow( row, isAfter )

그리드 레이아웃에서 특정 로우 앞, 또는 뒤에 새로운 로우를 삽입한다.

- `row` <Number> row 인덱스
- `isAfter` <Boolean> 앞인지 뒤인지 여부

<br/>

### layComponent( acomp, cell, width, height )

특정 셀에 컴포넌트를 추가한다. 셀을 지정해주지 않으면 빈자리에 추가된다.

- `acomp` \<AComponent> 추가 할 컴포넌트
- `cell` \<Object> 셀
- `width` \<Number> 너비
- `height` \<Number> 높이

```js
// 버튼컴포넌트를 [2,1]위치에 삽입함
var btn = new AButton();
btn.init();
var cell = gridLayout.getCell(2,1);
var item = gridLayout.layComponent(btn, cell);
```

<br/>

### layComponentAt( acomp, row, col, width, height )

특정 위치에 컴포넌트를 추가한다.

- `acomp` \<AComponent> 추가 할 컴포넌트
- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- `width` \<Number> 너비 (생략하면 100%)
- `height` \<Number> 높이 (생략하면 100%)

```js
var btn = new AButton(); // 버튼컴포넌트를 [2,1]위치에 삽입한다.
btn.init();
var item = gridLayout.layComponentAt(btn, 2, 1);
```

<br/>

### mergeCol( row, col, span )

그리드 레이아웃의 특정 컬럼을 병합한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- `span` \<Number> 병합하려는 개수

```js
//그리드 레이아웃 [1,1]위치의 셀로부터 2칸을 세로로 병합한다.
gridLayout.mergeCol(1,1,2);
```

<br/>

### mergeRow( row, col, span )

그리드 레이아웃의 특정 로우를 병합한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- `span` \<Number> 병합하려는 개수

```js
//그리드 레이아웃의 [2,1] 부터 3칸을 가로로 병합함.
gridLayout.mergeRow(2,1,3);
```

<br/>

### reduceColSpanCount( row, col )

특정 셀의 colspan을 감소시킨다. 1이하일 경우에는 제거한다.

- `row` \<Number> 로우 인덱스
- `col` \<Number> 컬럼 인덱스

<br/>

### removeCol( col )

그리드 레이아웃의 특정 컬럼을 삭제한다. 단, 숨겨진 cell에 colspan이 존재하면 안된다.

- `col` \<Number> 컬럼 인덱스

<br/>

### removeRow( row )

그리드 레이아웃의 특정 로우를 삭제한다.

- `row` \<Number> 로우 인덱스

<br/>

### setCellAlign( row, col, align )

그리드 레이아웃 특정 셀의 text-align값을 설정한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- `align` \<String> text-align css value값

```js
//그리드 레이아웃의 [1,1]좌표에 있는 셀의 text-align css value값을 center로 지정
gridLayout.setCellAlign(1,1,'center');
```

<br/>

### setCellPadding( row, col, padding )

그리드 레이아웃 특정 셀의 패딩값을 설정한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- `padding` \<Number> 패딩값

```js
//그리드레이아웃 [1,2] 좌표의 패딩을 5로 지정
gridLayout.setCellPadding(1,2,5);
```

<br/>

### setCellValign( row, col, align )

그리드 레이아웃 특정 셀의 vertical-align를 설정한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스
- `align` \<String> vertical-align css value 값

```js
//그리드 레이아웃 [1,1]위치의 셀의 vertical-align값을 middle로 지정
gridLayout.setCellValign(1,1,'middle');
```

<br/>

### setCols( cols )

컬럼의 개수를 설정한다.

- `cols` \<Number> 개수

<br/>

### setColsDivPercent()

컬럼의 크기를 퍼센트로 설정한다.

<br/>

### setColSize( col, size )

그리드 레이아웃 특정 컬럼의 width를 설정한다.

- `col` \<Number> col 인덱스
- `size` \<Number> 크기

```js
grid.setColSize(1, '20px');
```

<br/>

### setLayoutAlign( align )

레이아웃의 text-align 값을 설정한다.

- `align` \<String> text-align css value값

```js
gridLayout.setLayoutAlign('center');
```

<br/>

### setLayoutPadding( padding )

그리드 레이아웃의 패딩 값을 설정한다.

- `padding` \<Object> padding 값

<br/>

### setLayoutSize( rowSizeArr, colSizeArr )

레이아웃의 각 로우와 셀의 크기를 설정한다.

- `rowSizeArr` \<Array> 로우 사이즈 배열
- `colSizeArr` \<Array> 컬럼 사이즈 배열

```js
var size = [50, 20, '30px'];
gridLayout.setLayoutSize(size, size);
```

<br/>

### setRows( rows )

로우의 개수를 설정한다.

- `rows` <Number> 개수

<br/>

### setRowsDivPercent()

로우의 크기를 퍼센트로 설정한다.

<br/>

### setRowSize( row, size )

그리드 레이아웃의 특정 로우의 높이를 설정한다.

- `row` \<Number> row 인덱스
- `size` \<Number> 크기

```js
gridLayout.setRowSize(1, '15px');
```

<br/>

### splitCell( row, col )

특정위치의 셀이 병합되어 있다면 모두 분리한다.

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스

```js
gridLayout.splitCell(0,1);
```

<br/>

### splitCol( row, col )

그리드 레이아웃의 특정 셀이 세로로 병합되어 있다면 분리한다. (해당 셀의 colspan을 제거한다)

- `row` <Number> row 인덱스
- `col` <Number> col 인덱스

<br/>

### splitRow( row, col )

그리드 레이아웃의 특정 셀이 가로로 병합되어 있다면 분리한다. (해당 셀의 rowspan을 제거한다)

- `row` \<Number> row 인덱스
- `col` \<Number> col 인덱스

<br/>
<br/>

## Property

### Rows 
현재 로우의 총 개수  

### Cols  
현재 컬럼의 총 개수  

### Cell Height 
선택한 셀의 높이를 설정하는 속성

### Cell Width  
선택한 셀의 넓이를 설정하는 속성
 
### Cell Padding 
선택한 셀의 패딩을 설정하는 속성

### Cell Color 
선택한 셀의 배경색을 설정하는 속성

### Cell Borders
선택한 셀의 모서리를 설정하는 속성
   
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp101.png) : 선택된 셀의 top line만 border를 설정한다.
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp102.png) : 선택된 셀의 horizontal middle line 만 border를 설정한다.
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp103.png) : 선택된 셀의 bottom line만 border를 설정한다.
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp104.png) : 선택된 셀의 left line만 border를 설정한다. 
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp105.png) : 선택된 셀의 vertical middle line만 border를 설정한다.
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp106.png) : 선택된 셀의 right line만 border를 설정한다.
* **All:** 선택된 셀의 모든 border를 설정한다.
* **OutLine:** 선택된 셀의 테두리 line만 border를 설정한다.
* **Clear:** 선택된 셀에 적용된 border를 초기화한다.
  
### Cell Context Menu   
셀을 우클릭하면 나타나는 메뉴
  
* **Merge:** 현재 선택한 셀들을 하나의 셀로 합병한다.
* **Split:** Merge 된 셀을 Merge 전의 셀들로 분리한다.
* **Insert Row:** 현재 선택한 셀의 앞에 Row를 추가한다.
* **Delete Row:** 현재 선택한 셀의 Row를 삭제한다.
* **Insert Col:** 현재 선택한 셀의 앞에 Column을 추가한다.
* **Delete Col:** 현재 선택한 셀을 삭제한다.
* **Col H-Align:** 현재 선택한 셀내의 element를 가로 정렬한다.
    * **center:** 셀 내의 element를 중앙 정렬한다.
    * **left:** 셀 내의 element를 좌측 정렬한다.
    * **right:** 셀 내의 element를 우측 정렬한다.
    * **justify:** 셀 내의 element를 넓이 만큼 사이즈를 조정한다.

* **Col V-Align:** 현재 선택한 셀내의 element를 세로 정렬한다.
    * **middle:** 셀 내의 element를 세로 중앙에 정렬한다.
    * **top:** 셀 내의 element를 맨 상단으로 정렬한다.
    * **bottom:** 셀 내의 element를 맨 하단으로 정렬한다.
    * **baseline:** 셀 내의 element를 기준선에 맞추어 정렬한다.

<br/>
