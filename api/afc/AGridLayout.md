# AGridLayout
> **Extends**: `ALayout`

insertView 함수를 호출하여 ViewDirection 방향으로 뷰를 추가한다.<br/>추가하려는 뷰의 높이가 100% 이면 남은 공간 전체를 차지한다.<br/>auto 나 픽셀을 직접 지정한 경우는 원하는 높이가 된다.

<br/>

## Properties


### $table



* **Type**: ``
* **Default**: ``

<br/>


### $body



* **Type**: ``
* **Default**: ``

<br/>


### $colGroup



* **Type**: ``
* **Default**: ``

<br/>
<br/>


## Methods

### createLayout( rowCount, colCount, rowSizeArr, colSizeArr )

레이아웃의 틀을 생성합니다.

* **Parameters**: 
	* **`rowCount`** {Number} 로우의 갯수
	* **`colCount`** {Number} 컬럼의 갯수
	* **`rowSizeArr`** {Array} 로우의 사이즈 배열
	* **`colSizeArr`** {Array} 컬럼의 사이즈 배열

<br/>

### eachChild( callback, isReverse )

각 자식들로 특정 함수를 실행 시킵니다. 콜백 함수에 실행시키고자 하는 함수를 넣습니다.

* **Parameters**: 
	* **`callback`** {Function} 콜백함수
	* **`isReverse`** {Boolean} 역순 처리 여부

* **Usage**: 
```js
grid.eachChild(function(acomp){
                console.log(acomp);
}, true);
```

<br/>

### getAllLayoutComps()

레이아웃의 모든 컴포넌트를 배열로 리턴한다.

* **Returns**: Array

* **Usage**: 
```js
var resultArr = grid.getAllLayoutComps();
```

<br/>

### getCell( row, col )

특정 포지션의 cell을 리턴한다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
var cell = gridLayout.getCell(1,2);
```

<br/>

### getCellAlign( row, col )

그리드 레이아웃 특정 위치의 셀의 text-align값을 리턴한다.

* **Returns**: String

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
var reuslt = gridLayout.getCellAlign(0,0);
```

<br/>

### getCellPadding( row, col )

특정 포지션 셀의 Padding 값을 리턴 합니다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
var result = gridLayout.getCellPadding(0,0);
```

<br/>

### getCellValign( row, col )

특정 포지션 셀의 verticalAlign값을 리턴한다.

* **Returns**: String

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
var result = gridLayout.getCellValign(0,0);
```

<br/>

### getColGroupItem( col )

그리드 레이아웃의 컬럼그룹을 리턴한다.

* **Parameters**: 
	* **`col`** {Number} 컬럼 인덱스

* **Usage**: 
```js
var item = gridLayout.getColGroupItem(1);
```

<br/>

### getColGroupItems()

그리드 레이아웃의 컬럼의 개수를 리턴한다.

* **Returns**: number

* **Usage**: 
```js
var count = gridLayout.getColGroupItems();
```

<br/>

### getCols()

컬럼의 개수를 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var result = gridLayout.getCols();
```

<br/>

### getColSize( col )

특정 컬럼의 너비값을 리턴한다.

* **Returns**: Number

* **Parameters**: 
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
//1번 index 컬럼의 너비값을 리턴한다.
var result = gridLayout.getColSize(1);
```

<br/>

### getLayoutAlign()

레이아웃의 text-align값을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = gridLayout.getLayoutAlign();
```

<br/>

### getLayoutComp( row, col )

특정 인덱스의 컴포넌트를 리턴한다.

* **Returns**: AComponent

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
var result = gridLayout.getLayoutComp(1,1);
```

<br/>

### getLayoutPadding()

레이아웃의 Padding 값을 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var result = gridLayout.getLayoutPadding();
```

<br/>

### getRow( row )

특정 인덱스의 로우를 리턴한다.

* **Returns**: Object

* **Parameters**: 
	* **`row`** {Number} row 인덱스

* **Usage**: 
```js
var row = gridLayout.getRow(2);
```

<br/>

### getRows()

그리드 레이아웃 전체 로우의 개수를 리턴합니다.

* **Returns**: Number

* **Usage**: 
```js
var count = gridLayout.getRows();
```

<br/>

### getRowSize( row )

특정 로우의 높이값을 리턴한다.

* **Returns**: Number

* **Parameters**: 
	* **`row`** {Number} row 인덱스

* **Usage**: 
```js
var result = gridLayout.getRowSize(1);
```

<br/>

### initLayoutComp( evtListener )

레이아웃 내부의 컴포넌트들을 초기화 합니다.

* **Parameters**: 
	* **`evtListener`** {Object} context 에 매핑된 이벤트 수신자

<br/>

### insertCol( col, isAfter )

특정 컬럼 앞, 또는 뒤에 새로운 컬럼을 삽입합니다.

* **Parameters**: 
	* **`col`** {Number} col 인덱스
	* **`isAfter`** {Boolean} 앞인지 뒤인지 여부

* **Usage**: 
```js
gridLayout.insertCol(2);
```

<br/>

### insertRow( row, isAfter )

그리드 레이아웃에서 특정 로우 앞, 또는 뒤에 새로운 로우를 삽입한다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`isAfter`** {Boolean} 앞인지 뒤인지 여부

* **Usage**: 
```js
gridLayout.insertRow(1, true);
```

<br/>

### layComponent( acomp, cell, width, height )

특정 셀에 컴포넌트를 추가한다. 셀을 지정해주지 않으면 빈자리에 추가된다.

* **Parameters**: 
	* **`acomp`** {AComponent} 추가 할 컴포넌트
	* **`cell`** {Object} 셀
	* **`width`** {Number} 너비
	* **`height`** {Number} 높이

* **Usage**: 
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

* **Parameters**: 
	* **`acomp`** {AComponent} 추가 할 컴포넌트
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스
	* **`width`** {Number} 너비 (생략하면 100%)
	* **`height`** {Number} 높이 (생략하면 100%)

* **Usage**: 
```js
var btn = new AButton(); // 버튼컴포넌트를 [2,1]위치에 삽입한다.
btn.init();
var item = gridLayout.layComponentAt(btn, 2, 1);
```

<br/>

### mergeCol( row, col, span )

그리드 레이아웃의 특정 컬럼을 병합한다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스
	* **`span`** {Number} 병합하려는 개수

* **Usage**: 
```js
//그리드 레이아웃 [1,1]위치의 셀로부터 2칸을 세로로 병합한다.
gridLayout.mergeCol(1,1,2);
```

<br/>

### mergeRow( row, col, span )

그리드 레이아웃의 특정 로우를 병합한다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스
	* **`span`** {Number} 병합하려는 개수

* **Usage**: 
```js
//그리드 레이아웃의 [2,1] 부터 3칸을 가로로 병합함.
gridLayout.mergeRow(2,1,3);
```

<br/>

### reduceColSpanCount( row, col )

특정 셀의 colspan을 감소시킨다. 1이하일 경우에는 제거한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스
	* **`col`** {Number} 컬럼 인덱스

* **Usage**: 
```js
gridLayout.removeCol(2,2);
```

<br/>

### removeCol( col )

그리드 레이아웃의 특정 컬럼을 삭제한다. 단, 숨겨진 cell에 colspan이 존재하면 안된다.

* **Parameters**: 
	* **`col`** {Number} 컬럼 인덱스

* **Usage**: 
```js
gridLayout.removeCol(2);
```

<br/>

### removeRow( row )

그리드 레이아웃의 특정 로우를 삭제한다.

* **Parameters**: 
	* **`row`** {Number} 로우 인덱스

* **Usage**: 
```js
gridLayout.removeRow(2);
```

<br/>

### setCellAlign( row, col, align )

그리드 레이아웃 특정 셀의 text-align값을 설정한다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스
	* **`align`** {String} text-align css value값

* **Usage**: 
```js
//그리드 레이아웃의 [1,1]좌표에 있는 셀의 text-align css value값을 center로 지정
gridLayout.setCellAlign(1,1,'center');
```

<br/>

### setCellPadding( row, col, padding )

그리드 레이아웃 특정 셀의 패딩값을 설정한다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스
	* **`padding`** {Number} 패딩값

* **Usage**: 
```js
//그리드레이아웃 [1,2] 좌표의 패딩을 5로 지정
gridLayout.setCellPadding(1,2,5);
```

<br/>

### setCellValign( row, col, align )

그리드 레이아웃 특정 셀의 vertical-align를 설정한다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스
	* **`align`** {String} vertical-align css value 값

* **Usage**: 
```js
//그리드 레이아웃 [1,1]위치의 셀의 vertical-align값을 middle로 지정
gridLayout.setCellValign(1,1,'middle');
```

<br/>

### setCols( cols )

컬럼의 개수를 설정한다.

* **Parameters**: 
	* **`cols`** {Number} 개수

* **Usage**: 
```js
gridLayout.setCols(5);
```

<br/>

### setColsDivPercent()

컬럼의 크기를 퍼센트로 설정합니다.

<br/>

### setColSize( col, size )

그리드 레이아웃 특정 컬럼의 width를 설정한다.

* **Parameters**: 
	* **`col`** {Number} col 인덱스
	* **`size`** {Number} 크기

* **Usage**: 
```js
grid.setColSize(1, '20px');
```

<br/>

### setLayoutAlign( align )

레이아웃의 text-align 값을 설정한다.

* **Parameters**: 
	* **`align`** {String} text-align css value값

* **Usage**: 
```js
gridLayout.setLayoutAlign('center');
```

<br/>

### setLayoutPadding( padding )

그리드 레이아웃의 패딩값을 설정한다.

* **Parameters**: 
	* **`padding`** {Object} padding값

* **Usage**: 
```js
gridLayout.setLayoutPadding(5);
```

<br/>

### setLayoutSize( rowSizeArr, colSizeArr )

레이아웃의 각 로우와 셀의 크기를 설정한다.

* **Parameters**: 
	* **`rowSizeArr`** {Array} 로우 사이즈 배열
	* **`colSizeArr`** {Array} 컬럼 사이즈 배열

* **Usage**: 
```js
var size = [50, 20, '30px'];
gridLayout.setLayoutSize(size, size);
```

<br/>

### setRows( rows )

로우의 개수를 설정합니다.

* **Parameters**: 
	* **`rows`** {Number} 개수

* **Usage**: 
```js
gridLayout.setRows(5);
```

<br/>

### setRowsDivPercent()

로우의 크기를 퍼센트로 설정합니다.

<br/>

### setRowSize( row, size )

그리드 레이아웃의 특정 로우의 높이를 설정합니다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`size`** {Number} 크기

* **Usage**: 
```js
gridLayout.setRowSize(1, '15px');
```

<br/>

### splitCell( row, col )

특정위치의 셀이 병합되어 있다면 모두 분리한다.

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
gridLayout.splitCell(0,1);
```

<br/>

### splitCol( row, col )

그리드 레이아웃의 특정 셀이 세로로 병합되어 있다면 분리한다. (해당 셀의 colspan을 제거한다)

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
gridLayout.splitCol(2,2);
```

<br/>

### splitRow( row, col )

그리드 레이아웃의 특정 셀이 가로로 병합되어 있다면 분리한다. (해당 셀의 rowspan을 제거한다)

* **Parameters**: 
	* **`row`** {Number} row 인덱스
	* **`col`** {Number} col 인덱스

* **Usage**: 
```js
gridLayout.splitRow(1,1);
```

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### convertColInfo()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>

## Property

### Rows 
현재 로우의 총 개수  

### Cols  
현재 컬럼의 총 개수  

### Cell Height 
선택한 셀의 높이를 설정하는 속성입니다.  

### Cell Width  
선택한 셀의 넓이를 설정하는 속성입니다.  
 
### Cell Padding 
선택한 셀의 패딩을 설정하는 속성입니다.  

### Cell Color 
선택한 셀의 배경색을 설정하는 속성입니다.    

### Cell Borders
선택한 셀의 모서리를 설정하는 속성입니다.
   
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp101.png) : 선택된 셀의 top line만 border를 설정합니다.  
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp102.png) : 선택된 셀의 horizontal middle line 만 border를 설정합니다.  
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp103.png) : 선택된 셀의 bottom line만 border를 설정합니다. 
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp104.png) : 선택된 셀의 left line만 border를 설정합니다. 
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp105.png) : 선택된 셀의 vertical middle line만 border를 설정합니다. 
* ![](https://wikidocs.net/images/page/72805/gridlayout-comp106.png) : 선택된 셀의 right line만 border를 설정합니다. 
* **All:** 선택된 셀의 모든 border를 설정합니다. 
* **OutLine:** 선택된 셀의 테두리 line만 border를 설정합니다. 
* **Clear:** 선택된 셀에 적용된 border를 초기화합니다.     
  
### Cell Context Menu   
셀을 우클릭하면 나타나는 메뉴입니다.
  
* **Merge:** 현재 선택한 셀들을 하나의 셀로 합병합니다. 
* **Split:** Merge 된 셀을 Merge 전의 셀들로 분리합니다. 
* **Insert Row:** 현재 선택한 셀의 앞에 Row를 추가합니다. 
* **Delete Row:** 현재 선택한 셀의 Row를 삭제합니다. 
* **Insert Col:** 현재 선택한 셀의 앞에 Column을 추가합니다. 
* **Delete Col:** 현재 선택한 셀을 삭제합니다.
* **Col H-Align:** 현재 선택한 셀내의 element를 가로 정렬합니다. 
    * **center:** 셀 내의 element를 중앙 정렬합니다. 
    * **left:** 셀 내의 element를 좌측 정렬합니다. 
    * **right:** 셀 내의 element를 우측 정렬합니다. 
    * **justify:** 셀 내의 element를 넓이 만큼 사이즈를 조정합니다. 

* **Col V-Align:** 현재 선택한 셀내의 element를 세로 정렬합니다. 
    * **middle:** 셀 내의 element를 세로 중앙에 정렬합니다. 
    * **top:** 셀 내의 element를 맨 상단으로 정렬합니다. 
    * **bottom:** 셀 내의 element를 맨 하단으로 정렬합니다. 
    * **baseline:** 셀 내의 element를 기준선에 맞추어 정렬합니다.  

<br/>
