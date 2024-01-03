# ADataGrid
> **Extends** `AView`

ADataGrid

<br/>

## Class Variables

<br/>

## Instance Variables

### dataArr2 \<Array>

전체 데이터배열

<br/>

### dataInx \<Number>

보여지는 데이터의 시작 인덱스

<br/>

### endCol \<Number>

보여지는 컬럼종료 위치

<br/>

### realField \<String>

실시간 키 데이터를 가져올 수 있는 필드명

<br/>

### realMap \<Object>

실시간 키별 로우를 저장하는 객체

<br/>

### renderRowCnt \<Number>

보여지는 로우 개수

<br/>

### selObjs \<Array>

선택한 데이터 객체를 저장하는 배열

<br/> 

### showArr2 \<Array>

보여지는 데이터 배열

<br/>

### sortColInx \<Number>

현재 정렬 설정된 컬럼 위치정보

* `default` -1

<br/>

### sortInfo \<Array>

정렬 오름, 내림차순 정보 배열

<br/>

### startCol \<Number>

보여지는 컬럼시작 위치

<br/>
<br/>

## Class Methods

<br/>

## Instance Methods

### addRowData( rowData, metaData, noUpdate )

마지막줄에 로우 데이터를 추가한다.

* `rowData`  \<Array> 객체를 원소로 갖는 배열 로우 데이터
* `metaData`  \<Array> 로우에 저장할 meta data
* `noUpdate`  \<Boolean> 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

```js
// 컬럼이 3개인 경우
var dataArr = [
    // 각 컬럼에 설정할 객체(이 때 text 키는 셀에 들어갈 문자열)
    {text: 'text1', ...},   // 0번째 컬럼 세팅 값
    {text: 'text2', ...},   // 1번째 컬럼 세팅 값
    {text: 'text3', ...},   // 2번째 컬럼 세팅 값
];

dataGrid.addRowData(dataArr);
```

<br/>

### addSelectObj( selObj, existCheck )

선택 데이터 객체를 추가한다. existCheck 값이 true 인 경우 이전에 선택된 데이터 객체가 있는 경우 제거만 한다.

* `selObj` \<Object> 선택 데이터 객체
* `existCheck` \<Boolean> 존재 체크 여부

<br/>

### checkColPos()

좌우 스크롤시 보여지는 컬럼만 갱신하기 위해 시작, 종료 컬럼위치를 구한다.

<br/>

### clearSelected()

기존에 선택되어져 있는 선택정보를 지운다.

<br/>

### colIndexOfSel( selObj )

select object 가 위치한 column 의 index 를 리턴한다.

* `selObj`  \<Object> 선택된 객체
* **Returns** \<Number> 컬럼 위치

```js
var index = dataGrid.colIndexOfSel(selObj);
//------------------------------------------------------
// 0 (객체가 존재하는 column의 index)
```

<br/>

### filter( filterFunc, updateType )

원본 데이터 배열을 필터링한다.

* `filterFunc` \<Function> 각 요소를 시험할 함수. true를 반환하면 요소를 유지하고, false를 반환하면 버립니다. 다음 세 가지 매개변수를 받습니다.
* `updateType` \<Number> 0: (update, init), 1: (noupdate, init), 2: (update,noinit)

<br/>

### getCellData( rowInx, colInx )

전체 데이터 배열 중 특정 위치 셀의 데이터를 가져온다.

* `rowInx`  \<Number> 로우 인덱스
* `colInx`  \<Number> 컬럼 인덱스
* **Returns** \<Object> 셀 데이터

```js
var result = dataGrid.getCellData(0,1);
//------------------------------------------------------
// {text: (0, 1) 위치에 세팅된 값, ...}
```

<br/>

### getCheckedIndices( colInx )

데이터 목록 중 특정 위치의 컬럼 checkbox가 checked 인 row 들을 배열로 리턴하는 함수</br>
이 때 addRowData() 또는 setGridData() 시에 type 을 'checkbox' 로 해주어야 함

* `colInx` \<Number> checkbox 가 존재하는 컬럼 인덱스
* **Returns** \<Array>

```js
// 체크박스 데이터 예시
var dataArr = [
    {type: 'checkbox'},
    {text: 'checkboxRow'},
    ...
];

...

var checkedDataArr = dataGrid.getCheckedIndices(0);
//------------------------------------------------------
// [0, 1, 2]
```

<br/>

### getData()

필터링 되지 않은 원본 데이터 배열을 리턴한다.

* **Returns** \<Array>

```js
var resultArr = dataGrid.getData();
//------------------------------------------------------
// [
//    {text: 'data1', value: 'value1'},
//    {text: 'data2', value: 'value2'},
//    ...
// ]
```

<br/>

### getFilteredData()

필터링 된 전체 데이터 배열을 리턴한다.

* **Returns** \<Array>

```js
var resultArr = dataGrid.getFilteredData();
//------------------------------------------------------
// [
//    {text: 'filteredData1', value: 'filteredValue1'},
//    {text: 'filteredData2', value: 'filteredValue2'},
//    ...
// ]
```

<br/>

### getFilteredRowData( rowInx )

필터링 된 데이터 중 특정 위치의 로우 데이터만 가져온다.

* `rowInx` \<Number> 로우 위치
* **Returns** \<Array> 

```js
var resultArr = dataGrid.getFilteredRowData(0);
//------------------------------------------------------
// [
//    {text: 'filteredData1', value: 'filteredValue1'},
//    {text: 'filteredData2', value: 'filteredValue2'},
//    ...
// ]
```

<br/>


### getGridData()

필터링 되지 않은 원본 데이터 배열을 리턴한다.

* **Returns** \<Array>

```js
var resultArr = dataGrid.getData();
//------------------------------------------------------
// [
//    {text: 'data1', value: 'value1'},
//    {text: 'data2', value: 'value2'},
//    ...
// ]
```

<br/>

### getMetaData( row )

특정 위치의 로우에 저장해 놓은 meta data 를 가져온다.

* `row` \<Number or Object> 로우 위치 또는 로우
* **Returns** \<All> 로우에 저장해놓은 meta data

```js
var metaDataArr = dataGrid.getMetaData(0);
//------------------------------------------------------
// [
//    {value: 'value1'},
//    {value: 'value2'},
//    ...
// ]
```

<br/>

### getPivotGrid()

고정 그리드가 있다면 그리드 컴포넌트를 가져온다.

* **Returns** \<AGrid> 고정 그리드

```js
var pivotGrid = dataGrid.getPivotGrid();
//------------------------------------------------------
// [AGrid]
```

<br/>


### getRealKey( data )

데이터 중 setRealMap을 통해 지정한 실시간 필드명에 해당하는 값을 가져온다.

* `data`  \<Object> 데이터
* **Returns** \<String> 실시간 키값

<br/>

### getRowData( rowInx )

해당 로우의 데이터를 리턴한다.

* `rowInx`  \<Number> 로우 인덱스

```js
var result = dataGrid.getRowData();
//------------------------------------------------------
//[
//    {text: 'data1', value: 'value1'},
//    {text: 'data2', value: 'value2'},
//    ...
//]
```

<br/>

### getSelectObjs()

선택된 모든 Object를 리턴한다.

* **Returns** \<Object Array> 선택된 객체들을 저장한 배열

```js
var result = dataGrid.getSelectObjs();
```

<br/>

### getSelectRowArrs()

선택된 Object가 포함된 로우들을 배열로 리턴한다.

* **Returns** \<Array> 선택 로우들을 저장한 배열

```js
var result = dataGrid.getSelectRowArrs();
```

<br/>

### indexOfRowArr( rowArr )

전체 데이터 중 특정 로우 배열의 인덱스를 리턴한다.

* `rowArr`  \<Array> row array 는 object 담고 있는 1차원 배열이다.
* **Returns** \<number> 로우 위치

```js
var index = dataGrid.indexOfRowArr(rowArr);
```

<br/>

### insertRowData( rowInx, rowData, metaData, noUpdate )

로우 데이터를 삽입한다.

* `rowInx`  \<Number> 로우 인덱스
* `rowData`  \<Object> 로우 데이터
* `metaData`  \<Object> 로우에 저장할 meta data
* `noUpdate`  \<Boolean> 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

```js
// 3번째 index에 row data를 추가한다.
// 데이터 형식은 add 할 때와 같음
dataGrid.insertRowData(3, data);
```

<br/>

### mergeCellData( rowInx, colInx, cellData, noUpdate )

특정 셀의 기존 데이터와 새로운 데이터를 병합한다.

* `rowInx`  \<Number> 로우 인덱스
* `colInx`  \<Number> 컬럼 인덱스
* `cellData`  \<Object> 셀 데이터
* `noUpdate`  \<Boolean> 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

```js
// [0,1] 위치의 기존 데이터와 새로운 데이터를 병합함.
dataGrid.mergeCellData(0, 1, data);
```

<br/>

### mergeRowData( rowInx, rowData, noUpdate )

해당 로우 각각의 셀에 해당 데이터를 병합한다.

* `rowInx`  \<Number> 로우 인덱스
* `rowData`  \<Object> 로우 데이터
* `noUpdate`  \<Boolean> 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

```js
dataGrid.mergeRowData(1, data);
```

<br/>

### removeAllRowData( noUpdate )

모든 데이터를 삭제한다 .

* `noUpdate`  \<Boolean> 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

```js
dataGrid.removeAllRowData();
```

<br/>

### removeRowData( rowInx, noUpdate )

해당 로우를 삭제한다.

* `rowInx`  \<Number> 로우 인덱스
* `noUpdate`  \<Boolean> 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

```js
dataGrid.removeRowData(1);
```

<br/>

### removeSelectObj( selObj )

선택된 데이터 객체를 저장 배열에서 제거한다.

* `selObj` \<Object> 제거할 데이터 객체
* **Returns** \<Number> 제거한 데이터 객체 위치(없는 경우 -1)

<br/>

### renderData()

현재의 index 및 offset 정보로 부터 데이터를 얻어와 그리드 셀의 각 값을 갱신한다.
즉, 화면을 다시 그리는 일을 한다.

<br/>

### resetInitRow()

모든 row 를 지우고 현재의 데이터와 상황에 맞게 row 를 다시 추가한다.

<br/>

### rowIndexOfSel( selObj )

전체 데이터 중 select object가 위치한 row 의 index 를 리턴한다.

* `selObj`  \<Object> 선택된 객체
* **Returns** \<number> 로우 위치

```js
var index = dataGrid.rowIndexOfSel(selObj);
```

<br/>

### setCellData( rowInx, colInx, cellData, noUpdate )

특정 셀의 데이터를 설정한다.

* `rowInx`  \<Number> 로우 인덱스
* `colInx`  \<Number> 컬럼 인덱스
* `cellData`  \<Object> 셀 데이터
* `noUpdate`  \<Boolean> 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

```js
//[0,1] 좌표의 셀에 데이터를 세팅한다.
dataGrid.setCellData(0, 1, data);
```

<br/>

### setData( dataArr )

컴포넌트에 데이터를 세팅한다. 

- `dataArr` \<Array> 컴포넌트에 세팅할 데이터 배열
```js
this.dataGrid.setData([
    [1,2,3],
    [4,5,6]
]);
```

<br/>

### setGridData( dataArr, noUpdate )

데이터 배열을 세팅한다. 데이터만 반영할지 렌더링까지 할지도 설정 가능하다.

* `dataArr`  \<Array> 데이터 배열
* `noUpdate`  \<Boolean> 렌더링 여부 ( true:렌더링안함 / false or 생략: 렌더링까지함)

```js
//데이터 배열만 세팅하고 렌더링은 안함
dataGrid.setGridData(dataArr, true);
```

<br/>

### setMetaData( row, metaData )

특정 위치의 로우에 meta data 를 저장한다.

* `row` \<Number or Object> 로우 위치 또는 로우
* `metaData` \<All> 로우에 저장해놓을 meta data

<br/>

### setPivotGrid( grid )

고정 그리드를 지정한다.

* `grid` \<AGrid> 고정 그리드로 사용할 컴포넌트

<br/>

### setRealMap( realField )

리얼맵이 작동하도록 환경을 셋팅한다. setQueryData 에서 사용(this.realMap 변수 설명 참조)

* `realField` \<String> 실시간 키 수신 필드

<br/>

### setRowData( rowInx, rowData, metaData, noUpdate )

특정 로우에 데이터를 세팅한다.(덮어 씌운다)

* `rowInx`  \<Number> 로우 인덱스
* `rowData`  \<Object> 로우 데이터
* `metaData`  \<Object> 로우에 저장할 meta data
* `noUpdate`  \<Boolean> 렌더링 여부 ( true : 렌더링 안함 / false or 생략: 렌더링함)

```js
// 데이터 형식은 addRowData() 와 같음
dataGrid.setRowData(1, data);
```

<br/>

### sortColumn( colInx )

특정 컬럼을 정렬한다.

* `colInx`  \<Number> 컬럼 인덱스

```js
dataGrid.sortColumn(1);
```

<br/>

### updateDataGrid()

데이터 배열의 변화값을 스크롤바에 반영하고 그리드의 각 값도 갱신한다.

```js
dataGrid.updateDataGrid();
```

<br/>
<br/>

## Events

### dblclick( comp, info, e )

더블 클릭시 호출된다.

* `comp`  \<AComponent> 컴포넌트
* `info`  \<Object>
* `e`  \<Object> 이벤트 정보

### longtab( comp, info, e )

롱탭시 호출된다.

* `comp`  \<AComponent> 컴포넌트
* `info`  \<Object> 
* `e`  \<Object> 이벤트 정보

### scrollbottom( comp, info, e )

그리드의 스크롤이 가장 아래에 도달하면 호출된다.

* `comp`  \<AComponent> 컴포넌트
* `info`  \<Object>
* `e`  \<Object> 이벤트 정보

### scrolltop( comp, info, e )

그리드의 스크롤이 가장 위에 도달하면 호출된다.

* `comp`  \<AComponent> 컴포넌트
* `info`  \<Object> 
* `e`  \<Object> 이벤트 정보

### select( comp, info, e )

데이터 그리드를 선택시 호출된다.

* `comp`  \<AComponent> 컴포넌트
* `info`  \<Object> 데이터 그리드에서 선택된 아이템 객체
* `e`  \<Object> 이벤트 정보

<br/>
<br/>

## Atrtribute

### Option

* **Pivot Grid :** 열고정그리드 사용여부
* **Hide H-Scrollbar:** 좌우 스크롤바 숨김여부

<br/>
