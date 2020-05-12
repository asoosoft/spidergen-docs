<<<<<<< HEAD
<<<<<<< HEAD
# DnDListView
> **Extends**: `AListView`

HTML 드래그 앤 드롭 관리 리스트뷰

<br/>

## Properties


### dragInx

드래그 되는 리스트 아이템의 인덱스

* **Type**: `Number`
* **Default**: `-1`

<br/>

### option.longTabClass

* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

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
// dndListView 는 DnDListView 객체
var inx = dndListView.getDragInx();
```

<br/>

### init( context, evtListener )

리스트뷰 자체에도 드랍이 가능하도록 리스트뷰 엘리먼트의 드랍모드를 설정한다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {Object} context 에 매핑된 이벤트 수신자

<br/>

### onDragEnd( dnd, e )

드래그가 종료될 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragEnter( dnd, e )

드래그 된 요소 또는 텍스트 선택이 유효한 드롭 대상에 들어갈 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragLeave( dnd, e )

드래그 된 요소 또는 텍스트 선택이 유효한 드롭 대상에서 나갈 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragStart( dnd, e )

드래그가 시작될 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onElementDrop( dnd, e, dragEle )

드래그 작업이 종료 될 때 호출되는 메서드. 드래그 되는 아이템 뷰의 위치를 변경하고 리스트뷰에 등록된 delegator의 onItemMoved(dragComp, dropComp, listview) 메서드를 호출한다.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체
	* **`dragEle`** {HTML Object} 드래그 엘리먼트

<br/>

### onViewLongTab( comp, info, e )

아이템 뷰가 롱탭되었을 때 발생하는 이벤트 함수이다. 드래그뷰의 item 에 드래그모드를 설정한다.

* **Parameters**: 
	* **`comp`** {AView} 드래그 뷰
	* **`info`** {Object} .
	* **`e`** {Object} 이벤트 객체

<br/>

### regDrag( item, listener )

dndManager 의 regDrag 메서드를 호출하여 드래그 모드를 설정한다.

* **Parameters**: 
	* **`item`** {HTML Object} 드래그할 리스트 아이템
	* **`listener`** {Object} 이벤트를 수신할 객체

<br/>

### regDrop( item, listener )

dndManager 의 regDrag 메서드를 호출하여 드랍 모드를 설정한다.

* **Parameters**: 
	* **`item`** {HTML Object} 드래그할 리스트 아이템
	* **`listener`** {Object} 이벤트를 수신할 객체

<br/>
<br/>

## Events


### onItemMoved( dragEle, dropEle, dndListView )

아이템이 드래그 앤 드롭 되었을 때 호출되는 setDelegator(delegator) 로 등록한 delegator의  메서드.

* **Parameters**: 
	* **`dragEle`** {HTML Object} 드래그 엘리먼트
	* **`dropEle`** {HTML Object} 드랍 엘리먼트
	* **`dndListView`** {AComponent} DnDListView 객체

<br/>

=======
# DnDListView
> **Extends**: `AListView`

HTML 드래그 앤 드롭 관리 리스트뷰

<br/>

## Properties


### dragInx

드래그 되는 리스트 아이템의 인덱스

* **Type**: `Number`
* **Default**: `-1`

<br/>

### option.longTabClass

* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

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
// dndListView 는 DnDListView 객체
var inx = dndListView.getDragInx();
```

<br/>

### init( context, evtListener )

리스트뷰 자체에도 드랍이 가능하도록 리스트뷰 엘리먼트의 드랍모드를 설정한다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {Object} context 에 매핑된 이벤트 수신자

<br/>

### onDragEnd( dnd, e )

드래그가 종료될 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragEnter( dnd, e )

드래그 된 요소 또는 텍스트 선택이 유효한 드롭 대상에 들어갈 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragLeave( dnd, e )

드래그 된 요소 또는 텍스트 선택이 유효한 드롭 대상에서 나갈 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragStart( dnd, e )

드래그가 시작될 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onElementDrop( dnd, e, dragEle )

드래그 작업이 종료 될 때 호출되는 메서드. 드래그 되는 아이템 뷰의 위치를 변경하고 리스트뷰에 등록된 delegator의 onItemMoved(dragComp, dropComp, listview) 메서드를 호출한다.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체
	* **`dragEle`** {HTML Object} 드래그 엘리먼트

<br/>

### onViewLongTab( comp, info, e )

아이템 뷰가 롱탭되었을 때 발생하는 이벤트 함수이다. 드래그뷰의 item 에 드래그모드를 설정한다.

* **Parameters**: 
	* **`comp`** {AView} 드래그 뷰
	* **`info`** {Object} .
	* **`e`** {Object} 이벤트 객체

<br/>

### regDrag( item, listener )

dndManager 의 regDrag 메서드를 호출하여 드래그 모드를 설정한다.

* **Parameters**: 
	* **`item`** {HTML Object} 드래그할 리스트 아이템
	* **`listener`** {Object} 이벤트를 수신할 객체

<br/>

### regDrop( item, listener )

dndManager 의 regDrag 메서드를 호출하여 드랍 모드를 설정한다.

* **Parameters**: 
	* **`item`** {HTML Object} 드래그할 리스트 아이템
	* **`listener`** {Object} 이벤트를 수신할 객체

<br/>
<br/>

## Events


### onItemMoved( dragEle, dropEle, dndListView )

아이템이 드래그 앤 드롭 되었을 때 호출되는 setDelegator(delegator) 로 등록한 delegator의  메서드.

* **Parameters**: 
	* **`dragEle`** {HTML Object} 드래그 엘리먼트
	* **`dropEle`** {HTML Object} 드랍 엘리먼트
	* **`dndListView`** {AComponent} DnDListView 객체

<br/>

>>>>>>> bc729ae47e04917eefd0eaed80c7b915b82b4564
=======
# DnDListView
> **Extends**: `AListView`

HTML 드래그 앤 드롭 관리 리스트뷰

<br/>

## Properties


### dragInx

드래그 되는 리스트 아이템의 인덱스

* **Type**: `Number`
* **Default**: `-1`

<br/>

### option.longTabClass

* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

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
// dndListView 는 DnDListView 객체
var inx = dndListView.getDragInx();
```

<br/>

### init( context, evtListener )

리스트뷰 자체에도 드랍이 가능하도록 리스트뷰 엘리먼트의 드랍모드를 설정한다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {Object} context 에 매핑된 이벤트 수신자

<br/>

### onDragEnd( dnd, e )

드래그가 종료될 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragEnter( dnd, e )

드래그 된 요소 또는 텍스트 선택이 유효한 드롭 대상에 들어갈 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragLeave( dnd, e )

드래그 된 요소 또는 텍스트 선택이 유효한 드롭 대상에서 나갈 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onDragStart( dnd, e )

드래그가 시작될 때 호출되는 메서드.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

<br/>

### onElementDrop( dnd, e, dragEle )

드래그 작업이 종료 될 때 호출되는 메서드. 드래그 되는 아이템 뷰의 위치를 변경하고 리스트뷰에 등록된 delegator의 onItemMoved(dragComp, dropComp, listview) 메서드를 호출한다.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체
	* **`dragEle`** {HTML Object} 드래그 엘리먼트

<br/>

### onViewLongTab( comp, info, e )

아이템 뷰가 롱탭되었을 때 발생하는 이벤트 함수이다. 드래그뷰의 item 에 드래그모드를 설정한다.

* **Parameters**: 
	* **`comp`** {AView} 드래그 뷰
	* **`info`** {Object} .
	* **`e`** {Object} 이벤트 객체

<br/>

### regDrag( item, listener )

dndManager 의 regDrag 메서드를 호출하여 드래그 모드를 설정한다.

* **Parameters**: 
	* **`item`** {HTML Object} 드래그할 리스트 아이템
	* **`listener`** {Object} 이벤트를 수신할 객체

<br/>

### regDrop( item, listener )

dndManager 의 regDrag 메서드를 호출하여 드랍 모드를 설정한다.

* **Parameters**: 
	* **`item`** {HTML Object} 드래그할 리스트 아이템
	* **`listener`** {Object} 이벤트를 수신할 객체

<br/>
<br/>

## Events


### onItemMoved( dragEle, dropEle, dndListView )

아이템이 드래그 앤 드롭 되었을 때 호출되는 setDelegator(delegator) 로 등록한 delegator의  메서드.

* **Parameters**: 
	* **`dragEle`** {HTML Object} 드래그 엘리먼트
	* **`dropEle`** {HTML Object} 드랍 엘리먼트
	* **`dndListView`** {AComponent} DnDListView 객체

<br/>

>>>>>>> bc729ae47e04917eefd0eaed80c7b915b82b4564
