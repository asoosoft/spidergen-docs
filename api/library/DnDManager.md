# DnDManager( dndId )
> **Extends**

* `dndId` \<String> 매니저를 구분짓는 아이디

HTML 드래그 앤 드롭 관리 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

<!-- 
### dndGroup \<String>

드래그 element에 적용할 클래스명. DnDManager 가 생성될 떄의 시간과 dndId를 조합하여 만든다.

* **Default**: `'_' + tm + dndId`

<br/> -->

### dndId \<String or Number>

DnDManager를 구분하는 아이디

```js
var dndMgr = new DnDManager('testDnDMgr');
```

<br/>

### dragOption \<Object>

드래그 옵션

* `Default` `{ dragImage: null, imageOffset: {x:0, y:0} }`

<br/>

### dropOption \<Object>

드랍 옵션

* `Default` `{ applyChild: true, hoverClass: null }`

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### getApplyDragOption( option, key )

전달인자로 넘어온 옵션키에 해당하는 정보를 반환한다. 우선순위는 전달인자로 넘어온 옵션, DnDManager의 드래그 옵션 순이다.

* `option` \<Object> 옵션
* `key` \<String> 옵션 키
* **Returns** \<All>

<br/>

### getApplyDropOption( option, key )

전달인자로 넘어온 옵션키에 해당하는 정보를 반환한다. 우선순위는 전달인자로 넘어온 옵션, DnDManager의 드랍 옵션 순이다.

* `option` \<Object> 옵션
* `key` \<String> 옵션 키
* **Returns** \<All>

<br/>

### regDrag( element, listener, option )

엘리먼트의 드래그 모드를 설정한다. option을 지정하면 기본 드래그 옵션 대신 사용한다. dragstart 이벤트를 등록하여 리스너의 onDragStart 함수를 호출하고, dragend 이벤트를 등록하여 리스너의 onDragEnd 함수를 호출한다.

* `element` \<HTMLElement> 엘리먼트 또는 엘리먼트 배열
* `listener` \<Object> 이벤트를 수신할 객체
* `option` \<Object> 드래그 옵션

```js
// dndMgr 은 DnDManager 객체
dndMgr.regDrag(this.dragComp.getElement(), this, null);
var option = { dragImage: null, imageOffset: {x:10, y:20} };
dndMgr.regDrag(this.dragComp.getElement(), this, option);
```

<br/>

### regDrop( element, listener, option )

엘리먼트의 드랍 모드를 설정한다. option을 지정하면 기본 드랍 옵션 대신 사용한다. dragenter, dragleave, drop 이벤트를 등록하여 각각 리스너의 onDragEnter, onDragLeave, onElementDrop 함수를 호출한다. 리스너의 함수를 호출하지 않는 dragover 이벤트도 등록한다.

* `element` \<HTMLElement> 엘리먼트 또는 엘리먼트 배열
* `listener` \<Object> 이벤트를 수신할 객체
* `option` \<Object> 드랍 옵션

```js
// dndMgr 은 DnDManager 객체
dndMgr.regDrop(this.dropComp.getElement(), this, null);
var option = { applyChild: false, hoverClass: null };
dndMgr.regDrop(this.dropComp.getElement(), this, option);
```

<br/>

### setDragOption( option )

드래그 옵션을 지정한다.

* `option` \<Object> 드래그 옵션

```js
// dndMgr 은 DnDManager 객체
var option = { dragImage: 'Asset/dragImg.png', imageOffset: {x:1, y:1} };
dndMgr.setDragOption(option);
```

<br/>

### setDropOption( option )

드랍 옵션을 지정한다.

* `option` \<Object> 드랍 옵션

```js
// dndMgr 은 DnDManager 객체
var option = { applyChild: false, hoverClass: 'myClass1' };
dndMgr.setDropOption(option);
```

<br/>

### unregDrag( element )

엘리먼트의 드래그 모드를 해제한다.

* `element` \<HTMLElement> 엘리먼트 또는 엘리먼트 배열

```js
// dndMgr 은 DnDManager 객체
dndMgr.unregDrag(this.dragComp.getElement());
```

<br/>

### unregDrop( element )

엘리먼트의 드랍 모드를 해제한다.

* `element` \<HTMLElement> 엘리먼트 또는 엘리먼트 배열

```js
// dndMgr 은 DnDManager 객체
dndMgr.unregDrop(this.dropComp.getElement());
```

<br/>

### getApplyDragOption( option, key )

기본 옵션값을 가져온다. 만약 추가적인 옵션이 파라미터로 있다면 그 옵션값을 우선으로 한다. option[key] 값 또는 dragOption[key] 값을 가져온다. 

* `option` \<Object> 드래그 옵션
* `key` \<String> 옵션 키
* **Returns** \<All> drag option 값

```js
dndMgr.getApplyDragOption(null, 'dragImage'); //null
var option = { dragImage: './dragImg.png' };
dndMgr.getApplyDragOption(option, 'dragImage'); //'./dragImg.png'
```

<br/>

### getApplyDropOption( option, key )

기본 옵션값을 가져온다. 만약 추가적인 옵션이 파라미터로 있다면 그 옵션값을 우선으로 한다. option[key] 값 또는 drogOption[key] 값을 가져온다. 

* `option` \<Object> 드래그 옵션
* `key` \<String> 옵션 키
* **Returns** \<All> drop option 값

```js
dndMgr.getApplyDropOption(null, 'applyChild'); //true
var option = { applyChild: false };
dndMgr.getApplyDropOption(option, 'applyChild'); //false
```

<br/>
<br/>

## Events


### onDragEnd( dnd, e )

드래그 종료 이벤트. regDrag(element, listener, option) 를 호출하여 드래그 모드를 설정한 엘리먼트의 드래그가 종료될 때 listener의 이벤트 함수를 호출한다.

* `dnd` \<Object> DnDManager 객체
* `e` \<Object> 이벤트 객체

### onDragEnter( dnd, e )

드랍 엘리먼트 영역에 드래그 엘리먼트가 들어올 떄 호출되는 이벤트. regDrop(element, listener, option) 를 호출하여 드랍 모드를 설정한 엘리먼트에 드래그 엘리먼트가 들어올 때 listener의 이벤트 함수를 호출한다.

* `dnd` \<Object> DnDManager 객체
* `e` \<Object> 이벤트 객체

### onDragLeave( dnd, e )

드랍 엘리먼트 영역에서 드래그 엘리먼트가 나갈 떄 호출되는 이벤트. regDrop(element, listener, option) 를 호출하여 드랍 모드를 설정한 엘리먼트에서 드래그 엘리먼트가 나갈 때 listener의 이벤트 함수를 호출한다.

* `dnd` \<Object> DnDManager 객체
* `e` \<Object> 이벤트 객체

### onDragStart( dnd, e )

드래그 시작 이벤트. regDrag(element, listener, option) 를 호출하여 드래그 모드를 설정한 엘리먼트가 드래그 시작할 때 listener의 이벤트 함수를 호출한다.

* `dnd` \<Object> DnDManager 객체
* `e` \<Object> 이벤트 객체

### onElementDrop( dnd, e, element )

드랍 엘리먼트 영역에 드래그 엘리먼트가 드랍될 때 호출되는 이벤트. regDrop(element, listener, option) 를 호출하여 드랍 모드를 설정한 엘리먼트에 드래그 엘리먼트가 드랍될 때 listener의 이벤트 함수를 호출한다.

* `dnd` \<Object> DnDManager 객체
* `e` \<Object> 이벤트 객체
* `element` \<HTMLElement> 드래그 엘리먼트

<br/>

