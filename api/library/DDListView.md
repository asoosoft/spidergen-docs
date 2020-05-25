# DDListView
> **Extends** [`AListView`](./../afc/AListView.md)

드래그 & 드랍 관리하는 리스트뷰

<br/>

## Class Variables

<br/>

## Instance Variables

### dragInx \<Number>

드래그 되는 리스트 아이템의 인덱스

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### changeDragState( dragComp )

롱탭이 된 뷰가 드래그가 되도록 설정한다.

* `dragComp` \<[AView](./../afc/AView.md)> 드래그 뷰

<br/>

### createItems( url, dataArray, posItem, isPrepend )

리스트뷰에 아이템을 추가한다. 드랍, 롱탭시 드래그 되도록 처리한다.

* `url` \<String> 아이템에 추가될 뷰 리소스 url
* `dataArray` \<Array> 화면과 매핑될 데이터객체 배열
* `posItem` \<HTMLElement> 아이템을 추가할 위치가 되는 아이템(생략될 경우 리스트뷰의 맨 앞이나 맨 뒤에 추가된다)
* `isPrepend` \<Boolean> 아이템을 맨 앞에 추가하거나 맨 뒤에 추가할지(posItem이 존재하면 posItem 앞이나 뒤에 추가한다)
* **Returns** \<HTMLElement Array> 아이템 엘리먼트 배열

<br/>

### getDragInx()

드래그되는 아이템의 인덱스를 반환한다.

* **Returns** \<Number> 드래그 아이템 인덱스

```js
// ddListView는 DDListView 객체
var inx = ddListView.getDragInx();
```

<br/>

### onCompDrop( dropComp, evt )

드래그 작업이 종료 될 때 호출되는 메서드. 드래그 되는 아이템 뷰의 위치를 변경하고 리스트뷰에 등록된 delegator의 onItemMoved(dragComp, dropComp, listview) 메서드를 호출한다.

* `dropComp` \<[AView](./../afc/AView.md)> 드랍되는 아이템 뷰 또는 리스트뷰
* `evt` \<Object> 드래그 이벤트 정보 { dragComp, clientX, clientY }

<br/>

### onDragEnd( dragComp, e )

드래그가 종료될 때 호출되는 메서드.

* `dragComp` \<[AView](./../afc/AView.md)> 드래그 뷰
* `e` \<Object> 이벤트 객체

<br/>

<!-- 
### enableGlobalDrag()





```js

```

<br/>
-->

### onDropFail( dragComp, e )

아무곳에도 드랍되지 않은 경우 호출되는 메서드. 원래 위치로 되돌려 놓는다.

* `dragComp` \<[AView](./../afc/AView.md)> 드래그 컴포넌트
* `e` \<Object> 이벤트 객체

<br/>

### onDragScrollTop( dir )

드래그를 리스트뷰의 영역을 넘어선 상하의 위치로 이동시킨 하는 경우 리스트뷰의 스크롤탑 위치를 변경하여 상하의 영역이 보일수 있게 한다.

* `dir` \<Number> 방향 -1:상, 1:하

<br/>
<br/>

## Events

### onItemMoved( dragComp, dropComp, ddListView )

아이템이 드래그 앤 드롭 되었을 때 호출되는 [setDelegator(delegator)](./../afc/AListView.md#setdelegator-delegator-) 로 등록한 delegator의 메서드.

* `dragComp` \<[AView](./../afc/AView.md)> 드래그 컴포넌트
* `dropComp` \<[AView](./../afc/AView.md)> 드랍 컴포넌트
* `ddListView` \<[DDListView](./DDListView.md)> DDListView 객체

<br/>

