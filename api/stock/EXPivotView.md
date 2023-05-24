# EXPivotView
> **Extends**: [`AView`](./../afc/AView.md)

--NOT USE

<br/>

## Properties

### pivotGrid \<AGrid>

고정되는 그리드

<br/>

### scrollGrid \<AGrid>

스크롤뷰 내부에 있는 그리드

<br/>

### scrollView \<AView>

스크롤이 되는 뷰

<br/>

## Instance Method

### init()

<br/>

### lockScrollView()

스크롤뷰의 좌우 스크롤을 막는다.

<br/>

### unlockScrollView()

스크롤뷰의 좌우 스크롤을 허용한다.

<br/>

### scrollViewLeft()

스크롤뷰 내부 스크롤그리드의 우측끝이 보일수 있게 스크롤 위치를 변경한다.

<br/>

### addRow( pivotData, scrollData )

고정그리드와 스크롤그리드의 뒷부분에 로우를 추가한다.

* `pivotData` \<Array> 고정그리드에 추가할 데이터
* `scrollData` \<Array> 스크롤그리드에 추가할 데이터

<br/>

### prependRow( pivotData, scrollData )

고정그리드와 스크롤그리드의 앞부분에 로우를 추가한다.

* `pivotData` \<Array> 고정그리드에 추가할 데이터
* `scrollData` \<Array> 스크롤그리드에 추가할 데이터

<br/>

### setRow( rowInx, pivotData, scrollData, start, end )

특정 로우의 텍스트를 세팅한다.

* `rowInx` \<Number> 로우 인덱스
* `pivotData` \<Array> 고정그리드 데이터 배열
* `scrollData` \<Array> 스크롤그리드 데이터 배열
* `start` \<Number> 시작 컬럼 인덱스(생략하면 로우 전체)
* `end` \<Number> 종료 컬럼 인덱스

<br/>

### removeRow( rowIdx )

특정 row 를 그리드에서 제거한다.

* `rowIdx` \<Number> or \<HTMLTableRowElement> Row index 또는 Row Element

<br/>

### removeFirst()

첫번째 row를 제거한다.

<br/>

### removeLast()

마지막 Row를 제거한다.

<br/>

### removeAll()

그리드의 모든 row 를 제거한다.

<br/>

### createBackup( maxRow, restoreCount )

백업 시스템이 작동하도록 BackupManager 를 생성한다.<br/>프로젝트의 프레임웍 로딩옵션이 모든 항목 로드가 아닌 경우 프로젝트 트리의 Framework/afc 우측 메뉴에서 Default Load Settings 팝업을 띄워서 BackupManager.js 를 체크해줘야 사용할 수 있다.

* `maxRow` \<Number> 백업을 시작할 최대 row 개수
* `restoreCount` \<Number> 한번에 백업 및 복원할 row 개수

<br/>

### destroyBackup()

백업 시스템을 중단하고 BackupManager 를 소멸시킨다.

<br/>

<!-- 
### applyBackupScroll()

각 그리드에 백업스크롤을 적용한다. <br/><br/>※ 그리드내부에 표현될 항목의 최대 개수와 복원 개수를 지정하여 항목을 무한히 추가하지 않고 관리한다.

<br/>

### setAllGridSelect()



* **Parameters**: 


* **Usage**: 
```js

```

<br/> -->

### setScrollComp( acomp )

그리드의 스크롤과 관계되어 있는 컴포넌트를 세팅한다.

* `acomp` \<Component> 컴포넌트

<br/>

### scrollTo( pos )

세로 스크롤의 위치를 pos 위치로 이동한다.

* `pos` \<Number> 스크롤 위치

<br/>

### scrollOffset( offset )

세로 스크롤의 위치를 현재 위치로부터 offset 만큼 이동한다.

* `offset` \<Number> 이동할 거리

<br/>

### scrollIntoArea( row, isAlignTop)

row 가 보이는 위치로 스크롤 위치를 변경한다.

* `row` \<Number> 보여줄 로우 인덱스
* `isAlignTop` \<Boolean> 최상단 위치 여부(기본값 : true)


<br/>

### scrollToTop()

스크롤 위치를 최상단으로 이동한다.

<br/>

### scrollToBottom()

스크롤 위치를 바닥으로 이동한다.

<br/>

### scrollToCenter()

스크롤 세로방향 위치를 중간으로 이동한다.

<br/>

### setQueryData( dataArr, keyArr, queryData )



* `dataArr` \<Array>
* `keyArr` \<Array>
* `queryData` \<AQueryData>

<br/>

### getQueryData( dataArr, keyArr, queryData )



* `dataArr` \<Array>
* `keyArr` \<Array>
* `queryData` \<AQueryData>

<br/>