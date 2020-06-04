# AGrid
> **Extends** [`AComponent`](./AComponent.md)

그리드 컴포넌트

<br/>

## Class Variables

<br/>

## Instance Variables

### columnCount \<Number>

그리드의 컬럼 개수

<br/>

### isStoppagation \<Boolean>

그리드 터치시 상위로 이벤트 전달 여부

* `Default` true

<br/>


### realMap \<Object>

특정 키에 대응하는 row 객체를 가지고 있는 맵. 수신된 리얼 데이터에서 키를 추출하여 realMap 으로부터 특정 row 객체를 얻어 화면을 갱신한다.

<br/>

### scrlManager \<[ScrollManager](./../library/ScrollManager.md)>

자체적으로 스크롤 기능을 제공해 주는 객체

<br/>

### selectedCells \<Array>

선택된 셀,행 집합

<br/>

<!-- 
### shiftSelectedCells \<Array>

shift로 선택한 셀 목록

<br/>

### savedScrollPos \<Number>

스크롤 복원값

<br/> -->

### hRowTmplHeight \<Number>

헤더 로우들의 높이 합

<br/>

### rowTmplHeight \<Number>

바디 템플릿 로우들의 높이 합

<br/>

### isCheckScrl \<Boolean>

로우가 추가되거나 제거될 때 스크롤의 생성,제거 체크여부

<br/>

## Class Methods

<br/>

## Instance Methods

### addColumn()

그리드에 컬럼을 추가한다. 마지막컬럼 뒤에 추가된다.

```js
grid.addColumn();
```

<br/>

### addRow( infoArr, rowData )

그리드에 추가될 데이터를 배열로 받아 새로운 RowSet 객체를 생성하여 그리드에 추가한다. RowSet 이란 한번의 addRow 가 호출될 때마다 추가될 로우 그룹이다. RowSet은 화면 디자인 시점에 설정된다.

* `infoArr` \<Array> RowSet 구조와 매칭되는 배열 데이터
* `rowData` \<All> 하나의 RowSet 가 추가될 때, 같이 저장해 두어야 하는 데이터가 있을 경우 셋팅한다.

* **Returns** \<jQuery> 추가된 Row 그룹이 jQuery 객체로 리턴된다.

```js
var data = [ 1, 2, 3, 'a' ];
var row = grid.addRow(data);
```

<br/>

### applyBackupScroll()

그리드에 백업스크롤을 적용한다. <br/><br/>※ 그리드내부에 표현될 항목의 최대 개수와 복원 개수를 지정하여 항목을 무한히 추가하지 않고 관리한다.

* **Returns** \<Number> 적용된 백업스크롤 위치값

```js
var result = grid.applyBackupScroll();
```

<br/>

### cellAddClass( rowIdx, colIdx, className )

그리드 바디의 특정 cell 에 스타일 클래스를 추가한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼인덱스
* `className` \<String> 스타일 클래스명

```js
grid.cellAddClass(1,1,'ClassName);
```

<br/>

### cellRemoveClass( rowIdx, colIdx, className )

그리드 바디의 특정 cell 에 스타일 클래스를 제거한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼인덱스
* `className` \<String> 스타일 클래스명

```js
grid.cellRemoveClass(1,1,'ClassName');
```

<br/>

### changeRowCount( count, isHead )

그리드의 로우셋 카운트를 변경한다.

* `count` \<Number> 로우셋을 구성할 로우의 개수
* `isHead` \<Boolean> 헤더 여부

```js
grid.changeRowCount(2);
```

<br/>

### checkScrollbar( isAdd )

스크롤바 존재 여부에 따라 headerTable 의 사이즈를 조정한다.

* `isAdd` \<Boolean> true / false

```js
//add 인 경우는 스크롤바가 안 보이는 경우만 체크하고
//remove 인 경우는 스크롤바가 보이는 경우만 체크한다. 
grid.checkScrollbar(true);
```

<br/>

### clearAll()

그리드의 모든 텍스트와 background style을 삭제한다.

```js
grid.clearAll();
```

<br/>

### clearContents()

그리드의 모든 텍스트를 지운다.

```js
grid.clearContents();
```

<br/>

### clearSelected()

선택된 셀(행)을 모두 해제시킨다.(선택되지 않은 상태로 변경)

```js
grid.clearSelected();
```

<br/>

### colIndexOfCell( cell )

파라미터로 넘어온 cell 의 column index 를 리턴한다.

* `cell` \<HTMLTableCellElement> 셀 엘리먼트
* **Returns** \<Number>

```js
//선택된 셀의 column  index
var index = grid.colIndexOfCell(grid.getSelectedCells()[0]);
```

<br/>

### createBackup( maxRow, restoreCount )

백업 시스템이 작동하도록 BackupManager 를 생성한다.

* `maxRow` \<Number> 백업을 시작할 최대 row 개수
* `restoreCount` \<Number> 한번에 백업 및 복원할 row 개수

<br/>

### createRow( rowData )

로우를 추가하는 다른 함수에서 내부적으로 로우를 생성할떄 호출한다.

* `rowData` \<Object> rowData
* **Returns** \<$rowSet>

<br/>

### decreaseColSpan( tdDom )

컬럼이 삭제될 때 호출되는 함수이다. 제거되야할 td가 colspan을 가지고 있다면 하나줄여주거나 colspan을 제거한다.

* `tdDom` \<HTML Object> td DOM 객체

<br/>

### deselectCell( cellArr )

파라미터로 넘어온 셀 또는 row를 선택해제해주고 배경색을 바꿔주는 함수이다.

* `cellArr` \<Array or jQueryObject > element 를 담고 있는 배열이거나 jQuery 집합 객체

<br/>

### destroyBackup()

백업 시스템을 중단하고 BackupManager 를 소멸시킨다.

<br/>

### enableScrlManager( leftSyncArea, rightSyncArea )

터치 이벤트를 핸들링하여 자체적으로 구현한 스크롤 기능을 활성화 한다. 내부적으로 [ScrollManager](../library/ScrollManager.md) 가 사용된다.

* `leftSyncArea` \<HTML Object> 그리드가 스크롤될 때 같이 움직일 좌측 스크롤 영역
* `rightSyncArea` \<HTML Object> 그리드가 스크롤될 때 같이 움직일 우측 스크롤 영역

<br/>

### findRowByCellData( nCol, data )

특정 컬럼의 특정 Object 값을 가지는 row 객체를 리턴하는 함수이다. 단, 최초에 찾은 로우만 리턴한다.

* `nCol` \<Number> 검색하고자 하는 컬럼
* `data` \<Object> 검색하고자 하는 Object
* **Returns** \<HTMLTableRowElement> 로우 엘리먼트

```js
//3번째 컬럼이 가지고 잇는 데이터와 일치하는 row를 리턴한다.
var data = '검색하고자 하는 data Object';
var row = grid.findRowByCellData(3, data);
```

<br/>

### findRowByCellText( nCol, text )

특정 컬럼의 특정 문자열 값을 가지는 row 객체를 찾는다. 단, 최초에 찾은 로우만 리턴한다.

* `nCol` \<Number> 검색하고자 하는 컬럼
* `text` \<String> 검색하고자 하는 문자열
* **Returns** \<HTMLTableRowElement> 로우 엘리먼트

```js
//3번쨰컬럼이 휴지인 Row를 리턴한다.
var row = grid.findRowByCellText(3, '휴지');
```

<br/>

### getAllLaiedComps()

그리드의 body에 추가된 컴포넌트들을 배열로 리턴한다.

* **Returns** \<Array>

<br/>

### getBodyColor()

그리드 바디의 배경색을 리턴한다.

* **Returns** \<String>

```js
var result = grid.getBodyColor();
```

<br/>

### getBodyHeight( row )

그리드 바디의 특정 로우의 높이를 리턴한다.

* `row` \<Number> 로우 인덱스

```js
//0번째 로우의 높이를 구하는 방법
var result = grid.getBodyHeight(0);
```

<br/>

### getCell( rowIdx, colIdx )

특정 idx 의 cell 을 얻어온다. rowIdx 값은 row 객체가 될 수 있다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 index
* **Returns** \<HTMLTableCellElement> 셀 엘리먼트

```js
//그리드의 (2,3)의 cell객체를 받아온다.
var cell= grid.getCell(2,3);

//방금 추가한 row의 1번째 컬럼의 cell 객체를 받아온다.
var row = grid.addRow([1,2,3,'abc']);
var cell = grid.getCell(row, 1);
```

<br/>

### getCellData( rowIdx, colIdx )

특정 cell 의 data 를 얻어온다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 인덱스
* **Returns** \<All>

```js
//[3.1]위치의 cell의 data
var result = grid.getCellData(3,1);
```

<br/>

### getCellHeight( cell )

셀의 높이를 리턴한다.

* `cell` \<Object> 셀의 객체

```js
var cell = grid.getCell(1, 2);
var result = grid.getCellHeight(cell);
```

<br/>

### getCellIndex( cell )

해당 셀의 Row, Column 인덱스값을 배열로 리턴한다.

* `cell` \<Object> 셀의 객체
* **Returns** \<Array>

```js
var cell = grid.getCell(0, 1);
var result = grid.getCellIndex(cell);
// result -> [0,1]
```

<br/>

### getCellPos( cell )

해당셀의 위치를 배열로 리턴한다.

* `cell` \<Object> 셀의 객체
* **Returns** \<Array>

```js
var result = grid.getCellPos(cell);
//result -> [1,3];
```

<br/>

### getCellTag( rowIdx, colIdx )

특정 cell 의 태그를 얻어온다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 인덱스
* **Returns** \<HTML Object>

```js
//[1,1]위치의 cell의 태그
var tag = grid.getCellTag(1,1);
```

<br/>

### getCellText( rowIdx, colIdx )

특정 cell 의 텍스트를 얻어온다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> col index
* **Returns** \<String>

```js
//[2,2]위치의 cell의 텍스트
var text = grid.getCellText(2,2);
```

<br/>

### getColumnCount()

column 의 개수를 리턴한다.

* **Returns** \<Number> 컬럼 개수

```js
var result = grid.getColumnCount();
```

<br/>

### getDataByOption( rowInfo )

파라미터로 넘어온 객체의 엘리먼트에 저장되어 있는 데이터를 리턴하는 함수이다.

* `rowInfo` \<jQuery Object> 그리드 이벤트에서 넘어오는 Info
* **Returns** \<All> 데이터

```js
//그리드 셀렉트 이벤트 리스너 함수에서 다음과 같은 방식으로 data를 받아서 사용한다.
function 화면명:onGridSelect(comp, info)
{
var data = comp.getDataByOption(info);
}
```

<br/>

### getFirstRow()

그리드의 첫 번째 로우를 리턴한다.

* **Returns** \<HTMLTableRowElement> 로우 엘리먼트

```js
var row = grid.getFirstRow();
```

<br/>

### getHeadColor()

헤더의 배경색을 리턴한다.

* **Returns** \<String>

```js
var result = grid.getHeadColor();
```

<br/>

### getHeaderCell( rowIdx, colIdx )

특정 idx 의 header cell 을 얻어온다. rowIdx 값은 row 객체가 될 수 있다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 인덱스
* **Returns** \<HTMLTableCellElement> 셀 엘리먼트

```js
// 그리드 헤더의 [1,3] 위치에 있는 cell
var cell = grid.getHeaderCell(1,3);
```

<br/>

### getHeaderRowCount()

그리드에서 헤더로우의 개수를 리턴한다.

* **Returns** \<Number> 헤더로우 개수

```js
var result = grid.getHeaderRowCount();
```

<br/>

### getHeadHeight( row )

헤드의 특정 Row의 높이를 리턴한다.

* `row` \<Number> 헤더 로우의 Index
* **Returns** \<Number>

```js
var result = grid.getHeadHeight(1);
```

<br/>

### getHideHeaderCell()

hideThead의 특정 cell을 리턴한다.

* **Returns** \<HTMLTableCellElement> 셀 엘리먼트

```js
//[1,1]위치의 cell 객체
var cell = grid.getHideHeaderCell(1,1);
```

<br/>

### getLastRow()

마지막 row 를 얻어온다.

* **Returns** \<HTMLTableRowElement> 로우 엘리먼트

```js
var row = grid.getLastRow();
```

<br/>

### getRealKey( data )

getRealKey

* `data` \<String> data

<br/>

### getRow( rowIdx )

특정 인덱스의 row 를 얻어온다.

* `rowIdx` \<Number> 로우 위치
* **Returns** \<HTMLTableRowElement> 로우 엘리먼트

```js
//1번 index의 Row
var row = grid.getRow(1);
```

<br/>

### getRowCount()

row 의 개수를 리턴한다.

* **Returns** \<Number> 로우 개수

```js
var result = grid.getRowCount();
```

<br/>

### getRowDataByIndex( rowIdx )

그리드에서 파라미터로 넘어온 Row Index로 Row에 저장해둔 Data를 리턴한다.

* `rowIdx` \<Number> 로우 인덱스
* **Returns** \<Row Object>

```js
//2번째 index의 데이터를 리턴한다.
var data = grid.getRowDataByIndex(2);
```

<br/>

### getRowIndexByInfo( rowInfo )

로우 객체의 row index 를 리턴하는 함수이다.

* `rowInfo` \<jQuery Object> 이벤트 리스너에서 넘어오는 그리드 Info
* **Returns** \<Number>

```js
//화면에서 등록한 그리드 select 리스너 함수에서 사용법은 다음과 같다.
function 화면명:onGridSelect(comp, info, e)
{
var index = comp.getRowIndexByInfo(info);
}
```

<br/>

### getRowParentTag( cell )

그리드의 해당 셀이 tHead인지 tBody인지 판단해서 리턴한다.

* `cell` \<Object> 셀의 객체
* **Returns** \<String>

```js
var result = grid.getRowParentTag(cell);
//result -> 'tHead' or 'tBody'
```

<br/>

### getRows( start, end )

특정 영역의 row 집합을 얻어온다. 파라미터가 없으면 모든 row 집합을 리턴한다.

* `start` \<Number> 시작 인덱스
* `end` \<Number> 끝 인덱스
* **Returns** \<JQueryObject Array>

```js
//1~5번 index의 row 객체의 배열 (파라미터를 생략하면 모든 row를 리턴한다)
var rowArr = grid.getRows(1,5);
```

<br/>

### getRowSet( rowIdx )

그리드의 특정 RowSet을 리턴한다.

* `rowIdx` \<Number> 로우 인덱스
* **Returns** \<jQueryObject> 로우셋 객체

```js
//2번째 index의 RowSet을 리턴한다.
var rowSet = grid.getRowSet(2);
```

<br/>

### getRowSetCount()

그리드 로우셋의 개수를 리턴한다.

* **Returns** \<Number> 로우셋 개수

```js
var result = grid.getRowSetCount();
```

<br/>

### getScrollPos()

스크롤의 위치값을 리턴한다.

* **Returns** \<Number>

```js
var result = grid.getScrollPos();
```

<br/>

### getSelectedCells()

현재 선택되어져 있는 셀들을 배열로 리턴한다.

* **Returns** \<Array>

```js
var cellArr = grid.getSelectedCells();
var cell = cellArr[0];
```

<br/>

### hideHeader()

그리드 헤더를 숨긴다.

```js
grid.hideHeader();
```

<br/>

### indexOfCell( cell )

파라미터로 넘어온 cell 의 rowIndex 와 colIndex 값을 배열로 리턴한다.

* `cell` \<HTMLTableCellElement> index 값을 알고자 하는 셀 엘리먼트
* **Returns** \<Array> [rowIndex, colIndex]

```js
// [3,1] 위치의 cell
var result = grid.indexOfCell(cell);
// 다음과 같이 배열로 리턴된다.  -> [3,1]
```

<br/>

### indexOfRow( row )

파라미터로 넘어온 row 의 index 를 리턴한다.

* `row` \<HTMLTableRowElement> 로우 엘리먼트
* **Returns** \<Number> 로우 위치

```js
//방금 추가한 로우의 index를 받아온다.
var row = grid.addRow(data);
var index = grid.indexOfRow(row );
```

<br/>

### init( context, evtListener )

그리드를 생성하고 초기화 할때 호출한다. 그리드 구현 기본 알고리즘이 정의되어 있다.<br/>[헤더] 역할을 하는 header table 은 tbody 부분이 없으며 최상단으로 띄운다.<br/>[바디] 역할을 하는 table 은 thead 부분을 invisible 시켜 [헤더 table] 밑으로 들어가게 한다.  <br/>동적으로 생성할 경우에는 파라미터를 생략하고 호출한다.

* `context` \<String> 컴포넌트 생성 및 초기화 정보
* `evtListener` \<String> context에 매핑된 이벤트 수신자

```js
var grid = new AGrid();
grid.init();
```

<br/>

### insertDefaultCell( table, row, col, isAfter )

기본셀을 추가하는 함수이다. 컬럼을 삽입하는 함수에서 호출해서 사용한다.

* `table` \<String> 영역(showThead, hideThead, tBody)
* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스
* `isAfter` \<Boolean> true: after / false:before

<br/>

### insertRow( nRow, infoArr, rowData )

그리드의 특정 row 앞에 infoArr 를 추가한다.

* `nRow` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `infoArr` \<Array> 로우셋을 구성하는 배열 데이터
* `rowData` \<All> 로우에 저장할 데이터
* **Returns** \<jQueryObject> 로우 jQueryObject

```js
var infoArr = [1,2,3,'abc'];
//10번째 index의 Row앞에 Row를 추가함.
grid.insertRow(10, infoArr);

//특정 Row(해당 grid의 특정 Row Object라고 가정한다.) 앞에 Row를 추가함
var row = grid.getRow(9);
grid.insertRow(row, infoArr);
```

<br/>

### insertSingleCol( colIndex, isAfter )

그리드의 해당 컬럼위치에 컬럼을 삽입한다.

* `colIndex` \<Number> 컬럼 인덱스
* `isAfter` \<Boolean> true: after / false: before

```js
//1번 컬럼의 다음에 새로운 컬럼을 삽입한다.
grid.insertSingleCol(1, true);

//1번 컬럼의 이전에 새로운 컬럼을 삽입한다.
grid.insertSingleCol(1, false);
```

<br/>

### insertSingleRow( rowIndex, isAfter, isHead )

그리드의 특정 위치에 로우를 삽입한다.

* `rowIndex` \<Number> 로우 인덱스
* `isAfter` \<Boolean> true: after / false: before
* `isHead` \<Boolean> true: header / false: body

```js
grid.insertSingleRow(2);
```

<br/>

### isHeadCell( cell )

해당셀이 헤더의 셀인지 체크한 값을 리턴한다.

* `cell` \<Object> cell의 객체
* **Returns** \<Boolean>

```js
var result = grid.isHeadCell(cell);
```

<br/>

### isMoreScrollBottom()

하단으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

* **Returns** \<Boolean>

```js
var result = grid.isMoreScrollBottom();
```

<br/>

### isMoreScrollTop()

상단으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

* **Returns** \<Boolean>

```js
var result = grid.isMoreScrollTop();
```

<br/>

### isScroll()

현재 스크롤이 가능한 상태인지 여부를 리턴한다.

* **Returns** \<Boolean>

```js
var result = grid.isScroll();
```

<br/>

### isScrollBottom()

현재 그리드의 스크롤이 가장 하단인지 여부를 리턴한다.

* **Returns** \<Boolean>

```js
var result = grid.isScrollBottom();
```

<br/>

### isScrollTop()

현재 스크롤의 위치가 가장 상단인지 여부를 리턴한다.

* **Returns** \<Boolean>

```js
var result = grid.isScrollTop();
```

<br/>

### layComponent( acomp, row, col, width, height )

특정 셀(row,col)에 컴포넌트를 추가한다.

* `acomp` \<Object> 컴포넌트 객체(ex, ALabel, AButton 등등 컴포넌트)
* `row` \<Number or HTMLTableRowElement> 숫자가 아닌 row 객체가 될 수 있다.
* `col` \<Number> Column Index
* `width` \<String> 가로크기. 생략시 100%
* `height` \<String> 세로크기. 생략시 100%

```js
//그리드의 (2,1)에 버튼을 삽입하는 방법
//btn은 버튼 컴포넌트라고 가정한다.
grid.layComponent(btn, 2, 1);

//마지막으로 추가한 로우의 2번 컬럼에 버튼 넣는 방법
var row = grid.addRow(data);
grid.layComponent(btn, row, 2);
```

<br/>

### layHeaderComponent( acomp, row, col, width, height )

특정 헤더(row,col)에 컴포넌트를 추가한다.

* `acomp` \<AComponent> 컴포넌트객체(label, button 등등의 컴포넌트)
* `row` \<Number or HTMLTableRowElement> Row index or Row Object
* `col` \<Number> Column Index
* `width` \<String> 가로크기. 생략시 100%
* `height` \<String> 세로크기. 생략시 100%

```js
//그리드 헤더의 (2,1)에 버튼을 삽입하는 방법
//btn은 버튼 컴포넌트라고 가정한다.
grid.layHeaderComponent(btn, 2, 1);
```

<br/>

### loadCellView( rowIdx, colIdx, url )

해당 셀에 view를 생성하고 레이아웃 URL을 로드한다.

* `rowIdx` \<Number> 로우 인덱스
* `colIdx` \<Number> 컬럼 인덱스
* `url` \<String> 로드될 레이아웃의 URL
* **Returns** \<AView>

```js
//[1,1]위치의 cell에  url의 뷰를 로드한다.
var view = grid.loadCellView(1,1,'view/name.lay');
```

<br/>

### mergeCol( row, col, span )

그리드 바디의 특정 컬럼을 병합한다.

* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스
* `span` \<Number> 병합하려는 개수

```js
//그리드 바디 [2,1]부터 3칸만큼의 컬럼을 병합한다.
grid.mergeCol(2,1,3);
```

<br/>

### mergeHeadCol( row, col, span )

그리드 헤더의 특정 컬럼을 병합한다.

* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스
* `span` \<Number> 병합하려는 개수

```js
//그리드 헤더 [2,1]부터 3칸만큼의 컬럼을 병합한다.
grid.mergeHeadCol(2,1,3);
```

<br/>

### mergeHeadRow( row, col, span )

그리드 헤더의 특정 로우를 병합한다.

* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스
* `span` \<Number> 병합하는 개수

```js
//그리드 헤더의 [2,1]부터 3칸만큼 병합한다.
grid.mergeHeadRow(2,1,3);
```

<br/>

### mergeRow( row, col, span )

그리드 바디의 특정 로우를 병합한다.

* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스
* `span` \<Number> 병합할 개수

```js
//그리드 바디의 [2,1]부터 3칸만큼 병합한다.
grid.mergeRow(2,1,3);
```

<br/>

### moveRow( fromRow, toRow )

해당 로우를 특정위치로 이동한다.

* `fromRow` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `toRow` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트

```js
//그리드의 3번 index위치의 로우를 맨앞으로 이동한다.
grid.moveRow(3, 0);
```

<br/>

### prependRow( infoArr, rowData )

rowData 를 그리드에 상단에 추가한다.

* `infoArr` \<Array> 로우셋을 구성하는 배열 데이터
* `rowData` \<All> 로우에 저장할 데이터
* **Returns** \<jQueryObject> 로우 jQueryObject

```js
var data = [1,2,3,'abc'];
var row = grid.prependRow(data);
//add할떄 생성된 row Object가 리턴된다.
```

<br/>

### regCellEvent( $evtEle )

셀의 이벤트를 등록할떄 호출하는 함수이다.

* `$evtEle` \<jQuery Object> 이벤트 등록에서 예외적으로 dom element 가 아닌 jQuery 객체를 사용함

<br/>

### removeAll()

그리드의 모든 row 를 제거한다.

```js
grid.removeAll();
```

<br/>

### removeColumn( colIdx )

그리드의 특정 컬럼을 삭제한다.

* `colIdx` \<Number> 컬럼 인덱스

```js
grid.removeColumn(3);
```

<br/>

### removeFirst()

첫번째 row를 제거한다.

```js
grid.removeFirst();
```

<br/>

### removeHeaderRow( rowIdx )

그리드 헤더의 특정 Row를 제거한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트

```js
//1번째 index의 헤더로우를 제거한다.
grid.removeHeaderRow(1);
```

<br/>

### removeLast()

마지막 Row를 제거한다.

```js
grid.removeLast();
```

<br/>

### removeRow( rowIdx )

특정 row 를 그리드에서 제거한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트

```js
//1번 index의 row를 제거한다.
grid.removeRow(1);

//방금 추가한 로우를 제거한다.
var row = grid.addRow(data);
grid.removeRow(row);
```

<br/>

### removeRowSet( rowIdx )

특정 위치의 rowset을 제거하는 함수이다.

* `rowIdx` \<Number> 삭제하고자 하는 rowset 의 위치

```js
//1번째 위치의 rowSet을 제거한다.
grid.removeRowSet(1);
```

<br/>

### restoreScrollPos()

저장해둔 그리드의 위치로 스크롤 시킨다.

```js
grid.restoreScrollPos();
```

<br/>

### rowIndexOfCell( cell )

파라미터로 넘어온 cell 의 row index 를 리턴한다.

* `cell` \<HTMLTableCellElement> 셀 엘리먼트
* **Returns** \<Number>

```js
//선택된 셀의 row index
var index = grid.rowIndexOfCell(grid.getSelectedCells()[0]);
```

<br/>

### saveScrollPos()

현재의 그리드 위치를 저장해 둔다.

```js
grid.saveScrollPos();
```

<br/>

### scrollIntoArea( row, isAlignTop )

파라미터로 넘어온 row 객체가 보이도록 그리드를 스크롤 시킨다.

* `row` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `isAlignTop` \<Boolean> row를 상단으로 해서 보일지 여부(false 일 경우 하단)

```js
//특정 로우가 보이도록 스크롤 시킨다.
var row = grid.getRow(1);
grid.scrollIntoArea(row);
or
grid.scrollIntoArea(1);
```

<br/>

### scrollOffset( offset )

그리드를 현 위치에서 offset 만큼 스크롤 시킨다.

* `offset` \<Number> 스크롤시킬 값

```js
grid.scrollOffset(100);
grid.scrollOffset(-100)
```

<br/>

### scrollTo( pos )

그리드를 pos 의 위치로 스크롤 시킨다.

* `pos` \<Number> 스크롤의 위치값

```js
grid.scrollTo(0);
grid.scrollTo(50);
```

<br/>

### scrollToBottom()

그리드를 최하단의 위치로 스크롤 시킨다.

```js
grid.scrollToBottom();
```

<br/>

### scrollToCenter()

그리드를 중앙의 위치로 스크롤 시킨다.

```js
grid.scrollToCenter();
```

<br/>

### scrollToTop()

그리드를 최상단의 위치로 스크롤 시킨다.

```js
grid.scrollToTop();
```

<br/>

### selectCell( cellArr, e )

특정 cell 또는 row 를 선택된 상태로 변경한다.(중복, 연속 선택 가능)

* `cellArr` \<Array or jQueryObject > element 를 담고 있는 배열이거나 jQuery 집합 객체
* `e` \<Object> event Object

```js
//0번 index의 로우를 선택 상태로 만든다.
var row = grid.getRow(0);
grid.selectCell(row);
```

<br/>

### setBodyColor( color )

그리드 바디의 배경색을 설정한다.

* `color` \<String> background-color css value값

```js
grid.setBodyColor('#000000');
```

<br/>

### setBodyHeight( bodyHeight )

그리드 바디의 높이를 변경한다.

* `bodyHeight` \<String> 높이 값

```js
grid.setBodyHeight('50px');
```

<br/>

### setCellBgColor2( cell, color )

해당 셀의 백그라운드 색상을 지정한다.

* `cell` \<Object> 셀 객체
* `color` \<String> Color RGB값

```js
var cell = grid.getCell(1, 1);
grid.setCellBgColor2(cell, '#000000');
```

<br/>

### setCellData( rowIdx, colIdx, data )

그리드 바디의 특정 cell data를 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 인덱스
* `data` \<All> 데이터

<br/>

### setCellHAlign( cell, align )

해당 셀의 text-align을 세팅한다.

* `cell` \<Object> 셀의 객체
* `align` \<String> text-align css value값

```js
var cell = grid.getCell(1, 2);
grid.setCellHAlign(cell, 'center');
```

<br/>

### setCellHeight( cell, height )

셀의 높이를 변경한다. Row 전체가 바뀌어야 되므로 내부적으로 td 대신 tr의 높이를 변경한다.

* `cell` \<Object> 셀의 객체
* `height` \<String> 셀의 높이

```js
var cell = grid.getCell(1, 2);
grid.setCellHeight(cell, '10%');
grid.setCellHeight(cell, 100);
grid.setCellHeight(cell, '100px');
```

<br/>

### setCellStyle( rowIdx, colIdx, key, value )

바디 부분의 특정 셀의 특정 스타일을 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 인덱스
* `key` \<String> 스타일 키
* `value` \<String> 스타일 값

```js
grid.setCellStyle(1,1,{'background-color':'black'});
```

<br/>

### setCellTag( rowIdx, colIdx, tag )

그리드 바디의 특정 cell 태그를 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 인덱스
* `tag` \<HTML Object> 변경될 HTML Tag

```js
//[1,1]위치의 cell의 tag를 변경한다.
var = 'html tag....';
grid.setCellTag(1,1, tag)
```

<br/>

### setCellText( rowIdx, colIdx, txt )

그리드 바디의 특정 cell 텍스트를 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 인덱스
* `txt` \<String> 텍스트

```js
//그리드 [1,1]위치의 body cell 텍스트를 '휴지'로 지정한다.
grid.setCellText(1,1,'휴지');
```

<br/>

### setCellTextColor( rowIdx, colIdx, color )

그리드 바디의 특정 cell 의 텍스트 색상을 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼 인덱스
* `color` \<String> 컬러 RGB값

```js
//그리드의 [0,3]위치의 셀의 색상을 변경한다.
grid.setCellTextColor(0,3,'#000000');
```

<br/>

### setCellTextColor2( cell, color )

해당 셀의 텍스트 컬러를 변경한다. 이 함수는 셀의 인덱스가 아닌 셀의 객체를 이용한다.

* `cell` \<Object> 셀의 객체
* `color` \<String> 컬러 RGB값

```js
//셀의 컬러를 변경한다.
var cell = grid.getCell(0, 0);
grid.setCellTextColor2(cell, '#000000');
```

<br/>

### setCellVAlign( cell, align )

해당 셀의 vertical-align값을 세팅한다.

* `cell` \<Object> 셀의 객체
* `align` \<String> vertical-align css value값

```js
var cell = grid.getCell(1, 2);
grid.setCellVAlign(cell, 'middle');
```

<br/>

### setFlexibleRow( enable )

로우의 높이를 로우 개수에 맞게 균등 변경되도록 설정하는 함수이다. 단, 특정 셀에 필요한 높이가 최소 높이가 작은 경우 동일한 높이로 표현되지 않는다. 또한 로우의 높이가 최소높이가 된 경우에는 더 이상 작아지지 않는다.

* `enable` \<Boolean> true / false

```js
grid.setFlexibleRow(true);
```

<br/>



### setHeadColor( color )

그리드 헤더의 배경색을 설정한다.

* `color` \<String> background-color css value값

```js
grid.setHeadColor('#000000');
```

<br/>

### setHeaderCellText( rowIdx, colIdx, txt )

그리드 헤더의 특정 cell 텍스트를 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼인덱스
* `txt` \<String> 지정될 텍스트

```js
//[2,2]위치의 header cell의 text를 '휴지'로 지정한다.
grid.setHeaderCellText(2,2,'휴지');
```

<br/>

### setHeadHeight( headHeight )

헤더의 높이를 변경한다.

* `headHeight` \<String> 높이 값

```js
grid.setHeadHeight('50px');
```

<br/>




### setRealMap( realKey )

리얼맵이 작동하도록 환경을 셋팅한다. setQueryData 에서 사용(this.realKey, this.realMap 변수 설명 참조)

* `realKey` \<String> .

<br/>

### setRow( rowInx, rowData, start, end )

특정 로우의 텍스트를 세팅한다.

* `rowInx` \<Number> 로우 인덱스
* `rowData` \<Array> 텍스트 배열
* `start` \<Number> 시작 컬럼 인덱스(생략하면 로우 전체)
* `end` \<Number> 종료 컬럼 인덱스

```js
//1번 로우의 텍스트를 각각[1,2,3]으로 지정
grid.setRow(1, [1,2,3]);
```

<br/>

### setRowByObj( rowInx, rowData, start, end )

그리드의 특정 로우의 텍스트와 타입을 세팅한다.

* `rowInx` \<Number> 로우 인덱스
* `rowData` \<Array> 오브젝트 배열
* `start` \<Number> 시작 컬럼 인덱스(생략하면 로우 전체)
* `end` \<Number> 종료 컬럼 인덱스

```js
var data = [
　{ text: 'abc', type:'checkbox', checked:true },
　{ text: 'def', type:'checkbox', checked:false },
　{ text: 'qqq', type:'checkbox', checked:false }......];
grid.setRowByObj(1, data);
```

<br/>

### setScrollArrow( headHeight )

주로 모바일에서 사용되는 함수이다. 스크롤 표시가 없을 시 위, 아래 스크롤 아이콘을 표시한다.

* `headHeight` \<Number> 스크롤을 표시할 top 위치값

```js
//파라미터를 생략하고 헤더를 숨기는 그리드 옵션을 활성화 할때 top을 0으로 세팅.
grid.setScrollArrow();
```

<br/>

### setScrollComp( acomp )

그리드 스크롤과 관계되어 있는 컴포넌트를 세팅한다. 그리드가 스크롤 될 때 세팅된 컴포넌트의 상하 위치값을 변경하여 같이 스크롤되는 것처럼 보이게 한다.
단, enableScrlManager 가 호출된 경우에만 작동한다.

* `acomp` \<[AComponent](./AComponent.md)> 컴포넌트

<br/>

### showHeader()

그리드의 헤더를 보이게 한다.

<br/>

### splitCell( row, col )

그리드 바디의 특정 cell의 병합을 모두 해제한다.

* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스

```js
//그리드 바디[2,1] 좌표의 cell의 병합을 모두 해제한다.
grid.splitCell(2,1);
```

<br/>

### splitCol( row, col )

그리드 바디의 특정 셀의 세로 병합을 해제한다.(colspan만 제거한다.)

* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스

```js
//그리드 바디 [1,1] 의 세로 병합을 해제함
grid.splitCol(1,1);
```

<br/>

### splitHeadCell( row, col )

그리드 헤더의 병합된 셀을 모두 분리한다.

* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스

```js
//그리드 헤더 [2,1] 좌표의 cell의 병합을 모두 해제한다.
grid.splitHeadCell(2,1);
```

<br/>

### splitRow( row, col )

그리드 바디의 특정 cell의 가로병합을 해제한다. (rowspan만 제거)

* `row` \<Number> 로우 인덱스
* `col` \<Number> 컬럼 인덱스

```js
//그리드 바디 [1,1] 의 가로 병합을 해제함
grid.splitRow(1,1);
```

<br/>


### getCellComps( row, col )

하나의 셀에 들어있는 컴포넌트 배열을 리턴한다.

* `row` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `col` \<Number> 컬럼 인덱스
* **Returns** \<Array> 컴포넌트 배열

```js
var arr = grid.getCellComps(1,1);
```

<br/>


### getColumnComps( colInx )

특정 컬럼 위치의 모든 셀을 조사하여 들어있는 컴포넌트 목록을 가져온다.

* `col` \<Number> 컬럼 인덱스
* **Returns** \<Array> 컴포넌트 목록

```js
var arr = grid.getColumnComps(0);
```

<br/>


### getDataMask( rowIdx, colIdx, maskIdx )

셀에 세팅한 ADataMask 인스턴스 또는 마스킹(데이터를 가공하는) 함수와 파라미터를 얻어온다.

* `rowIdx` \<Number or HTMLTableRowElement> 숫자가 아닌 row 객체가 될 수 있다.
* `colIdx` \<Number> 컬럼인덱스
* `maskIdx` \<Number> 마스킹 함수의 위치값

- **Returns** \<[ADataMask](./ADataMask.md)> 또는 \<Array>
	- maskIdx 지정 안한 경우 ADataMask 인스턴스
    - maskIdx 지정을 한 경우 [ 해당 위치 마스킹함수, 해당 위치 마스킹 파라미터 ]
```js
grid.getDataMask(0, 0, 0); //[ ADataMask.Number.money.func, undefined ]
grid.getDataMask(0, 0); //ADataMask 인스턴스
```

<br/>


### enableScrollIndicator()

커스텀 스크롤바를 스크롤 영역에 표현하여 스크롤을 표현한다. 프로젝트 전체적으로 커스텀 스크롤바를 사용하고 싶은 경우에는 컴포넌트의 함수 대신 [afc.enableScrollIndicator();](./afc.md#-afc.enableScrollIndicator) 함수를 호출하면 된다.

```js
grid.enableScrollIndicator();
```

<br/>


### getRowData( row )

해당 로우에 저장된 데이터를 가져온다.

* `row` \<Number or HTMLTableRowElement> 숫자가 아닌 row 객체가 될 수 있다.
* **Returns** \<All> 로우에 저장된 데이터

```js
grid.setRowData(0, "rowdata");
grid.getRowData(0); //"rowdata"
```

<br/>

### setRowData( row, rowData)

해당 로우에 데이터를 저장한다.

* `row` \<Number or HTMLTableRowElement> 숫자가 아닌 row 객체가 될 수 있다.
* `rowData` \<All> 로우에 저장할 데이터

```js
grid.setRowData(0, "rowdata");
grid.getRowData(0); //"rowdata"
```

<br/>

### isHeadCell( cell )

헤더 셀여부를 가져온다.

* `cell` \<HTMLTableCellElement> 셀 엘리먼트
* **Returns** \<Boolean> 헤더 셀여부

<br/>

### setHeaderCellStyle( rowIdx, colIdx, key, value )

헤더 부분의 특정 셀의 특정 스타일을 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼인덱스
* `key` \<String> 스타일 키
* `value` \<String> 스타일 값

<br/>

### setHeaderCellStyleObj( rowIdx, colIdx, obj )

헤더 부분의 특정 셀의 스타일을 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼인덱스
* `obj` \<Object> 스타일 객체

<br/>


### getHeaderCellStyle( rowIdx, colIdx, key )

헤더 부분의 특정 셀의 스타일 값을 가져온다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼인덱스
* `key` \<String> 스타일 키
* **Returns** \<String> 스타일 값

<br/>


### setCellStyleObj( rowIdx, colIdx, obj )

바디 부분의 특정 셀의 스타일을 변경한다.

* `rowIdx` \<Number or HTMLTableRowElement> 로우 인덱스 또는 로우 엘리먼트
* `colIdx` \<Number> 컬럼인덱스
* `obj` \<Object> 스타일 객체

<br/>

### hideColumn( colIdx )

해당 열을 숨긴다.

* `colIdx` \<Number> 열 위치

<br/>

### showColumn( colIdx )

해당 열을 보여준다.

* `colIdx` \<Number> 열 위치

<br/>

### isColumnHided()

열 숨기기 여부를 가져온다.

* **Returns** \<Boolean> 열 숨김여부

<br/>

### toggleColumn( colIdx )

해당 열의 보임 여부에 따라 열을 숨기거나 보여준다.

* `colIdx` \<Number> 열 위치

<br/>


### setRotateColumns( colIdxArr )

여러 열을 돌아가며 보여주고 싶을 때 설정하는 함수. [rotateColumns](#rotatecolumns-index) 함수를 호출하면 colIdxArr 안의 열위치 순서대로 보여주게 된다.

* `colIdxArr` \<Number Array> 열 위치 배열
* **Returns** \<Number> 그리드에 로테이트 설정된 순서

```js
//3, 4, 5번째 열을 돌아가며 보여주는 설정
var index = this.grid.setRotateColumns([3,4,5]);
this.grid.rotateColumns(index);
```

<br/>

### rotateColumns( index )

[setRotateColumns](#setrotatecolumns-colidxarr) 함수를 이용해 로테이트를 설정한 정보에 맞게 여러 열을 돌아가며 보여주는 함수이다.

* `index` \<Number> 그리드에 로테이트 설정된 순서

```js
//3, 4, 5번째 열을 돌아가며 보여주는 설정
var index = this.grid.setRotateColumns([3,4,5]);
this.grid.rotateColumns(index);
```

<br/>

### removeRotateColumns( index )

그리드에 로테이트 설정된 순서에 해당하는 정보를 제거한다. 설정하면서 숨겨졌던 컬럼은 모두 보임처리되며 이후 설정된 순서는 갱신되지 않는다.
<br/>예를 들어 2,3열 4,5열을 각각 로테이트 설정한 경우 2,3열의 순서는 0이고 4,5열의 순서는 1이다. 2,3열에 해당하는 순서 0의 로테이트 정보를 제거하더라도 4,5열의 순서 1은 0으로 변경되지 않는다.

* `index` \<Number> 제거할 로테이트 설정 순서

```js
var rotate1 = this.grid.setRotateColumns([2,3]);
var rotate2 = this.grid.setRotateColumns([4,5]);
this.grid.removeRotateColumns(rotate1);

//먼저 설정한 rotate1 을 제거하더라도 rotate2는 그대로 사용가능하다.
this.grid.rotateColumns(rotate2);
```

<br/>


### isScroll()

상하 스크롤이 생긴 상태인지를 가져온다.

* **Returns** \<Boolean> 상하스크롤 유무

<br/>


### setData( data )

컴포넌트에 데이터를 세팅한다.

- `data` \<Array> 데이터 배열
    * [ [1,2,3], [4,5,6] ]
    * [ {col1: 1, col2: 2, col3: 3}, {col1: 4, col2: 5, col3: 6} ]

```js
//배열의 순서대로 데이터가 세팅된다.
this.grid.setData([ [1,2,3], [4,5,6] ]);

//그리드의 각 셀에 name 속성을 넣은 경우에는 아래와 같이 사용한다.
//name 속성을 넣지 않은 경우 Object 키 순서대로 데이터가 세팅된다.
this.grid.setData([ {col1: 1, col2: 2, col3: 3}, {col1: 4, col2: 5, col3: 6} ])
```

<br/>

### setDirectBackup( isDirect )

createBackup 을 호출하여 백업매니저를 사용하는 경우 로우를 추가되는 순간 화면에 표시되지 않고 바로 백업되도록 한다. addRow 인 경우만 유효

* `isDirect` \<Boolean> 바로 백업처리 여부

```js
//반드시 BackupManager를 Default Load Settings 에서 체크를 해줄 것!
this.grid.createBackup(50, 20);
for(var i=0; i<100; i++) this.grid.addRow([i, i, i]);
//setDirectBackup 호출 이전의 addRow 와 이후의 addRow 호출시 화면에서 로우 추가되는것을 확인해본다.
this.grid.setDirectBackup(true);
for(; i<110; i++) this.grid.addRow([i, i, i]);

```

<br/>

### showGridMsg( isShow, msg )

그리드 내부에 메시지를 표현하는 함수. 주로 데이터가 없는 경우에 사용한다.

* `isShow` \<Boolean> 보임여부
* `msg` \<String> 표현할 메시지 기본 : "no data"

```js
this.grid.showGridMsg(true);
this.grid.showGridMsg(false);
```

<br/>


### setSortFunc( func )

컬럼을 정렬할 때 값을 비교할 함수를 지정한다.

* `func` \<Function> 정렬함수

```js
this.grid.setSortFunc(function(a, b)
{
    if(a < b) return -1;
    else if(a > b) return 1;
    else return 0;
})
this.grid.sortColumn(0);
```

<br/>


### sortColumn( colInx, isAsc )

컬럼을 정렬한다.

* `colInx` \<Number> 컬럼 위치
* `isAsc` \<Boolean> 오름차순 여부 false: 내림차순

```js
this.grid.sortColumn(0, true);
```

<br/>


### overscrollBehavior( disableScrlManager )

그리드의 enableScrlManager 를 호출한 상태에서 그리드의 스크롤이 상단 또는 하단에 이르러서 더이상 스크롤이 되지 않을 때 부모 엘리먼트의 스크롤이 되어야 할때 호출하는 함수.
<br/>단, 상위 컴포넌트에서도 enableScrlManager 가 호출되어있어야 제대로 동작함.

* `disableScrlManager` 부모 엘리먼트 스크롤매니저

```js
var scrlMgr = this.view.enableScrlManagerY();
this.grid.enableScrlManager();
this.grid.overscrollBehavior(scrlMgr);
```

<br/>
<br/>

## Events

### dblclick( comp, info, e )

더블 클릭시 호출된다.

* `comp` \<[AComponent](./AComponent.md)> 컴포넌트
* `info` \<jQuery Object> 로우 또는 cell의 jQuery객체
* `e` \<Object> 이벤트 정보

### longtab( comp, info, e )

롱탭시 호출된다.

* `comp` \<[AComponent](./AComponent.md)> 컴포넌트
* `info` \<jQuery Object> 로우 또는 cell의 jQuery객체
* `e` \<Object> 이벤트 정보

### scrollbottom( comp, info, e )

그리드의 스크롤이 가장 아래에 도달하면 호출된다.

* `comp` \<[AComponent](./AComponent.md)> 컴포넌트
* `info` \<String> null
* `e` \<Object> 이벤트 정보

### scrolltop( comp, info, e )

그리드의 스크롤이 가장 위에 도달하면 호출된다.

* `comp` \<[AComponent](./AComponent.md)> 컴포넌트
* `info` \<String> null
* `e` \<Object> 이벤트 정보

### select( comp, info, e )

그리드의 로우 또는 셀을 선택시 호출된다.

* `comp` \<[AComponent](./AComponent.md)> 컴포넌트
* `info` \<Object> 로우 또는 cell의 jQuery객체
* `e` \<Object> 이벤트 정보

<br/>
<br/>

## Attribute

### Option
* **Hide Header:** 헤더 숨김 옵션
* **Single Select:** 단일 선택 옵션
* **Fullrow Select:** 로우템플릿 단위 선택 옵션
* **Selectable:** 선택기능 옵션
* **Flexible Row:** 표현되고 있는 로우 꽉차게 보이게 하는 옵션
* **Clear Row Template:** 초기화시 로우템플릿 제거 옵션. 제거 옵션인 경우 데이터 셋팅시에 로우가 추가되고 옵션을 해제한 경우 현재 로우에 데이터만 세팅된다.

<br/>
