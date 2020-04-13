# PivotGrid
> **Extends**: `AView`

.

<br/>

## Properties


### pivotGrid

좌측 고정된 그리드 Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>

### scrollGrid

우측 스크롤 그리드 Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>

### scrollView

우측 스크롤 그리드를 감싸고 있는 뷰

* **Type**: `Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### addRow( pivotData, scrollData )

PivotGrid의 마지막 Row 뒤에 Row를 추가한다.

* **Parameters**: 
	* **`pivotData`** {Array} 고정 그리드 데이터
	* **`scrollData`** {Array} 스크롤 그리드 데이터

<br/>

### applyBackupScroll()

백업 후의 스크롤 상태값을 적용합니다.

<br/>

### createBackup( maxRow, restoreCount )

그리드의 row수가 maxRow를 넘어갈때 상단의 restoreCount 수만큼 row를 백업을 합니다.

* **Parameters**: 
	* **`maxRow`** {Number} 그리드 최대 Row 수
	* **`restoreCount`** {Number} 백업할 수

<br/>

### destroyBackup()

그리드의 createBackup을 제거합니다.

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
<br/>
