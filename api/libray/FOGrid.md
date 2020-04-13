# FOGrid
> **Extends**: `AView`

.

<br/>

## Properties


### callGrid

콜 그리드 Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>

### pivotGrid

행사가 그리드 Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>

### putGrid

풋 그리드 Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### addHelper( grid, data, isPrepend )

FOGrid에 데이터를 추가합니다.

* **Parameters**: 
	* **`grid`** {AGrid} 데이터를 추가할 그리드
	* **`data`** {Array} 데이터
	* **`isPrepend`** {Boolean} 앞으로 추가할지 여부(true:앞으로 추가 / false:뒤로 추가)

<br/>

### addRow( callData, pivotData, putData )

FOGrid의 마지막 Row 뒤에 Row를 추가한다.

* **Parameters**: 
	* **`callData`** {Array} 콜 데이터
	* **`pivotData`** {Array} 행사가 데이터
	* **`putData`** {Array} 풋 데이터

<br/>

### prependRow( callData, pivotData, putData )

FOGrid의 첫번째 Row 앞에 Row를 추가한다.

* **Parameters**: 
	* **`callData`** {Array} 콜 데이터
	* **`pivotData`** {Array} 행사가 데이터
	* **`putData`** {Array} 풋 데이터

<br/>

### removeAll()

모든 row를 삭제합니다.

<br/>

### removeRow( rowIdx )

rowIdx에 해당하는 row를 삭제합니다.

* **Parameters**: 
	* **`rowIdx`** {Number} 삭제할 rowIndex

<br/>

### scrollIntoArea( row, isAlignTop )

파라미터로 넘어온 row 객체가 보이도록 그리드를 스크롤 시킨다.

* **Parameters**: 
	* **`row`** {Number or HTML Object} 숫자 또는 row 객체가 될 수 있다.
	* **`isAlignTop`** {Boolean} row를 상단으로 해서 보일지 여부(false 일 경우 하단)

<br/>

### scrollSyncSet( scrollGrid, scrollView )

스크롤뷰의 스크롤 값을 싱크할 그리드를 셋팅합니다.

* **Parameters**: 
	* **`scrollGrid`** {AGrid} 스크롤값을 싱크할 그리드
	* **`scrollView`** {AView} 스크롤뷰

<br/>
<br/>
