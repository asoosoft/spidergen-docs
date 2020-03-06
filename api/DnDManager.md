# DnDManager
> **Extends**: 

HTML 드래그 앤 드롭 관리 클래스

<br/>

## Properties


### dndGroup

드래그 element에 적용할 클래스명. DnDManager 가 생성될 떄의 시간과 dndId를 조합하여 만든다.

* **Type**: `String`
* **Default**: `'_' + tm + dndId`

<br/>

### dndId

DnDManager를 구분하는 아이디

* **Type**: `String or Number`
* **Default**: `dndId`

<br/>

### dragOption

드래그 옵션

* **Type**: `Object`
* **Default**: `{ dragImage: null, imageOffset: {x:0, y:0} }`

<br/>

### dropOption

드랍 옵션

* **Type**: `Object`
* **Default**: `{ applyChild: true, hoverClass: null }`

<br/>
<br/>

## Methods

### getApplyDragOption( option, key )

전달인자로 넘어온 옵션키에 해당하는 정보를 반환한다. 우선순위는 전달인자로 넘어온 옵션, DnDManager의 드래그 옵션 순이다.

* **Returns**: All

* **Parameters**: 
	* **`option`** {Object} 옵션
	* **`key`** {String} 옵션 키

<br/>

### getApplyDropOption( option, key )

전달인자로 넘어온 옵션키에 해당하는 정보를 반환한다. 우선순위는 전달인자로 넘어온 옵션, DnDManager의 드랍 옵션 순이다.

* **Returns**: All

* **Parameters**: 
	* **`option`** {Object} 옵션
	* **`key`** {String} 옵션 키

<br/>

### regDrag( element, listener, option )

엘리먼트의 드래그 모드를 설정한다. option을 지정하면 기본 드래그 옵션 대신 사용한다. dragstart 이벤트를 등록하여 리스너의 onDragStart 함수를 호출하고, dragend 이벤트를 등록하여 리스너의 onDragEnd 함수를 호출한다.

* **Parameters**: 
	* **`element`** {HTML Object} 엘리먼트 또는 엘리먼트 배열
	* **`listener`** {Object} 이벤트를 수신할 객체
	* **`option`** {Object} 드래그 옵션

* **Usage**: 
```js
// dndMgr 은 DnDManager 객체
dndMgr.regDrag(this.dragComp.getElement(), this, null);
dndMgr.regDrag(this.dragComp.getElement(), this, { dragImage: null, imageOffset: {x:10, y:20}});
```

<br/>

### regDrop( element, listener, option )

엘리먼트의 드랍 모드를 설정한다. option을 지정하면 기본 드랍 옵션 대신 사용한다. dragenter, dragleave, drop 이벤트를 등록하여 각각 리스너의 onDragEnter, onDragLeave, onElementDrop 함수를 호출한다. 리스너의 함수를 호출하지 않는 dragover 이벤트도 등록한다.

* **Parameters**: 
	* **`element`** {HTML Object} 엘리먼트 또는 엘리먼트 배열
	* **`listener`** {Object} 이벤트를 수신할 객체
	* **`option`** {Object} 드랍 옵션

* **Usage**: 
```js
// dndMgr 은 DnDManager 객체
dndMgr.regDrop(this.dropComp.getElement(), this, null);
dndMgr.regDrop(this.dropComp.getElement(), this, { applyChild: false, hoverClass: null});
```

<br/>

### setDragOption( option )

드래그 옵션을 지정한다.

* **Parameters**: 
	* **`option`** {Object} 드래그 옵션

* **Usage**: 
```js
// dndMgr 은 DnDManager 객체
var option = { dragImage: 'Asset/dragImg.png', imageOffset: {x:1, y:1} };
dndMgr.setDragOption(option);
```

<br/>

### setDropOption( option )

드랍 옵션을 지정한다.

* **Parameters**: 
	* **`option`** {Object} 드랍 옵션

* **Usage**: 
```js
// dndMgr 은 DnDManager 객체
var option = { applyChild: false, hoverClass: 'myClass1' };
dndMgr.setDropOption(option);
```

<br/>

### unregDrag( element )

엘리먼트의 드래그 모드를 해제한다.

* **Parameters**: 
	* **`element`** {HTML Object} 엘리먼트 또는 엘리먼트 배열

* **Usage**: 
```js
// dndMgr 은 DnDManager 객체
dndMgr.unregDrag(this.dragComp.getElement());
```

<br/>

### unregDrop( element )

엘리먼트의 드랍 모드를 해제한다.

* **Parameters**: 
	* **`element`** {HTML Object} 엘리먼트 또는 엘리먼트 배열

* **Usage**: 
```js
// dndMgr 은 DnDManager 객체
dndMgr.unregDrop(this.dropComp.getElement());
```

<br/>
<br/>
## Events


### onDragEnd( dnd, e )

드래그 종료 이벤트. regDrag(element, listener, option) 를 호출하여 드래그 모드를 설정한 엘리먼트의 드래그가 종료될 때 listener의 이벤트 함수를 호출한다.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

### onDragEnter( dnd, e )

드랍 엘리먼트 영역에 드래그 엘리먼트가 들어올 떄 호출되는 이벤트. regDrop(element, listener, option) 를 호출하여 드랍 모드를 설정한 엘리먼트에 드래그 엘리먼트가 들어올 때 listener의 이벤트 함수를 호출한다.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

### onDragLeave( dnd, e )

드랍 엘리먼트 영역에서 드래그 엘리먼트가 나갈 떄 호출되는 이벤트. regDrop(element, listener, option) 를 호출하여 드랍 모드를 설정한 엘리먼트에서 드래그 엘리먼트가 나갈 때 listener의 이벤트 함수를 호출한다.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

### onDragStart( dnd, e )

드래그 시작 이벤트. regDrag(element, listener, option) 를 호출하여 드래그 모드를 설정한 엘리먼트가 드래그 시작할 때 listener의 이벤트 함수를 호출한다.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체

### onElementDrop( dnd, e, element )

드랍 엘리먼트 영역에 드래그 엘리먼트가 드랍될 때 호출되는 이벤트. regDrop(element, listener, option) 를 호출하여 드랍 모드를 설정한 엘리먼트에 드래그 엘리먼트가 드랍될 때 listener의 이벤트 함수를 호출한다.

* **Parameters**: 
	* **`dnd`** {Object} DnDManager 객체
	* **`e`** {Object} 이벤트 객체
	* **`element`** {HTML Object} 드래그 엘리먼트

<br/>

