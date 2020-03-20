# DDManager
> **Extends**: 

AComponent 의 드래그 & 드랍을 관리하는 클래스

<br/>

## Properties


### acomp

드래그&드랍 대상 AComponent 객체

* **Type**: `AComponent`
* **Default**: `acomp`

<br/>

### dragBound

드래그 가능 영역 <br/>{left:0, top:0, right:0, bottom:0}

* **Type**: `Rect`
* **Default**: `null`

<br/>


### isDraggable

드래그 가능 여부

* **Type**: `Boolean`
* **Default**: `false`

<br/>

### isDroppable

드랍 가능 여부

* **Type**: `Boolean`
* **Default**: `false`

<br/>

### offsetX

드래그하는 동안 draggable 요소의 X 위치값을 지정한다. 위치값은 상대값이며 위치값이 0인 경우 요소의 중앙이 마우스 포인터에 위치한다.

* **Type**: `Number`
* **Default**: `0`

<br/>

### offsetY

드래그하는 동안 draggable 요소의 Y 위치값을 지정한다. 위치값은 상대값이며 위치값이 0인 경우 요소의 중앙이 마우스 포인터에 위치한다.

* **Type**: `Number`
* **Default**: `0`

<br/>

### option

드래그&드랍 옵션 <br/>isDropPropagation: false, //드랍 이벤트를 최상위 드랍 컴포넌트에게만 전달할지 <br/>direction: DDManager.DIR_BOTH //드래그 이동 가능 방향, 기본은 가로, 세로 모두 가능

* **Type**: `Object`
* **Default**: 

<br/>


### isDroppable()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### touchStart()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### touchMove()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### touchEnd()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### touchCancel()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>

## Methods

### enableDrag( isDraggable, listener )

드래그 가능 여부를 지정한다. 리스너에 드래그가 시작, 종료될 때 호출되는 이벤트 함수를 반드시 정의해야 한다.<br/>드래그 시작 이벤트 : onDragStart(dragComp, e)<br/>드래그 종료 이벤트 : onDragEnd(dragComp, e)

* **Parameters**: 
	* **`isDraggable`** {Boolean} 드래그 가능 여부
	* **`listener`** {Object} 드래그시 이벤트 받을 객체

* **Usage**: 
```js
// ddMgr 은 DDManager 객체
ddMgr.enableDrag(true, this);
ddMgr.enableDrag(false, this);
```

<br/>

### setDDOption( option )

드래그&드랍 옵션을 설정한다. option 은{ isDropPropagation, direction } 형식이다.<br/>isDropPropagation: 드랍 이벤트를 최상위 드랍 컴포넌트에게만 전달할지(Boolean)<br/>direction: 드래그 이동 가능 방향(DDManager.DIR_BOTH, DDManager.DIR_VERTICAL, DDManager.DIR_HORIZENTAL)

* **Parameters**: 
	* **`option`** {Object} .

* **Usage**: 
```js
// ddMgr 은 DDManager 객체
var option = { isDropPropagation: true, direction: DDManager.DIR_VERTICAL };
ddMgr.setDDOption(option);
```

<br/>

### setDragBound( bound )

드래그 가능 영역을 셋팅한다.

* **Parameters**: 
	* **`bound`** {Rect} {left:0, top:0, right:0, bottom:0}

* **Usage**: 
```js
// ddMgr 은 DDManager 객체
ddMgr.setDragBound(this.dragComp.getBoundRect());
```

<br/>

### setOffset( offsetX, offsetY )

드래그하는 동안 draggable 요소의 위치를 지정한다. 위치값은 상대값이며 위치값이 0인 경우 요소의 중앙이 마우스 포인터에 위치한다.

* **Parameters**: 
	* **`offsetX`** {Number} 위치값 x
	* **`offsetY`** {Number} 위치값 y

* **Usage**: 
```js
// ddMgr 은 DDManager 객체
ddMgr.setOffset(10, -10);
```

<br/>

### setDropListener()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>

## Events


### onCompDrop( dragComp, evt )

드랍 이벤트. enableDrop(true, listener) 를 호출하여 드랍 모드를 설정한 컴포넌트에 드랍될 때 listener의 이벤트 함수를 호출한다.<br/>evt는 { dragComp, clientX, clientY } 형식이다.

* **Parameters**: 
	* **`dragComp`** {AComponent} 드래그 컴포넌트
	* **`evt`** {Object} 이벤트 객체

### onDragEnd( dragComp, e )

드래그 종료 이벤트. enableDrag(true, listener) 를 호출하여 드래그 모드를 설정한 컴포넌트가 드래그 종료될 때 listener의 이벤트 함수를 호출한다.

* **Parameters**: 
	* **`dragComp`** {AComponent} 드래그 컴포넌트
	* **`e`** {Object} 이벤트 객체

### onDragStart( dragComp, e )

드래그 시작 이벤트. enableDrag(true, listener) 를 호출하여 드래그 모드를 설정한 컴포넌트가 드래그 될 때 listener의 이벤트 함수호출한다.

* **Parameters**: 
	* **`dragComp`** {AComponent} 드래그 컴포넌트
	* **`e`** {Object} 이벤트 객체

<br/>

