# AGrid
> **Extends**: `AComponent`

그리드 컴포넌트

<br/>

## Properties

### columnCount

그리드의 컬럼 개수

* **Type**: `Number`
* **Default**: `0`

<br/>

### isStoppagation

그리드 터치시 상위로 이벤트 전달 여부

* **Type**: `Boolean`
* **Default**: `true`

<br/>


### realMap

특정 키에 대응하는 row 객체를 가지고 있는 맵. 수신된 리얼 데이터에서 키를 추출하여 realMap 으로부터 특정 row 객체를 얻어 화면을 갱신한다

* **Type**: `Object`
* **Default**: `null`

<br/>

### scrlManager

자체적으로 스크롤 기능을 제공해 주는 객체

* **Type**: `ScrollManager`
* **Default**: `null`

<br/>

### selectedCells

선택된 셀,행 집합

* **Type**: `Array`
* **Default**: `new Array()`

<br/>

### shiftSelectedCells



* **Type**: ``
* **Default**: ``

<br/>

### savedScrollPos



* **Type**: ``
* **Default**: ``

<br/>


### isScrollVisible



* **Type**: ``
* **Default**: ``

<br/>


### selectStyleName



* **Type**: ``
* **Default**: ``

<br/>


### hRowTmplHeight



* **Type**: ``
* **Default**: ``

<br/>


### rowTmplHeight



* **Type**: ``
* **Default**: ``

<br/>


### realField



* **Type**: ``
* **Default**: ``

<br/>


### scrollComp



* **Type**: ``
* **Default**: ``

<br/>


### shrinkInfo



* **Type**: ``
* **Default**: ``

<br/>


### isCheckScrl



* **Type**: ``
* **Default**: ``

<br/>


### lastSelectedCell



* **Type**: ``
* **Default**: ``

<br/>


### rotateColArr



* **Type**: ``
* **Default**: ``

<br/>


### sortFunc



* **Type**: ``
* **Default**: ``

<br/>

## Methods

### addColumn()

그리드에 컬럼을 추가한다. 마지막컬럼 뒤에 추가된다.

* **Usage**: 
```js
grid.addColumn();
```

<br/>

### addRow( rowData, isApplyBackupScroll )

rowData 를 그리드에 추가한다.

* **Returns**: JQueryObject

* **Parameters**: 
	* **`rowData`** {Array} 로우셋을 구성하는 배열 데이터
	* **`isApplyBackupScroll`** {Boolean} 바로 백업 스크롤을 적용할 지 여부, 일반적으로 모든 row 를 추가한 후 별도로 호출하므로 생략한다.

* **Usage**: 
```js
var data = [1,2,3,'abc'];
var row = grid.addRow(data);
//add할떄 생성된 row Object가 리턴된다.
```

<br/>

### addRowWithData( rowData, data, isApplyBackupScroll )

rowData 를 그리드에 추가하고 로우셋에 데이터를 저장한다.

* **Returns**: JQueryObject

* **Parameters**: 
	* **`rowData`** {Array} 로우셋을 구성하는 배열 데이터. 순차적으로 셀에 데이터 표시됨
	* **`data`** {Object} 로우셋에 데이터를 저장할 객체
	* **`isApplyBackupScroll`** {Boolean} 바로 백업 스크롤을 적용할 지 여부. 일반적으로 모든 row를 추가한 후 별도로 호출하므로 생략한다.

* **Usage**: 
```js
var rowData = [1, 2, 3, 'abc'];
var data = 'Row set에 저장하고싶은 데이터';
grid.addRowWithData(rowData, data);
```

<br/>

### applyBackupScroll()

그리드에 백업스크롤을 적용한다. <br/><br/>※ 그리드내부에 표현될 항목의 최대 개수와 복원 개수를 지정하여 항목을 무한히 추가하지 않고 관리한다.

* **Returns**: number

* **Usage**: 
```js
var result = grid.applyBackupScroll();
```

<br/>

### cellAddClass( rowIdx, colIdx, className )

그리드 바디의 특정 cell 에 스타일 클래스를 추가한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 로우인덱스 or 로우객체
	* **`colIdx`** {Number} 컬럼인덱스
	* **`className`** {String} 스타일 클래스명

* **Usage**: 
```js
grid.cellAddClass(1,1,'ClassName);
```

<br/>

### cellRemoveClass( rowIdx, colIdx, className )

그리드 바디의 특정 cell 에 스타일 클래스를 제거한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 로우인덱스 or 로우 객체
	* **`colIdx`** {Number} 컬럼인덱스
	* **`className`** {String} 스타일 클래스명

* **Usage**: 
```js
grid.cellRemoveClass(1,1,'ClassName');
```

<br/>

### changeRowCount( count, isHead )

그리드의 로우셋 카운트를 변경한다.

* **Parameters**: 
	* **`count`** {Number} 로우셋을 구성할 로우의 개수
	* **`isHead`** {Boolean} 헤더 여부

* **Usage**: 
```js
grid.changeRowCount(2);
```

<br/>

### checkScrollbar( isAdd )

스크롤바 존재 여부에 따라 headerTable 의 사이즈를 조정한다.

* **Parameters**: 
	* **`isAdd`** {Boolean} true / false

* **Usage**: 
```js
//add 인 경우는 스크롤바가 안 보이는 경우만 체크하고
//remove 인 경우는 스크롤바가 보이는 경우만 체크한다. 
grid.checkScrollbar(true);
```

<br/>

### clearAll()

그리드의 모든 텍스트와 background style을 삭제한다.

* **Usage**: 
```js
grid.clearAll();
```

<br/>

### clearContents()

그리드의 내부 데이터를 모두 지운다.

* **Usage**: 
```js
grid.clearContents();
```

<br/>

### clearSelected()

선택된 셀(행)을 모두 해제시킨다.(선택되지 않은 상태로 변경)

* **Usage**: 
```js
grid.clearSelected();
```

<br/>

### colIndexOfCell( cell )

파라미터로 넘어온 cell 의 column index 를 리턴한다.

* **Returns**: Number

* **Parameters**: 
	* **`cell`** {HTML Object} cell 객체

* **Usage**: 
```js
//선택된 셀의 column  index
var index = grid.colIndexOfCell(grid.getSelectedCells()[0]);
```

<br/>

### createBackup( maxRow, restoreCount )

백업 시스템이 작동하도록 BackupManager 를 생성한다.

* **Parameters**: 
	* **`maxRow`** {Number} 백업을 시작할 최대 row 개수
	* **`restoreCount`** {Number} 한번에 백업 및 복원할 row 개수

<br/>

### createRow( rowData )

로우를 추가하는 다른 함수에서 내부적으로 로우를 생성할떄 호출한다.

* **Returns**: $rowSet

* **Parameters**: 
	* **`rowData`** {Object} rowData

<br/>

### decreaseColSpan( tdDom )

컬럼이 삭제될 때 호출되는 함수이다. 제거되야할 td가 colspan을 가지고 있다면 하나줄여주거나 colspan을 제거한다.

* **Parameters**: 
	* **`tdDom`** {HTML Object} td Dom객체

<br/>

### deselectCell( cell )

파라미터로 넘어온 셀 또는 row를 선택해제해주고 배경색을 바꿔주는 함수이다.

* **Parameters**: 
	* **`cell`** {Object} cell 또는 row

<br/>

### destroyBackup()

백업 시스템을 중단하고 BackupManager 를 소멸시킨다.

<br/>

### enableScrlManager( leftSyncArea, rightSyncArea )

ScrollManager 의 자체 스크롤이 적용되도록 한다.

* **Parameters**: 
	* **`leftSyncArea`** {HTML Object} 그리드가 스크롤될 때 같이 움직일 좌측 스크롤 영역
	* **`rightSyncArea`** {HTML Object} 그리드가 스크롤될 때 같이 움직일 우측 스크롤 영역

<br/>

### findRowByCellData( nCol, data )

특정 컬럼의 특정 Object 값을 가지는 row 객체를 리턴하는 함수이다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`nCol`** {Number} 검색하고자 하는 컬럼
	* **`data`** {Object} 검색하고자 하는 Object

* **Usage**: 
```js
//3번째 컬럼이 가지고 잇는 데이터와 일치하는 row를 리턴한다.
var data = '검색하고자 하는 data Object';
var row = grid.findRowByCellData(3, data);
```

<br/>

### findRowByCellText( nCol, text )

특정 컬럼의 특정 문자열 값을 가지는 row 객체를 찾는다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`nCol`** {Number} 검색하고자 하는 컬럼
	* **`text`** {String} 검색하고자 하는 문자열

* **Usage**: 
```js
//3번쨰컬럼이 휴지인 Row를 리턴한다.
var row = grid.findRowByCellText(3, '휴지');
```

<br/>

### getAllLaiedComps()

그리드의 body에 추가된 컴포넌트들을 배열로 리턴한다.

* **Returns**: Array

<br/>

### getBodyColor()

그리드 바디의 배경색을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = grid.getBodyColor();
```

<br/>

### getBodyHeight( row )

그리드 바디의 특정 로우의 높이를 리턴한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스

* **Usage**: 
```js
//0번째 로우의 높이를 구하는 방법
var result = grid.getBodyHeight(0);
```

<br/>

### getCell( rowIdx, colIdx )

특정 idx 의 cell 을 얻어온다. rowIdx 값은 row 객체가 될 수 있다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} 컬럼 index

* **Usage**: 
```js
//그리드의 (2,3)의 cell객체를 받아온다.
var cell= grid.getCell(2,3);

//방금 추가한 row의 1번째 컬럼의 cell 객체를 받아온다.
var row = grid.addRow([1,2,3,'abc']);
var cell = grid.getCell(row, 1);
```

<br/>

### getCellBgColor2( cell )

해당 셀의 백그라운드 색을 리턴한다.

* **Returns**: String

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체

* **Usage**: 
```js
var cell = grid.getCell(4, 2);
var result = grid.getCellBgColor2(cell);
```

<br/>

### getCellData( rowIdx, colIdx )

특정 cell 의 data Object 를 얻어온다.

* **Returns**: Object

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} 컬럼 인덱스

* **Usage**: 
```js
//[3.1]위치의 cell의 data
var result = grid.getCellData(3,1);
```

<br/>

### getCellHeight( cell )

셀의 높이를 리턴한다.

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체

* **Usage**: 
```js
var cell = grid.getCell(1, 2);
var result = grid.getCellHeight(cell);
```

<br/>

### getCellIndex( cell )

해당 셀의 Row, Column 인덱스값을 배열로 리턴한다.

* **Returns**: Array

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체

* **Usage**: 
```js
var cell = grid.getCell(0, 1);
var result = grid.getCellIndex(cell);
// result -> [0,1]
```

<br/>

### getCellPos( cell )

해당셀의 위치를 배열로 리턴한다.

* **Returns**: Array

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체

* **Usage**: 
```js
var result = grid.getCellPos(cell);
//result -> [1,3];
```

<br/>

### getCellTag( rowIdx, colIdx )

특정 cell 의 태그를 얻어온다.

* **Returns**: HTML Object

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} 컬럼 인덱스

* **Usage**: 
```js
//[1,1]위치의 cell의 태그
var tag = grid.getCellTag(1,1);
```

<br/>

### getCellText( rowIdx, colIdx )

특정 cell 의 텍스트를 얻어온다.

* **Returns**: String

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} col index

* **Usage**: 
```js
//[2,2]위치의 cell의 텍스트
var text = grid.getCellText(2,2);
```

<br/>

### getCellTextColor2( cell )

해당 셀의 텍스트 컬러를 리턴한다.

* **Parameters**: 
	* **`cell`** {Object} cell 객체

* **Usage**: 
```js
var cell = grid.getCell(1, 1);
var result = grid.getCellTextColor2(cell);
```

<br/>

### getColumnCount()

column 의 개수를 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var result = grid.getColumnCount();
```

<br/>

### getDataByOption( rowInfo )

파라미터로 넘어온 객체의 엘리먼트에 저장되어 있는 데이터를 리턴하는 함수이다.

* **Returns**: Object

* **Parameters**: 
	* **`rowInfo`** {jQuery Object} 그리드 이벤트에서 넘어오는 Info

* **Usage**: 
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

* **Returns**: HTMLObject

* **Usage**: 
```js
var row = grid.getFirstRow();
```

<br/>

### getHeadColor()

헤더의 배경색을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = grid.getHeadColor();
```

<br/>

### getHeaderCell( rowIdx, colIdx )

특정 idx 의 header cell 을 얻어온다. rowIdx 값은 row 객체가 될 수 있다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} 컬럼 인덱스

* **Usage**: 
```js
// 그리드 헤더의 [1,3] 위치에 있는 cell
var cell = grid.getHeaderCell(1,3);
```

<br/>

### getHeaderRowCount()

그리드에서 헤더로우의 개수를 리턴한다.

* **Returns**: number

* **Usage**: 
```js
var result = grid.getHeaderRowCount();
```

<br/>

### getHeadHeight( row )

헤드의 특정 Row의 높이를 리턴한다.

* **Returns**: number

* **Parameters**: 
	* **`row`** {Number} 헤더 로우의 Index

* **Usage**: 
```js
var result = grid.getHeadHeight(1);
```

<br/>

### getHideHeaderCell()

hideThead의 특정 cell을 리턴한다.

* **Returns**: Object

* **Usage**: 
```js
//[1,1]위치의 cell 객체
var cell = grid.getHideHeaderCell(1,1);
```

<br/>

### getLastRow()

마지막 row 를 얻어온다.

* **Returns**: HTMLObject

* **Usage**: 
```js
var row = grid.getLastRow();
```

<br/>

### getRealKey( data )

getRealKey

* **Parameters**: 
	* **`data`** {String} data

<br/>

### getRow( rowIdx )

특정 인덱스의 row 를 얻어온다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`rowIdx`** {Number} Row Index

* **Usage**: 
```js
//1번 index의 Row
var row = grid.getRow(1);
```

<br/>

### getRowCount()

row 의 개수를 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var result = grid.getRowCount();
```

<br/>

### getRowDataByIndex( rowIdx )

그리드에서 파라미터로 넘어온 Row Index로 Row에 저장해둔 Data를 리턴한다.

* **Returns**: Row Object

* **Parameters**: 
	* **`rowIdx`** {Number} Row index

* **Usage**: 
```js
//2번째 index의 데이터를 리턴한다.
var data = grid.getRowDataByIndex(2);
```

<br/>

### getRowIndexByInfo( rowInfo )

로우 객체의 row index 를 리턴하는 함수이다.

* **Returns**: Number

* **Parameters**: 
	* **`rowInfo`** {jQuery Object} 이벤트 리스너에서 넘어오는 그리드 Info

* **Usage**: 
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

* **Returns**: String

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체

* **Usage**: 
```js
var result = grid.getRowParentTag(cell);
//result -> 'tHead' or 'tBody'
```

<br/>

### getRows( start, end )

특정 영역의 row 집합을 얻어온다.

* **Returns**: JQueryObject Array

* **Parameters**: 
	* **`start`** {Number} 시작 인덱스
	* **`end`** {Number} 끝 인덱스

* **Usage**: 
```js
//1~5번 index의 row 객체의 배열 (파라미터를 생략하면 모든 row를 리턴한다)
var rowArr = grid.getRows(1,5);
```

<br/>

### getRowSet( rowIdx )

그리드의 특정 RowSet을 리턴한다.

* **Returns**: Object

* **Parameters**: 
	* **`rowIdx`** {Number} Row Index

* **Usage**: 
```js
//2번째 index의 RowSet을 리턴한다.
var rowSet = gird.getRowSet(2);
```

<br/>

### getRowSetCount()

그리드 로우셋의 개수를 리턴한다.

* **Returns**: number

* **Usage**: 
```js
var result = grid.getRowSetCount();
```

<br/>

### getScrollPos()

스크롤의 위치값을 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var result = grid.getScrollPos();
```

<br/>

### getSelectedCells()

현재 선택되어져 있는 셀들을 배열로 리턴한다.

* **Returns**: Array

* **Usage**: 
```js
var cellArr = grid.getSelectedCells();
var cell = cellArr[0];
```

<br/>

### hideHeader()

그리드 헤더를 숨긴다.

* **Usage**: 
```js
grid.hideHeader();
```

<br/>

### indexOfCell( cell )

파라미터로 넘어온 cell 의 row 와 clumn 값을 배열로 리턴한다.

* **Returns**: Array

* **Parameters**: 
	* **`cell`** {HTML Object} index 값을 알고자 하는 cell 객체

* **Usage**: 
```js
// [3,1] 위치의 cell
var result = grid.indexOfCell(cell);
// 다음과 같이 배열로 리턴된다.  -> [3,1]
```

<br/>

### indexOfRow( row )

파라미터로 넘어온 row 의 index 를 리턴한다.

* **Returns**: Number

* **Parameters**: 
	* **`row`** {HTML Object} Row 객체

* **Usage**: 
```js
//방금 추가한 로우의 index를 받아온다.
var row = grid.addRow(data);
var index = grid.indexOfRow(row );
```

<br/>

### init( context, evtListener )

그리드를 생성하고 초기화 할때 호출한다. 그리드 구현 기본 알고리즘이 정의되어 있다.<br/>[헤더] 역할을 하는 header table 은 tbody 부분이 없으며 최상단으로 띄운다.<br/>[바디] 역할을 하는 table 은 thead 부분을 invisible 시켜 [헤더 table] 밑으로 들어가게 한다.  <br/>동적으로 생성할 경우에는 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {String} context에 매핑된 이벤트 수신자

* **Usage**: 
```js
var grid = new AGrid();
grid.init();
```

<br/>

### insertDefaultCell( table, row, col, isAfter )

기본셀을 추가하는 함수이다. 컬럼을 삽입하는 함수에서 호출해서 사용한다.

* **Parameters**: 
	* **`table`** {String} 영역(showThead, hideThead, tBody)
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스
	* **`isAfter`** {Boolean} true: after / false:before

<br/>

### insertRow( nRow, rowData )

그리드의 특정row 앞에 rowData 를 추가한다.

* **Returns**: JQueryObject

* **Parameters**: 
	* **`nRow`** {Number or HTML Object} Row index or Row Object
	* **`rowData`** {Array} 로우셋을 구성하는 배열 데이터

* **Usage**: 
```js
var rowData = [1,2,3,'abc'];
//10번째 index의 Row앞에 Row를 추가함.
grid.insertRow(10, rowData);

//특정 Row(해당 grid의 특정 Row Object라고 가정한다.) 앞에 Row를 추가함
var row;
grid.insertRow(row, rowData);
```

<br/>

### insertSingleCol( colIndex, isAfter )

그리드의 해당 컬럼위치에 컬럼을 삽입한다.

* **Parameters**: 
	* **`colIndex`** {Number} 컬럼 인덱스
	* **`isAfter`** {Boolean} true: after / false: before

* **Usage**: 
```js
//1번 컬럼의 다음에 새로운 컬럼을 삽입한다.
grid.insertSingleCol(1, true);

//1번 컬럼의 이전에 새로운 컬럼을 삽입한다.
grid.insertSingleCol(1, false);
```

<br/>

### insertSingleRow( rowIndex, isAfter, isHead )

그리드의 특정 위치에 로우를 삽입한다.

* **Parameters**: 
	* **`rowIndex`** {Number} 로우 인덱스
	* **`isAfter`** {Boolean} true: after / false: before
	* **`isHead`** {Boolean} true: header / false: body

* **Usage**: 
```js
grid.insertSingleRow(2);
```

<br/>

### isHeadCell( cell )

해당셀이 헤더의 셀인지 체크한 값을 리턴한다.

* **Returns**: boolean

* **Parameters**: 
	* **`cell`** {Object} cell의 객체

* **Usage**: 
```js
var result = grid.isHeadCell(cell);
```

<br/>

### isMoreScrollBottom()

하단으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = grid.isMoreScrollBottom();
```

<br/>

### isMoreScrollTop()

상단으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = grid.isMoreScrollTop();
```

<br/>

### isScroll()

현재 스크롤이 가능한 상태인지 여부를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = grid.isScroll();
```

<br/>

### isScrollBottom()

현재 그리드의 스크롤이 가장 하단인지 여부를 리턴한다.

* **Returns**: boolean

* **Usage**: 
```js
var result = grid.isScrollBottom();
```

<br/>

### isScrollTop()

현재 스크롤의 위치가 가장 상단인지 여부를 리턴한다.

* **Returns**: boolean

* **Usage**: 
```js
var result = grid.isScrollTop();
```

<br/>

### layComponent( acomp, row, col, width, height )

특정 셀(row,col)에 컴포넌트를 추가한다.

* **Parameters**: 
	* **`acomp`** {Object} 컴포넌트 객체(ex, label, button 등등 컴포넌트)
	* **`row`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`col`** {Number} Column Index
	* **`width`** {String} 가로크기. 생략시 100%
	* **`height`** {String} 세로크기. 생략시 100%

* **Usage**: 
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

* **Parameters**: 
	* **`acomp`** {AComponent} 컴포넌트객체(label, button 등등의 컴포넌트)
	* **`row`** {Number or HTML Object} Row index or Row Object
	* **`col`** {Number} Column Index
	* **`width`** {String} 가로크기. 생략시 100%
	* **`height`** {String} 세로크기. 생략시 100%

* **Usage**: 
```js
//그리드 헤더의 (2,1)에 버튼을 삽입하는 방법
//btn은 버튼 컴포넌트라고 가정한다.
grid.layHeaderComponent(btn, 2, 1);
```

<br/>

### loadCellView( rowIdx, colIdx, url )

해당 셀에 view를 생성하고 레이아웃 URL을 로드한다.

* **Returns**: AView

* **Parameters**: 
	* **`rowIdx`** {Number} 로우 인덱스
	* **`colIdx`** {Number} 컬럼 인덱스
	* **`url`** {String} 로드될 레이아웃의 URL

* **Usage**: 
```js
//[1,1]위치의 cell에  url의 뷰를 로드한다.
var view = grid.loadCellView(1,1,'view/name.lay');
```

<br/>

### loadGridDataMask()

그리드의 마스킹을 로드한다.

<br/>

### mergeCol( row, col, span )

그리드 바디의 특정 컬럼을 병합한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스
	* **`span`** {Number} 병합하려는 개수

* **Usage**: 
```js
//그리드 바디 [2,1]부터 3칸만큼의 컬럼을 병합한다.
grid.mergeCol(2,1,3);
```

<br/>

### mergeHeadCol( row, col, span )

그리드 헤더의 특정 컬럼을 병합한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스
	* **`span`** {Number} 병합하려는 개수

* **Usage**: 
```js
//그리드 헤더 [2,1]부터 3칸만큼의 컬럼을 병합한다.
grid.mergeHeadCol(2,1,3);
```

<br/>

### mergeHeadRow( row, col, span )

그리드 헤더의 특정 로우를 병합한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스
	* **`span`** {Number} 병합하는 개수

* **Usage**: 
```js
//그리드 헤더의 [2,1]부터 3칸만큼 병합한다.
grid.mergeHeadRow(2,1,3);
```

<br/>

### mergeRow( row, col, span )

그리드 바디의 특정 로우를 병합한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스
	* **`span`** {Number} 병합할 개수

* **Usage**: 
```js
//그리드 바디의 [2,1]부터 3칸만큼 병합한다.
grid.mergeRow(2,1,3);
```

<br/>

### moveRow( fromRow, toRow )

해당 로우를 특정위치로 이동한다.

* **Parameters**: 
	* **`fromRow`** {Number or HTML Object} Row Index or Row Object
	* **`toRow`** {Number or HTML Object} Row Index or Row Object

* **Usage**: 
```js
//그리드의 3번 index위치의 로우를 맨앞으로 이동한다.
grid.moveRow(3, 0);
```

<br/>

### prependRow( rowData )

rowData 를 그리드에 상단에 추가한다.

* **Returns**: JQueryObject

* **Parameters**: 
	* **`rowData`** {Array} 로우셋을 구성하는 배열 데이터

* **Usage**: 
```js
var data = [1,2,3,'abc'];
var row = grid.prependRow(data);
//add할떄 생성된 row Object가 리턴된다.
```

<br/>

### regCellEvent( $evtEle )

셀의 이벤트를 등록할떄 호출하는 함수이다.

* **Parameters**: 
	* **`$evtEle`** {jQuery Object} 이벤트 등록에서 예외적으로 dom element 가 아닌 jQuery 객체를 사용함

<br/>

### removeAll()

그리드의 모든 row 를 제거한다.

* **Usage**: 
```js
grid.removeAll();
```

<br/>

### removeColumn( colIdx )

그리드의 특정 컬럼을 삭제한다.

* **Parameters**: 
	* **`colIdx`** {Number} 컬럼 인덱스

* **Usage**: 
```js
grid.removeColumn(3);
```

<br/>

### removeFirst()

첫번째 row를 제거한다.

* **Usage**: 
```js
grid.removeFirst();
```

<br/>

### removeHeaderRow( rowIdx )

그리드 헤더의 특정 Row를 제거한다.

* **Parameters**: 
	* **`rowIdx`** {Number} Row index

* **Usage**: 
```js
//1번째 index의 헤더로우를 제거한다.
grid.removeHeaderRow(1);
```

<br/>

### removeLast()

마지막 Row를 제거한다.

* **Usage**: 
```js
grid.removeLast();
```

<br/>

### removeRow( rowIdx )

특정 row 를 그리드에서 제거한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} Row index or Row object

* **Usage**: 
```js
//1번 index의 row를 제거한다.
grid.removeRow(1);

//방금 추가한 로우를 제거한다.
var row = grid.addRow(data);
gird.removeRow(row);
```

<br/>

### removeRowSet( rowIdx )

특정 위치의 rowset을 제거하는 함수이다.

* **Parameters**: 
	* **`rowIdx`** {Number} 삭제하고자 하는 rowset 의 위치

* **Usage**: 
```js
//1번째 위치의 rowSet을 제거한다.
grid.removeRowSet(1);
```

<br/>

### restoreScrollPos()

저장해둔 그리드의 위치로 스크롤 시킨다.

* **Usage**: 
```js
grid.restoreScrollPos();
```

<br/>

### rowIndexOfCell( cell )

파라미터로 넘어온 cell 의 row index 를 리턴한다.

* **Returns**: Number

* **Parameters**: 
	* **`cell`** {HTML Object} cell 객체

* **Usage**: 
```js
//선택된 셀의 row index
var index = grid.rowIndexOfCell(grid.getSelectedCells()[0]);
```

<br/>

### saveScrollPos()

현재의 그리드 위치를 저장해 둔다.

* **Usage**: 
```js
grid.saveScrollPos();
```

<br/>

### scrollBottomManage()

스크롤의 최하단 위치 여부를 리턴하는 함수이다.

* **Returns**: Boolean

<br/>

### scrollImplement( leftSyncArea, rightSyncArea )

스크롤 매니저를 사용하는 경우에 스크롤 관련 처리를 구현하는 함수이다.

* **Parameters**: 
	* **`leftSyncArea`** {jQuery Object} 좌측 동기화 영역
	* **`rightSyncArea`** {jQuery Object} 우측 동기화 영역

<br/>

### scrollIntoArea( row, isAlignTop )

파라미터로 넘어온 row 객체가 보이도록 그리드를 스크롤 시킨다.

* **Parameters**: 
	* **`row`** {Number or HTML Object} 숫자 또는 row 객체가 될 수 있다.
	* **`isAlignTop`** {Boolean} row를 상단으로 해서 보일지 여부(false 일 경우 하단)

* **Usage**: 
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

* **Parameters**: 
	* **`offset`** {Number} 스크롤시킬 값

* **Usage**: 
```js
grid.scrollOffset(100);
grid.scrollOffset(-100)
```

<br/>

### scrollTo( pos )

그리드를 pos 의 위치로 스크롤 시킨다.

* **Parameters**: 
	* **`pos`** {Number} 스크롤의 위치값

* **Usage**: 
```js
grid.scrollTo(0);
grid.scrollTo(50);
```

<br/>

### scrollToBottom()

그리드를 최하단의 위치로 스크롤 시킨다.

* **Usage**: 
```js
grid.scrollToBottom();
```

<br/>

### scrollToCenter()

그리드를 중앙의 위치로 스크롤 시킨다.

* **Usage**: 
```js
grid.scrollToCenter();
```

<br/>

### scrollTopManage()

스크롤의 최상단 위치 여부를 리턴하는 함수이다

* **Returns**: Boolean

<br/>

### scrollToTop()

그리드를 최상단의 위치로 스크롤 시킨다.

* **Usage**: 
```js
grid.scrollToTop();
```

<br/>

### selectCell( cell, e )

특정 cell 또는 row 를 선택된 상태로 변경한다.(중복, 연속 선택 가능)

* **Parameters**: 
	* **`cell`** {HTML Object} 기본적으로 td 객체이며 isFullRowSelect 가 참이면 tr 객체(즉, 하나의 row)
	* **`e`** {Object} event Object

* **Usage**: 
```js
//0번 index의 로우를 선택 상태로 만든다.
var row = grid.getRow(0);
grid.selectCell(row);
```

<br/>

### setBodyColor( color )

그리드 바디의 배경색을 설정한다.

* **Parameters**: 
	* **`color`** {String} background-color css value값

* **Usage**: 
```js
grid.setBodyColor('#000000');
```

<br/>

### setBodyHeight( bodyHeight )

그리드 바디의 높이를 변경한다.

* **Parameters**: 
	* **`bodyHeight`** {String} 높이 값

* **Usage**: 
```js
grid.setBodyHeight('50px');
```

<br/>

### setCellBgColor2( cell, color )

해당 셀의 백그라운드 색상을 지정한다.

* **Parameters**: 
	* **`cell`** {Object} 셀 객체
	* **`color`** {String} Color RGB값

* **Usage**: 
```js
var cell = grid.getCell(1, 1);
grid.setCellBgColor2(cell, '#000000');
```

<br/>

### setCellData( rowIdx, colIdx, data )

그리드 바디의 특정 cell data를 변경한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} .
	* **`data`** {Object} .

<br/>

### setCellHAlign( cell, align )

해당 셀의 text-align을 세팅한다.

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체
	* **`align`** {String} text-align css value값

* **Usage**: 
```js
var cell = grid.getCell(1, 2);
grid.setCellHAlign(cell, 'center');
```

<br/>

### setCellHeight( cell, height )

셀의 높이를 변경한다. Row전체가 바뀌어여 되므로 내부적으로 td 대신 tr의 높이를 변경한다.

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체
	* **`height`** {String} 셀의 높이

* **Usage**: 
```js
var cell = grid.getCell(1, 2);
grid.setCellHeight(cell, '10%');
grid.setCellHeight(cell, 100);
grid.setCellHeight(cell, '100px');
```

<br/>

### setCellStyle( rowIdx, colIdx, style )

그리드 바디의 특정 cell 의 스타일을 변경한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} 컬럼 인덱스
	* **`style`** {Object} css 오브젝트

* **Usage**: 
```js
grid.setCellStyle(1,1,{'background-color':'black'});
```

<br/>

### setCellTag( rowIdx, colIdx, tag )

그리드 바디의 특정 cell 태그를 변경한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} 컬럼 인덱스
	* **`tag`** {HTML Object} 변경될 HTML Tag

* **Usage**: 
```js
//[1,1]위치의 cell의 tag를 변경한다.
var = 'html tag....';
grid.setCellTag(1,1, tag)
```

<br/>

### setCellText( rowIdx, colIdx, txt )

그리드 바디의 특정 cell 텍스트를 변경한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} 컬럼 인덱스
	* **`txt`** {String} 텍스트

* **Usage**: 
```js
//그리드 [1,1]위치의 body cell 텍스트를 '휴지'로 지정한다.
grid.setCellText(1,1,'휴지');
```

<br/>

### setCellTextColor( rowIdx, colIdx, color )

그리드 바디의 특정 cell 의 텍스트 색상을 변경한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 로우 인덱스 OR 로우 객체
	* **`colIdx`** {Number} 컬럼 인덱스
	* **`color`** {String} 컬러 RGB값

* **Usage**: 
```js
//그리드의 [0,3]위치의 셀의 색상을 변경한다.
grid.setCellTextColor(0,3,'#000000');
```

<br/>

### setCellTextColor2( cell, color )

해당 셀의 텍스트 컬러를 변경한다. 이 함수는 셀의 인덱스가 아닌 셀의 객체를 이용한다.

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체
	* **`color`** {String} 컬러 RGB값

* **Usage**: 
```js
//셀의 컬러를 변경한다.
var cell = grid.getCell(0, 0);
grid.setCellTextColor2(cell, '#000000');
```

<br/>

### setCellVAlign( cell, align )

해당 셀의 vertical-align값을 세팅한다.

* **Parameters**: 
	* **`cell`** {Object} 셀의 객체
	* **`align`** {String} vertical-align css value값

* **Usage**: 
```js
var cell = grid.getCell(1, 2);
grid.setCellVAlign(cell, 'middle');
```

<br/>

### setFlexibleRow( enable )

로우의 높이를 로우 개수에 맞게 균등 변경되도록 설정하는 함수이다.

* **Parameters**: 
	* **`enable`** {Boolean} true / false

* **Usage**: 
```js
//로우의 높이가 최소높이가 된 경우에는 더 이상 작아지지 않음.
grid.setFlexibleRow(true);
```

<br/>



### setHeadColor( color )

그리드 헤더의 배경색을 설정한다.

* **Parameters**: 
	* **`color`** {String} background-color css value값

* **Usage**: 
```js
grid.setHeadColor('#000000');
```

<br/>

### setHeaderCellText( rowIdx, colIdx, txt )

그리드 헤더의 특정 cell 텍스트를 변경한다.

* **Parameters**: 
	* **`rowIdx`** {Number or HTML Object} 숫자가 아닌 row 객체가 될 수 있다.
	* **`colIdx`** {Number} 컬럼인덱스
	* **`txt`** {String} 지정될 텍스트

* **Usage**: 
```js
//[2,2]위치의 header cell의 text를 '휴지'로 지정한다.
grid.setHeaderCellText(2,2,'휴지');
```

<br/>

### setHeadHeight( headHeight )

헤더의 높이를 변경한다.

* **Parameters**: 
	* **`headHeight`** {String} 높이 값

* **Usage**: 
```js
grid.setHeadHeight('50px');
```

<br/>




### setRealMap( realKey )

리얼맵이 작동하도록 환경을 셋팅한다. setQueryData 에서 사용(this.realKey, this.realMap 변수 설명 참조)

* **Parameters**: 
	* **`realKey`** {String} .

<br/>

### setRow( rowInx, rowData, start, end )

특정 로우의 텍스트를 세팅한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`rowData`** {Array} 텍스트 배열
	* **`start`** {Number} 시작 컬럼 인덱스(생략하면 로우 전체)
	* **`end`** {Number} 종료 컬럼 인덱스

* **Usage**: 
```js
//1번 로우의 텍스트를 각각[1,2,3]으로 지정
grid.setRow(1, [1,2,3]);
```

<br/>

### setRowByObj( rowInx, rowData, start, end )

그리드의 특정 로우의 텍스트와 타입을 세팅한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`rowData`** {Array} 오브젝트 배열
	* **`start`** {Number} 시작 컬럼 인덱스(생략하면 로우 전체)
	* **`end`** {Number} 종료 컬럼 인덱스

* **Usage**: 
```js
var data = [
　{ text: 'abc', type:'checkbox', checked:true },
　{ text: 'def', type:'checkbox', checked:false },
　{ text: 'qqq', type:'checkbox', checked:false }......];
grid.setRowByObj(1, data);
```

<br/>

### setScrollArrow( headHeight )

주로 모바일 장치에서 사용되는 함수이다. 리스트뷰 스크롤 표시가 없을 시 위, 아래 스크롤 아이콘을 표시한다.

* **Parameters**: 
	* **`headHeight`** {Number} 스크롤을 표시할 top 위치값

* **Usage**: 
```js
//파라미터를 생략하고 헤더를 숨기는 그리드 옵션을 활성화 할때 top을 0으로 세팅.
grid.setScrollArrow();
```

<br/>

### setScrollComp( acomp )

그리드의 스크롤과 관계되어 있는 컴포넌트를 세팅한다.

* **Parameters**: 
	* **`acomp`** {AComponent} 컴포넌트

<br/>


### splitCell( row, col )

그리드 바디의 특정 cell의 병합을 모두 해제한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스

* **Usage**: 
```js
//그리드 바디[2,1] 좌표의 cell의 병합을 모두 해제한다.
grid.splitCell(2,1);
```

<br/>

### splitCol( row, col )

그리드 바디의 특정 셀의 세로 병합을 해제한다.(colspan만 제거한다.)

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스

* **Usage**: 
```js
//그리드 바디 [1,1] 의 세로 병합을 해제함
grid.splitCol(1,1);
```

<br/>

### splitHeadCell( row, col )

그리드 헤더의 병합된 셀을 모두 분리한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스

* **Usage**: 
```js
//그리드 헤더 [2,1] 좌표의 cell의 병합을 모두 해제한다.
grid.splitHeadCell(2,1);
```

<br/>

### splitRow( row, col )

그리드 바디의 특정 cell의 가로병합을 해제한다. (rowspan만 제거)

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스

* **Usage**: 
```js
//그리드 바디 [1,1] 의 가로 병합을 해제함
grid.splitRow(1,1);
```

<br/>

### initVariables()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### createElement()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getCellComps()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getColumnComps()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getDataMask()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### loadGridShrinkInfo()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### loadGridNameKeyInfo()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### enableScrollIndicator()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getRowData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setRowData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### removeLast()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getRow()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### isHeadCell()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setHeaderCellStyle()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setHeaderCellStyleObj()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getHeaderCellStyle()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setCellStyleObj()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### hideColumn()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### showColumn()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### isColumnHided()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### toggleColumn()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setRotateColumns()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### rotateColumns()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### removeRotateColumns()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### isScroll()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### doRealPattern()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### doAddPattern()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### doUpdatePattern()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setDirectBackup()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getTopItem()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

 
### getBottomItem()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getCompStyleObj()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setCompStyleObj()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getMappingCount()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### showGridMsg()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### updatePosition()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setSortFunc()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### sortColumn()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### overscrollBehavior()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>

## Events

### dblclick( comp, info, e )

더블 클릭시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {jQuery Object} 로우 또는 cell의 jQuery객체
	* **`e`** {Object} 이벤트 정보

### longtab( comp, info, e )

롱탭시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {jQuery Object} 로우 또는 cell의 jQuery객체
	* **`e`** {Object} 이벤트 정보

### scrollbottom( comp, info, e )

그리드의 스크롤이 가장 아래에 도달하면 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

### scrolltop( comp, info, e )

그리드의 스크롤이 가장 위에 도달하면 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

### select( comp, info, e )

그리드의 로우 또는 셀을 선택시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} 로우 또는 cell의 jQuery객체
	* **`e`** {Object} 이벤트 정보

<br/>
<br/>

## Attribute

### Option
* **Hide Header:** 설명이 필요합니다.
* **Single Select:** 설명이 필요합니다.
* **Fullrow Select:** 설명이 필요합니다.
* **Selectable:** 설명이 필요합니다.
* **Flexable Row:** 설명이 필요합니다.
* **Clear Row Template:** 설명이 필요합니다.

<br/>
