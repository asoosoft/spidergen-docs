# DDManager( acomp )
> **Extends**

* `acomp` \<[AComponent](./../afc/AComponent.md)> 드래그 & 드랍할 컴포넌트 객체

[AComponent](./../afc/AComponent.md) 의 드래그 & 드랍을 관리하는 클래스

<br/>

## Class Variables

### DDManager.DIR_BOTH \<Number>

상하좌우로 드래그 가능 플래그
<br/>[setDDOption](#-setDDOption-option-) 에 direction 으로 지정한다.

* `Default` `0`

<br/>

### DDManager.DIR_VERTICAL \<Number>

상하로 드래그 가능 플래그
<br/>[setDDOption](#-setDDOption-option-) 에 direction 으로 지정한다.

* `Default` `1`

<br/>

### DDManager.DIR_HORIZENTAL \<Number>

좌우로 드래그 가능 플래그
<br/>[setDDOption](#-setDDOption-option-) 에 direction 으로 지정한다.

* `Default` `2`

<br/>

## Instance Variables

### acomp \<[AComponent](./../afc/AComponent.md)>

드래그&드랍 대상 AComponent 객체

<br/>

### dragBound \<DOMRect>

드래그 가능 영역 {left:0, top:0, right:0, bottom:0}
<br/>보통 [AComponent](./../afc/AComponent.md)의 getBoundRect() 함수를 사용한다

<br/>

### isDraggable \<Boolean>

드래그 가능 여부

<br/>

### isDroppable \<Boolean>

드랍 가능 여부

<br/>

### offsetX \<Number>

드래그하는 동안 draggable 요소의 X 위치값을 지정한다. 위치값은 상대값이며 위치값이 0인 경우 요소의 중앙이 마우스 포인터에 위치한다.

<br/>

### offsetY \<Number>

드래그하는 동안 draggable 요소의 Y 위치값을 지정한다. 위치값은 상대값이며 위치값이 0인 경우 요소의 중앙이 마우스 포인터에 위치한다.

<br/>

### option \<Object>

드래그&드랍 옵션 <br/>isDropPropagation: false, //드랍 이벤트를 최상위 드랍 컴포넌트에게만 전달할지 <br/>direction: DDManager.DIR_BOTH //드래그 이동 가능 방향, 기본은 가로, 세로 모두 가능

<br/>
<br/>

## Class Method

<br/>
<br/>

## Instance Method

### enableDrag( isDraggable, listener )

드래그 가능 여부를 지정한다. 리스너에 드래그가 시작, 종료될 때 호출되는 이벤트 함수를 반드시 정의해야 한다.<br/>드래그 시작 이벤트 : onDragStart(dragComp, e)<br/>드래그 종료 이벤트 : onDragEnd(dragComp, e)

* `isDraggable` \<Boolean> 드래그 가능 여부
* `listener` \<Object> 드래그시 이벤트 받을 객체

```js
// ddMgr 은 DDManager 객체
ddMgr.enableDrag(true, this);
ddMgr.enableDrag(false, this);
```

<br/>

### enableDrop( isDroppable, listener )

드랍 가능 여부를 지정한다. 리스너에 드랍될 때 호출되는 이벤트 함수를 반드시 정의해야 한다.<br/>드랍 이벤트 : onCompDrop(dragComp, e)

* `isDroppable` \<Boolean> 드랍 가능 여부
* `listener` \<Object> 드랍 이벤트 받을 객체

```js
// ddMgr 은 DDManager 객체
ddMgr.enableDrop(true, this);
ddMgr.enableDrop(false, this);
```

<br/>

### setDDOption( option )

드래그&드랍 옵션을 설정한다.

* `option` \<Object> 옵션 { isDropPropagation, direction } 형식
  
  * isDropPropagation: 드랍 이벤트를 최상위 드랍 컴포넌트에게만 전달할지(Boolean)
  * direction: 드래그 이동 가능 방향(DDManager.DIR_BOTH, DIR_VERTICAL, DIR_HORIZENTAL)

```js
// ddMgr 은 DDManager 객체
var option = {
	isDropPropagation: true, //드랍 이벤트를 최상위 드랍 컴포넌트에게만 전달(Boolean)
	direction: DDManager.DIR_VERTICAL //드래그 이동 가능 방향
};
ddMgr.setDDOption(option);
```

<br/>

### setDragBound( bound )

드래그 가능 영역을 셋팅한다.

* `bound` \<DOMRect> {left:0, top:0, right:0, bottom:0}

```js
// ddMgr 은 DDManager 객체
ddMgr.setDragBound(this.dragComp.getBoundRect());
```

<br/>

### setDropListener( listener )

드랍 가능 여부를 지정한다. 리스너에 드랍될 때 호출되는 이벤트 함수를 반드시 정의해야 한다.<br/>드랍 이벤트 : onCompDrop(dropComp, e)

* `listener` \<Object> 드랍 이벤트 받을 객체

```js
// ddMgr 은 DDManager 객체
ddMgr.setDropListener(this);
```

<br/>

### setOffset( offsetX, offsetY )

드래그하는 동안 draggable 요소의 위치를 지정한다. 위치값은 상대값이며 위치값이 0인 경우 요소의 중앙이 마우스 포인터에 위치한다.

* `offsetX` \<Number> 위치값 x
* `offsetY` \<Number> 위치값 y

```js
// ddMgr 은 DDManager 객체
ddMgr.setOffset(10, -10);
```

<br/>
<br/>

## Events


### onCompDrop( dragComp, evt )

드랍 이벤트. enableDrop(true, listener) 를 호출하여 드랍 모드를 설정한 컴포넌트에 드랍될 때 listener의 이벤트를 함수를 호출한다.<br/>evt는 { dragComp, clientX, clientY } 형식이다.

* `dragComp` \<[AComponent](./../afc/AComponent.md)> 드래그 컴포넌트
* `evt` \<Object> 이벤트 객체

<br/>

### onDragEnd( dragComp, e )

드래그 종료 이벤트. enableDrag(true, listener) 를 호출하여 드래그 모드를 설정한 컴포넌트가 드래그 종료될 때 listener의 이벤트를 함수를 호출한다.

* `dragComp` \<[AComponent](./../afc/AComponent.md)> 드래그 컴포넌트
* `e` \<Object> 이벤트 객체

<br/>

### onDragScrollLeft( dir )

드래그하여 드래그 영역 보다 더 왼쪽 또는 더 오른쪽으로 이동시켰을 때 호출되는 이벤트. enableDrag(true, listener) 를 호출하여 드래그 모드를 설정한 컴포넌트가 드래그 가능한 영역을 좌우로 넘어간 경우 listener의 이벤트를 함수를 호출한다.

* `dir` \<Number> 방향 -1:좌, 1:우

<br/>

### onDragScrollTop( dir )

드래그하여 드래그 영역 보다 더 위쪽 또는 더 아래쪽으로 이동시켰을 때 호출되는 이벤트. enableDrag(true, listener) 를 호출하여 드래그 모드를 설정한 컴포넌트가 드래그 가능한 영역을 상하로 넘어간 경우 listener의 이벤트를 함수를 호출한다.

* `dir` \<Number> 방향 -1:상, 1:하
* 
<br/>

### onDragStart( dragComp, e )

드래그 시작 이벤트. enableDrag(true, listener) 를 호출하여 드래그 모드를 설정한 컴포넌트가 드래그 될 때 listener의 이벤트를 함수호출한다.

* `dragComp` \<[AComponent](./../afc/AComponent.md)> 드래그 컴포넌트
* `e` \<Object> 이벤트 객체

<br/>

### onDropFail( dragComp, e )

아무곳에도 드랍되지 않은 경우. enableDrag(true, listener) 를 호출하여 드래그 모드를 설정한 컴포넌트가 아무곳에도 드랍되지 않은 경우 listener의 이벤트를 함수호출한다.

* `dragComp` \<[AComponent](./../afc/AComponent.md)> 드래그 컴포넌트
* `e` \<Object> 이벤트 객체

<br/>