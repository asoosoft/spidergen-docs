# AComponent
**Extends**: 

최상위 추상 컴포넌트

<br/>

## Properties

### element \<HTMLElement>
컴포넌트를 이루고 있는 HTMLElement 객체
```js
this.element.style.color = 'blue';
```
<br>

### $ele \<jQuery>

this.element 의 jQuery 객체
```js
this.$ele.css('color', 'blue');
```
<br>

### isEnable \<Boolean>
컴포넌트의 활성화 여부

<br>

### option \<Object>
컴포넌트의 옵션 정보를 담고 있는 객체
```js
this.setOption({isToolBtn: true});
console.log(this.option.isToolBtn);
------------------------------------------------------
true
```

<br>
<br>

## Class Methods


### AComponent.getFocusComp()

현재 포커스 되어있는 컴포넌트를 얻어온다.

- **Returns** \<[AComponent](#AComponent)>

<br/>

### AComponent.realizeContext( context, container, rootView, parentView, listener )

동적으로 로드한 뷰를 사용할 수 있도록 초기화 합니다.

- `context` \<String> 컨텍스트
- `container` \<String> 자신을 담을 컨테이너
- `rootView` \<String> 루트 뷰
- `parentView` \<String> 부모 뷰
- `listener` \<String> 이벤트를 전달받을 객체
- **Returns** \<AComponent>

<br/>


## Instance Methods

### actionToFocusComp()

터치나 마우스 다운 시, 자동으로 포커스를 얻으려면 호출해 준다. 
<br>**컴포넌트 개발 시점** 에 상황에 따라 사용된다.

```js
ACanvas.prototype.init = function(context, evtListener)
{
	AComponent.prototype.init.call(this, context, evtListener);
	
	this.ctx = this.element.getContext('2d');
	
	this.actionToFocusComp(); // <--
};
```
<br>

### addEventListener( evtName, listener, funcName )

컴포넌트에 이벤트를 처리할 listener 와 함수를 추가한다.

* `evtName` \<String> 이벤트 이름 ("click", "focus", ...)
* `listener` \<Object> 이벤트를 전달 받을 객체
* `funcName` \<String> 이벤트 처리 함수 이름
```js
this.myBtn.addEventListener('click', this, 'onMyBtnClick');
//myBtn 에 클릭 이벤트 발생 시 this 의 onMyBtnClick 함수가 호출된다.
```
<br>

### autoShrink( info )

텍스트의 자동 축소 기능이 작동되도록 설정한다.

* `info` \<Object> 축소 정보 객체, { maxChar:15, fontSize:24 }
  * `maxChar` \<Number> 최대 글자 개수 
  * `fontSize` \<Number> 시작 폰트 사이즈
```js
this.myLabel.autoShrink({ maxChar:15, fontSize:24 });

//폰트 사이즈 24를 기본으로 셋팅하고,
//15글자를 넘어가면 상화에 맞게 폰트 사이즈를 축소한다.
```
<br>

### enableDrag( isDraggable, listener )

컴포넌트를 드래그로 이동 가능하도록 만들어 준다. ( Library 폴더 > Add System Lib > DDManager.js 추가 ) 
일반적인 DOM 의 드래그와는 다르며 드래그 시 바로 컴포넌트를 이동 시켜준다. <[DDManager 샘플 참조]()>

- `isDraggable` \<Boolean> 드래그 가능 여부
- `listener` \<Object> 다음과 같은 드래그 이벤트를 수신할 객체
    - `onDragScrollLeft(state)` DDManager 의 dragBound 를 설정한 경우, 드래그가 좌측 끝에 다다른 경우 호출 , state 는 -1(scrollLeft) 또는 1(scrollRight)
    - `onDragScrollTop(state)` DDManager 의 dragBound 를 설정한 경우, 드래그가 상단 끝에 다다른 경우 호출 , state 는 -1(scrollTop) 또는 1(scrollBottom)
    - `onDragStart(dragComp, event)` 드래그가 시작되면 호출
    - `onDragEnd(dragComp, event)` 드래그가 종료되면 호출
    - `onDropFail(dragComp, event)` 드랍 가능한 영역에 드랍되지 않은 경우 호출

```js
function MainView*onInitDone()
{
	super.onInitDone();

	this.myBtn.enableDrag(true, this);
};

function MainView*onDragStart(dragComp, event)
{
    //dragComp is this.myBtn
    //event is javascript event object

};

...

```
<br>

### enableDrop( isDroppable, listener )

다른 컴포넌트가 자신에게 드랍 가능하도록 만들어 준다. ( Library 폴더 > Add System Lib > DDManager.js 추가 ) <[DDManager 샘플 참조]()>

- `isDroppable` \<Boolean> 드랍 가능 여부
- `listener` \<Object> 다음과 같은 드랍 이벤트를 수신할 객체
  - `onCompDrop(dropComp, event)` 다른 컴포넌트가 자신에게 드랍할 경우 호출
```js
function MainView*onInitDone()
{
	super.onInitDone();

    this.myBtn.enableDrag(true, this);
    this.myView.enableDrop(true, this);
};

function MainView*onCompDrop(dropComp, event)
{
    //dropComp is this.myView
    //event is javascript event object

    console.log(event);
    //{ dragComp: .. , touchX: .. , touchY: .. }

    //event.dragComp is this.myBtn

};

...
```
<br>

### get$ele()

this.[$ele](#\$ele-\<jQuery>) 객체를 얻어온다.

- **Returns** \<jQuery>

```js
this.myComp.get$ele().css('color', 'blue');
```
<br>

### getBoundRect()

컴포넌트의 영역 정보를 얻어온다.

- **Returns** \<Object> 
```js
var rt = this.myComp.getBoundRect();
console.log(rt);
//{ left:0, top:0, right: 100, bottom: 100, ... }
```
<br>

### getClassName()

컴포넌트의 클래스명을 얻어온다.

- **Returns** \<String>

<br/>

### getComponentId()

컴포넌트에 셋팅한 아이디를 얻어온다.
- **Returns** \<String>

<br>

### getContainer()

자신을 담고 있는 컨테이너 객체를 얻어온다. 
- **Returns** \<[AContainer](AContainer.md#AContainer)>

<br>

### getContainerId()

자신을 담고 있는 컨테이너의 아이디를 얻어온다.
- **Returns** \<String>

<br>

### getCursor()

컴포넌트의 커서 스타일을 얻어온다.

- **Returns** \<Cursor>

<br>

### getElement()

this.[element](#element-\<HTMLElement>) 객체를 얻어온다.

- **Returns** \<HTMLElement>

<br>

### getGroupName()

컴포넌트에 셋팅한 그룹명을 얻어온다.

- **Returns** \<String>

<br/>

### getHeight()

컴포넌트의 높이 값을 얻어온다.

- **Returns** \<Number>

<br/>

### getNextComp()

부모를 기준으로 레이아웃 트리에서 바로 다음에 위치한 컴포넌트를 얻어온다.

- **Returns** \<[AComponent](#AComponent)>

<br/>

### getParent()

자신을 담고 있는 부모 컴포넌트를 얻어온다.

- **Returns** \<[AView](AView.md#AView)>

<br>

### getPos()

부모 뷰를 기준으로 한 컴포넌트의 위치 정보를 얻어온다.

- **Returns** \<Object> 
  - { left: 100, top: 100 }

<br>

### getPrevComp()

부모를 기준으로 레이아웃 트리에서 바로 이전에 위치한 컴포넌트를 얻어온다.

- **Returns** \<[AComponent](AComponent)>

<br>

### getRootView()

레이아웃 파일상의 최상위 부모 뷰를 얻어온다.

- **Returns** \<[AView](AView.md#AView)>

<br>

### getStyle( propertyName )

propertyName 에 대응하는 this.[element](#element-\<HTMLElement>) 의 style 속성값을 얻어온다.

- `propertyName` \<String>
- **Returns** \<String>

```js
var bgColor = this.myBtn.getStyle('background-color');
//-----------------------------------------------------
//bgColor is rgb(51,51,51)
//this function is like that ...
//bgColor = this.myBtn.element.style['background-color'];
```

<br>

### getTooltip()

현재 설정되어 있는 툴팁 메시지를 얻어온다.

- **Returns** \<String>

<br>

### getWidth()

컴포넌트의 넓이 값을 얻어온다.

- **Returns** \<Number>

<br/>

### hideTooltip()

툴팁 메시지를 숨긴다.

<br/>

### init( context, evtListener )

컴포넌트 객체를 생성한 후 초기화 할 때 호출한다. 코딩을 이용하여 동적으로 객체를 생성할 경우 사용한다. 일반적으로 파라미터를 생략하여 기본값으로 생성 되도록 해준다.

- `context` \<String> 컴포넌트 생성 정보
- `evtListener` \<String> 이벤트 발생 시 수신할 객체

```js

function MainView*onInitDone()
{
    ...

    var btn = new AButton();
    btn.init();
    
    btn.setPos(100, 100);
    btn.setSize(200, 60);
    btn.addEventListener('click', this, 'onMyBtnClick');

    this.addComponent(btn);
}
```

<br/>

### invisible()

컴포넌트가 위치한 공간은 남겨진 채로 컴포넌트를 숨긴다.

<br/>

### isShow()

컴포넌트가 현재 보여지고 있는지를 확인한다.

* **Returns** \<Boolean>

<br/>

### isValid()

컴포넌트의 리소스(this.[element]()) 가 유효한 지를 확인한다. 생성이 안 됐거나 소멸된 경우 false 를 리턴한다.

* **Returns** \<Boolean>

<br>

### offsetPos( dx, dy )

컴포넌트의 현재 위치에서 파라미터 값 만큼 이동한다.

- `dx` \<Number> 이동 할 x값 (left)
- `dy` \<Number> 이동 할 y값 (top)

<br>

### offsetSize( dw, dh )

컴포넌트의 현재 크기에서 파라미터 값 만큼 변경한다.

- `dw` \<Number> 변경할 너비값
- `dh` \<Number> 변경할 높이값

<br>

### removeEventListener( evtName, listener )

컴포넌트에 등록된 이벤트에 대한 listener 를 제거한다. 이 함수를 호출하면 더 이상 이벤트를 전달 받지 않는다.

- `evtName` \<String> 이벤트 이름 ("click", "focus", ...)
- `listener` \<Object> 이벤트를 전달받을 객체

```js
this.myBtn.removeEventListener('click', this);
```

<br>

### reportEvent( evtName, info, event )

자신에게 evtName 으로 등록된 모든 리스너에게 이벤트를 전달한다.
각 컴포넌트 별 이벤트 조건이 만족됐을 경우 자동으로 호출되지만, 코딩을 이용해 임의로 리스너에게 이벤트를 전달하고 싶은 경우 사용할 수 있다.

- `evtName` \<String> 발생시킬 이벤트 이름 ("click", "focus", ...)
- `info` \<Object> 발생된 이벤트 관련 정보, 각 컴포넌트 마다 전달되는 값이 다르며 이벤트 처리 함수의 두번째 파라미터로 전달된다.
- `event` \<Event> 자바스크립트 이벤트 객체, 이벤트 발생 시점의 값을 전달한다.

```js
var event = new Event(); 
...
this.myBtn.reportEvent('click', null, event);
```
<br>

### reportEventDelay( evtName, info, delay, event )

설정한 시간(delay) 후에 이벤트를 발생시킨다. 설명은 [reportEvent](#-reportEvent(-evtName,-info,-event-)) 참조

- `evtName` \<String>
- `info` \<Object>
- `delay` \<Number> 지연 시간
- `event` \<Event>

```js
...
this.myBtn.reportEventDelay('click', null, 100, event);
```
<br>

---
여기부터
---
---


### setClassName( className )

컴포넌트의 클래스 이름을 지정합니다.

* **Parameters**: 
	* **`className`** {String} 클래스명

* **Usage**: 
```js
acomp.setClassName('NewClass');
```

<br/>

### setComponentId( compId )

컴포넌트를 식별하기위한 고유 아이디를 세팅한다.

* **Parameters**: 
	* **`compId`** {String} 컴포넌트 아이디

* **Usage**: 
```js
acomp.setComponentId('CompId');
```

<br/>

### setCompRect( x, y, w, h )

컴포넌트의 위치와 크기값을 일괄 설정 할떄 사용 되는 함수이다. 파라미터 값을 입력할때 px는 생략해야 하며, 값의 단위는 자동으로 px로 입력 된다.

* **Parameters**: 
	* **`x`** {String} x값 (left)
	* **`y`** {Number} y값 (top)
	* **`w`** {Number} 너비 (width)
	* **`h`** {String} 높이 (height)

* **Usage**: 
```js
// px, % 입력불가
acomp.setCompRect(10,20,30,30);
```

<br/>

### setCursor( cursorName )

컴포넌트의 커서 스타일을 설정한다.

* **Parameters**: 
	* **`cursorName`** {String} 커서명

<br/>

### setDataMask( func, param, ele )

데이터 마스크를 설정한다. 데이터가 표시 될 때 설정한 마스크값이 적용되어 표시된다.

* **Parameters**: 
	* **`func`** {Object} 함수
	* **`param`** {String} 파람
	* **`ele`** {HTML Object} 객체

<br/>

### setEventSync( dstEventEle )

setEventSync

* **Parameters**: 
	* **`dstEventEle`** {String} dstEventEle

<br/>

### setFocus()

컴포넌트를 포커싱한다.

<br/>

### setGroupName( groupName )

컴포넌트 그룹을 지정하기위해 그룹명을 세팅한다.

* **Parameters**: 
	* **`groupName`** {String} .

* **Usage**: 
```js
acomp.setGroupName('groupName');
```

<br/>

### setHeight( h )

컴포넌트의 높이를 변경한다.

* **Parameters**: 
	* **`h`** {String} 픽셀단위의 숫자 또는 숫자값에 단위를 포함한 문자 또는 높이값을 반환하는 함수

* **Usage**: 
```js
acomp.setHeight(100);
acomp.setHeight('100px');
acomp.setHeight('10%');
```

<br/>

### setInlineStyle()

컴포넌트가 부모뷰에 일렬로(가로) 정렬되도록 설정한다. 부모뷰의 넓이를 벗어날 경우 다음줄로 이동 된다.

* **Usage**: 
```js
acomp.setInlineStyle();
```

<br/>

### setOption( option )

옵션을 세팅한다.

* **Parameters**: 
	* **`option`** {Object} option

<br/>

### setPos( pos )

컴포넌트의 위치를 세팅한다.

* **Parameters**: 
	* **`pos`** {String} 타입 position {left:10, top:10}

* **Usage**: 
```js
//%는 입력불가
acomp.setPos({left:10, top:10});
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. dataArr은 AQueryData 특정부분의 참조자이다. <br><br> ※ 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조

<br/>

### setShrinkInfo( info )

자동 생략 정보를 설정한다.

* **Parameters**: 
	* **`info`** {Object} ex) {maxChar:15, fontSize:24}

<br/>

### setSize( w, h )

컴포넌트의 너비와 높이를 변경한다.

* **Parameters**: 
	* **`w`** {String} 너비 (width)
	* **`h`** {String} 높이 (height)

* **Usage**: 
```js
// 숫자, px, % 모두 입력이 가능하다.
acomp.setSize(100, 200);
acomp.setSize('100px', '200px');
acomp.setSize('10%', '20%');
```

<br/>

### setStyle( key, value )

컴포넌트에 특정 스타일을 적용한다.

* **Parameters**: 
	* **`key`** {String} 스타일 키
	* **`value`** {String} 스타일 값

* **Usage**: 
```js
acmop.setStyle('left','100px');
```

<br/>

### setStyleObj( obj )

스타일을 정의한 json 객체를 셋팅합니다.

* **Parameters**: 
	* **`obj`** {String} 스타일 오브젝트

* **Usage**: 
```js
acomp.setStyleObj({color: 'black', width: '100px'});
```

<br/>

### setTooltip( ttMsg )

툴팁 메시지를 설정한다.

- `ttMsg` \<String> 메시지

<br>

### setWidth( w )

컴포넌트의 넓이를 변경한다.

- **`w`** \<String> or \<Number> 픽셀단위의 숫자 또는 숫자값에 단위를 포함한 문자 또는 넓이값을 반환하는 함수

<br>

### showTooltip()

툴팁 메시지를 표시한다.

<br/>

### toString()

컴포넌트의 정보를 스트링으로 리턴한다.

<br/>

### updateComponent( queryData )

AQueryData 의 값을 컴포넌트에 반영한다. 내부적으로 setQueryData 를 호출한다.

- **`queryData`** {AQueryData} AQueryData의 전체 값

<br/>

### updatePosition( pWidth, pHeight )

컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. 브라우저의 사이즈가 변경될 경우 자동으로 호출된다.

* **Parameters**: 
	* **`pWidth`** {Number} 부모의 너비
	* **`pHeight`** {Number} 부모의 높이

<br/>

### updateQueryData( queryData )

컴포넌트의 값을 AQueryData 에 채운다. 내부적으로 getQueryData 를 호출한다.

* **Parameters**: 
	* **`queryData`** {AQueryData} AQueryData의 전체 값

<br/>

### visible()

컴포넌트를 보이게 한다.

* **Usage**: 
```js
acomp.visible();
```

<br/>

<br/>

### getContainerView()

자신이 포함된 컨테이너의 메인뷰를 리턴한다.

<br/>

### addClass()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### removeClass()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### getName()

Name 속성으로 지정한 값을 얻어온다.

* **Parameters**:

* **Usage**: 
```js
```

<br/>

### show()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### enable()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### centerX()


<br/>

### centerY()


<br/>

### removeFromView()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### getDataMask()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### loadShrinkInfo()


* **Parameters**:

* **Usage**: 
```js
```

<br>

### setData()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### isDev()


* **Parameters**:

* **Usage**: 
```js
```

<br>
<br>

### Events


### actiondown( comp, info, e )

pc인 경우에는 마우스다운시 호출되고, 모바일인 경우에는 터치가 시작 될 때 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값 (null)
	* **`e`** {Object} 이벤트 정보

### actionenter( comp, info, e )

해당 영역에 마우스가 올라가는 것을 감지하면 호출된다. (자식 영역은 감지하지 않는다.)

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값 (null)
	* **`e`** {Object} 이벤트 정보

### actionleave( comp, info, e )

해당 영역에 마우스가 올라가 있는 상태에서 벗어난 것이 감지되면 호출된다. (자식 영역에서 마우스가 빠져 나가도 감지하지 않는다.)

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값 (null)
	* **`e`** {Object} 이벤트 정보

### actionmove( comp, info, e )

pc인 경우에는 마우스무브시 호출되고, 모바일인 경우에는 터치무브가 발생 중일 때 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값 (null)
	* **`e`** {Object} 이벤트 정보

### actionup( comp, info, e )

pc인 경우에는 마우스업시 호출되고, 모바일인 경우에는 터치업이 발생 될때 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값 (null)
	* **`e`** {Object} 이벤트 정보

### keydown( comp, info, e )

키보드 다운시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값 (null)
	* **`e`** {Object} 이벤트 정보

### keyup( comp, info, e )

키보드업이 발생할 때 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값 (null)
	* **`e`** {Object} 이벤트 정보

<br/>

