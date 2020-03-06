# DDListView
> **Extends**: `AListView`

드래그 & 드랍 관리하는 리스트뷰

<br/>

## Properties


### direction

드래그 방향

* **Type**: `Number`
* **Default**: `DDManager.DIR_VERTICAL`

<br/>

### dragInx

드래그 되는 리스트 아이템의 인덱스

* **Type**: `Number`
* **Default**: `-1`

<br/>
<br/>

## Methods

### changeDragState( dragComp )

롱탭이 된 뷰가 드래그가 되도록 설정한다.

* **Parameters**: 
	* **`dragComp`** {AView} 드래그 뷰

<br/>

### createItems( url, dataArray, posItem, isPrepend )

리스트뷰에 아이템을 추가한다. 드랍, 롱탭시 드래그 되도록 처리한다.

* **Returns**: Array

* **Parameters**: 
	* **`url`** {String} 아이템에 추가될 뷰 리소스 url
	* **`dataArray`** {Array} 화면과 매핑될 데이터객체 배열
	* **`posItem`** {HTML Object} 아이템을 추가할 위치가 되는 아이템(생략될 경우 리스트뷰의 맨 앞이나 맨 뒤에 추가된다)
	* **`isPrepend`** {Boolean} 아이템을 맨 앞에 추가하거나 맨 뒤에 추가할지(posItem이 존재하면 posItem 앞이나 뒤에 추가한다)

<br/>

### getDragInx()

드래그되는 아이템의 인덱스를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
// ddListView는 DDListView 객체
var inx = ddListView.getDragInx();
```

<br/>

### onCompDrop( dropComp, evt )

드래그 작업이 종료 될 때 호출되는 메서드. 드래그 되는 아이템 뷰의 위치를 변경하고 리스트뷰에 등록된 delegator의 onItemMoved(dragComp, dropComp, listview) 메서드를 호출한다.

* **Parameters**: 
	* **`dropComp`** {AView} 드랍되는 아이템 뷰 또는 리스트뷰
	* **`evt`** {Object} 드래그 이벤트 정보 { dragComp, clientX, clientY }

<br/>

### onDragEnd( dragComp, e )

드래그가 종료될 때 호출되는 메서드.

* **Parameters**: 
	* **`dragComp`** {AView} 드래그 뷰
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragStart( dragComp, e )

드래그가 시작될 때 호출되는 메서드.

* **Parameters**: 
	* **`dragComp`** {AView} 드래그 뷰
	* **`e`** {Object} 이벤트 객체

<br/>

### onViewLongTab( comp, info, e )

아이템 뷰가 롱탭되었을 때 발생하는 이벤트 함수이다.

* **Parameters**: 
	* **`comp`** {AView} 드래그 뷰
	* **`info`** {Object} .
	* **`e`** {Object} 이벤트 객체

<br/>

### setDirection( direction )

드래그 방향을 지정한다.<br/>DDManager.DIR_BOTH, DDManager.DIR_VERTICAL, DDManager.DIR_HORIZENTAL

* **Parameters**: 
	* **`direction`** {Number} 드래그 방향

* **Usage**: 
```js
// ddListView는 DDListView 객체
ddListView.setDirection(DDManager.DIR_BOTH);
ddListView.setDirection(DDManager.DIR_VERTICAL);
ddListView.setDirection(DDManager.DIR_HORIZENTAL);
```

<br/>
<br/>
## Events


### onItemMoved( dragComp, dropComp, ddListView )

아이템이 드래그 앤 드롭 되었을 때 호출되는 setDelegator(delegator) 로 등록한 delegator의 메서드.

* **Parameters**: 
	* **`dragComp`** {AComponent} 드래그 컴포넌트
	* **`dropComp`** {AComponent} 드랍 컴포넌트
	* **`ddListView`** {Object} DDListView 객체

<br/>

