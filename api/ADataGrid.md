# ADataGrid
> **Extends**: `AView`

ADataGrid

<br/>

## Methods

### addRowData( rowData, noUpdate )

마지막줄에 로우 데이터를 추가한다.

* **Parameters**: 
	* **`rowData`** {Object} 로우 데이터
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

* **Usage**: 
```js
dataGrid.addRowData(data);
```

<br/>

### addSelectObj()

addSelectObj

<br/>

### checkColPos()

좌우 스크롤시 보여지는 컬럼만 갱신하는 함수이다.

<br/>

### clearSelected()

선택되어져 있는 선택정보를 지운다.

<br/>

### colIndexOfSel( selObj )

select object 가 위치한 column 의 index 를 리턴한다.

* **Returns**: number

* **Parameters**: 
	* **`selObj`** {Object} 선택된 객체

* **Usage**: 
```js
var index = dataGrid.colIndexOfSel(selObj);
```

<br/>

### getCellData( rowInx, colInx )

셀의 데이터를 리턴한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`colInx`** {Number} 컬럼 인덱스

* **Usage**: 
```js
var result = dataGrid.getCellData(0,1);
```

<br/>

### getGridData()

데이터 배열을 리턴한다.

* **Returns**: Array

* **Usage**: 
```js
var result = dataGrid.getGridData();
```

<br/>

### getRowData( rowInx )

해당 로우의 데이터를 리턴한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스

* **Usage**: 
```js
var result = dataGrid.getRowData();
```

<br/>

### getSelectObjs()

선택된 모든 Object를 리턴한다.

* **Returns**: Object Array

* **Usage**: 
```js
var result = dataGrid.getSelectObjs();
```

<br/>

### getSelectRowArrs()

선택된 Object가 포함된 배열들을 배열로 리턴한다.

* **Returns**: Array

* **Usage**: 
```js
var result = dataGrid.getSelectRowArrs();
```

<br/>

### indexOfRowArr( rowArr )

row array 의 인덱스를 리턴한다.

* **Returns**: number

* **Parameters**: 
	* **`rowArr`** {Array} row array 는 object 담고 있는 1차원 배열이다.

* **Usage**: 
```js
var index = dataGrid.indexOfRowArr(rowArr);
```

<br/>

### insertRowData( rowInx, rowData, noUpdate )

로우 데이터를 삽입한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`rowData`** {Object} 로우 데이터
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

* **Usage**: 
```js
//3번째 index에 row data를 추가한다.
dataGrid.insertRowData(3, data);
```

<br/>

### mergeCellData( rowInx, colInx, cellData, noUpdate )

특정 셀의 기존 데이터와 새로운 데이터를 병합한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`colInx`** {Number} 컬럼 인덱스
	* **`cellData`** {Object} 셀 데이터
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

* **Usage**: 
```js
// [0,1] 위치의 기존 데이터와 새로운 데이터를 병합함.
dataGrid.mergeCellData(0,1,data);
```

<br/>

### mergeRowData( rowInx, rowData, noUpdate )

해당 로우 각각의 셀에 해당 데이터를 병합한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`rowData`** {Object} 로우 데이터
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

* **Usage**: 
```js
dataGrid.mergeRowData(1, data);
```

<br/>

### onGridSelect()

onGridSelect

<br/>

### onScrollX()

onScrollX

<br/>

### onScrollY()

onScrollY

<br/>

### removeAllRowData( noUpdate )

모든 데이터를 삭제한다 .

* **Parameters**: 
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

* **Usage**: 
```js
dataGrid.removeAllRowData();
```

<br/>

### removeRowData( rowInx, noUpdate )

해당 로우를 삭제한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

* **Usage**: 
```js
dataGrid.removeRowData(1);
```

<br/>

### removeSelectObj()

removeSelectObj

<br/>

### renderData()

renderData

<br/>

### resetInitRow()

resetInitRow

<br/>

### rowIndexOfSel( selObj )

select object가 위치한 row 의 index 를 리턴한다.

* **Returns**: number

* **Parameters**: 
	* **`selObj`** {Object} 선택된 객체

* **Usage**: 
```js
var index = dataGrid.rowIndexOfSel(selObj);
```

<br/>

### setCellData( rowInx, colInx, cellData, noUpdate )

특정 셀의 데이터를 설정한다.

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`colInx`** {Number} 컬럼 인덱스
	* **`cellData`** {Object} 셀 데이터
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

* **Usage**: 
```js
//[0,1] 좌표의 셀에 데이터를 세팅한다.
dataGrid.setCellData(0,1,data);
```

<br/>

### setGridData( dataArr2, noUpdate )

데이터 배열을 세팅한다. 데이터만 반영할지 렌더링까지 할지도 설정 가능하다.

* **Parameters**: 
	* **`dataArr2`** {Array} 데이터 배열
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true:렌더링안함 / false or 생략: 렌더링까지함)

* **Usage**: 
```js
//데이터 배열만 세팅하고 렌더링은 안함
dataGrid.setGridData(dataArr, true);
```

<br/>

### setRowData( rowInx, rowData, noUpdate )

특정 로우에 데이터를 세팅한다.(덮어 씌운다)

* **Parameters**: 
	* **`rowInx`** {Number} 로우 인덱스
	* **`rowData`** {Object} 로우 데이터
	* **`noUpdate`** {Boolean} 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

* **Usage**: 
```js
dataGrid.setRowData(1, data);
```

<br/>

### sortColumn( colInx )

특정 컬럼을 정렬한다.

* **Parameters**: 
	* **`colInx`** {Number} 컬럼 인덱스

* **Usage**: 
```js
dataGrid.sortColumn(1);
```

<br/>

### updateDataGrid()

데이터 배열의 변화값을 스크롤바에 반영하고 그리드의 각 값도 갱신한다.

* **Usage**: 
```js
dataGrid.updateDataGrid();
```

<br/>
<br/>
## Events


### dblclick( comp, info, e )

더블 클릭시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

### longtab( comp, info, e )

롱탭시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
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

데이터 그리드를 선택시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} 데이터 그리드에서 선택된 아이템 객체
	* **`e`** {Object} 이벤트 정보

<br/>

