# AComponent

최상위 추상 컴포넌트

<br/>

## Properties

### element \<HTMLElement>

컴포넌트를 구성하고 있는 HTMLElement 객체

```js
//순수 자바스크립트와 같이 다음 코드가 동작한다.
this.element.style.color = 'blue';
```

<br>

### $ele \<jQuery>

this.element 의 jQuery 객체

```js
//jQyery 와 같이 다음 코드가 동작한다.
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

<br>
<br>

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

### addClass( styleName )

컴포넌트에 스타일 클래스를 추가한다. jQuery 의 addClass 와 같다.

* `styleName` \<String> 스타일 클래스 이름 

```js
this.myBtn.addClass('normalBtn');
//------------------------------------- same result
this.myBtn.$ele.addClass('normalBtn');
```

<br>

### addEventListener( evtName, listener, funcName )

컴포넌트에 이벤트를 처리할 listener 와 함수를 추가한다.

- `evtName` \<String> 이벤트 이름 ("click", "focus", ...)
- `listener` \<Object> 이벤트를 전달 받을 객체
- `funcName` \<String> 이벤트 처리 함수 이름

```js
this.myBtn.addEventListener('click', this, 'onMyBtnClick');
//myBtn 에 클릭 이벤트 발생 시 this 의 onMyBtnClick 함수가 호출된다.
```

<br>

### centerX()

컴포넌트가 부모 넓이의 가로 중앙에 위치 하도록 해준다. 부모의 넓이가 바뀌어도 중앙을 유지한다.

<br>

### centerY()

컴포넌트가 부모 높이의 세로 중앙에 위치 하도록 해준다. 부모의 높이가 바뀌어도 중앙을 유지한다.

<br>

### enable( isEnable )

컴포넌트를 활성/비활성 상태로 만든다.

- `isEnable` \<Boolean> 활성화 여부, **true / false**

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

컴포넌트 객체의 클래스명을 얻어온다.

- **Returns** \<String>

```js
var name = this.myBtn.getClassName();
console.log(name);
//------------------------------------------------------
//AButton
```

<br>

### getComponentId()

컴포넌트에 셋팅한 아이디를 얻어온다. [setComponentId()](#-setComponentId(-compId-)) 참조
- **Returns** \<String>

<br>

### getContainer()

자신을 담고 있는 컨테이너 객체를 얻어온다. 
- **Returns** \<[AContainer](./AContainer.md)>

<br>

### getContainerId()

자신을 담고 있는 컨테이너의 아이디를 얻어온다.
- **Returns** \<String>

<br>

### getContainerView()

자신을 담고 있는 컨테이너의 메인뷰를 얻어온다.

- **Returns** \<[AView](./AView.md)>
```js
var view1 = this.getContainerView();
//------------------------------------------ same result
var view2 = this.getContainer().getView();
```
<br>

### getCursor()

컴포넌트의 커서 스타일을 얻어온다. [setCursor()](#-setCursor(-cursorName-)) 참조

- **Returns** \<String>

<br>

### getData()

컴포넌트에 세팅된 데이터를 추출한다.
- 자식 컴포넌트 : 자신의 특성에 맞는 데이터를 반환한다.
- 부모 컴포넌트 : [AView](./AView.md), [AFlexLayout](./AFlexLayout.md), [AGridLayout](./AGridLayout.md) 과 같은 부모 컴포넌트는 자식 컴포넌트들의 데이터를 추출하여 Object 또는 Array 데이터를 반환한다.
<br />[AView](./AView.md) 는 getDataAsArray 옵션값이 false 면 Object 를 true 면 Array 를 반환한다.

- **Returns** \<All> 컴포넌트 데이터

```js
this.label.getData();
//'data1'
this.view.getData();
//['data1', 'data2', 'data3'] 또는
//{name1: 'data1', name2: 'data2', name3: 'data3'}
```

### getDataMask(idx, ele)

컴포넌트에 세팅한 마스킹(데이터를 가공하는) 함수와 파라미터를 얻어온다.

- `idx` \<Number> 마스킹 함수의 위치값
- `ele` \<HTMLElement> 마스킹 함수를 얻어올 엘리먼트 객체(기본값: 컴포넌트 엘리먼트)

- **Returns** \<[ADataMask](./ADataMask.md)> 또는 \<Array>
	- idx 지정 안한 경우 ADataMask 객체
    - idx 지정을 한 경우[ 해당 위치 마스킹함수, 해당 위치 마스킹 파라미터 ]
```js
this.label.setDataMask(ADataMask.Number.money.func);
this.label.getDataMask(); //ADataMask
this.label.getDataMask(idx); //[ ADataMask.Number.money.func, undefined ]
```


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

### getName()

컴포넌트에 지정한 name 값을 얻어온다. 

* **Returns** \<String>

<br>

### getNextComp()

부모를 기준으로 레이아웃 트리에서 바로 다음에 위치한 컴포넌트를 얻어온다.

- **Returns** \<[AComponent](#AComponent)>

<br/>

### getParent()

자신을 담고 있는 부모 컴포넌트를 얻어온다.

- **Returns** \<[AView](./AView.md)>

<br>

### getPos()

부모 뷰를 기준으로 한 컴포넌트의 위치 정보를 얻어온다.

- **Returns** \<Object> 
  - { left: 100, top: 100 }

<br>

### getPrevComp()

부모를 기준으로 레이아웃 트리에서 바로 이전에 위치한 컴포넌트를 얻어온다.

- **Returns** \<[AComponent](#AComponent)>

<br>

### getRootView()

레이아웃 파일상의 최상위 부모 뷰를 얻어온다.

- **Returns** \<[AView](./AView.md)>

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

### removeClass( styleName )

컴포넌트에서 스타일 클래스를 제거한다. jQuery 의 removeClass 와 같다.

* `styleName` \<String> 스타일 클래스 이름 

```js
this.myBtn.removeClass('normalBtn');
//------------------------------------- same result
this.myBtn.$ele.removeClass('normalBtn');
```

<br>

### removeEventListener( evtName, listener )

컴포넌트에 등록된 이벤트에 대한 listener 를 제거한다. 이 함수를 호출하면 더 이상 이벤트를 전달 받지 않는다.

- `evtName` \<String> 이벤트 이름 ("click", "focus", ...)
- `listener` \<Object> 이벤트를 전달받을 객체

```js
this.myBtn.removeEventListener('click', this);
```

<br>

### removeFromView()

자신의 부모뷰로부터 자신을 제거한다.

```js
function MainView*onTestFunc()
{
    //this is AView
    this.removeComponent(this.myBtn);
    //-------------------------------------- same result
    this.myBtn.removeFromView();

    ...
};
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

### setComponentId( compId )

컴포넌트의 아이디를 세팅한다. 모듈뷰(lay파일) 를 기준으로, 컴포넌트 아이디는 중복될 수 없다. 차후 지정된 아이디 값으로 컴포넌트 객체를 얻어올 수 있다. 

- `compId` \<String> 컴포넌트 아이디

```js
function MainView*onInitDone()
{
	super.onInitDone();

    var btn = new AButton();
    btn.init();
    btn.setText('OK');
    ...
    btn.setComponentId('okBtn');

    this.addComponent(btn);
};

function MainView*changeBtnText()
{
    var okBtn = this.findCompById('okBtn');
    okBtn.setText('Yes');
};
```

<br>

### setCompRect( x, y, w, h )

컴포넌트의 위치와 크기값을 일괄 설정 할 때 사용 되는 함수이다. 

- `x` \<Number> 가로 위치 (left)
- `y` \<Number> 세로 위치 (top)
- `w` \<Number> 넓이 값 (width)
- `h` \<Number> 높이 값 (height)

<br>

### setCursor( cursorName )

컴포넌트의 마우스 커서 스타일을 설정한다. (마우스를 컴포넌트 위로 이동했을 경우 변경되는 모양)

- `cursorName` \<String> [커서이름](https://developer.mozilla.org/ko/docs/Web/CSS/cursor) 참조

```js
function MainView*onInitDone()
{
	super.onInitDone();

    this.okBtn.setCursor('pointer');
};
```

<br>

### setData( data )

컴포넌트에 데이터를 세팅한다.
- 자식 컴포넌트 : 데이터를 수신하여 자신의 특성에 맞게 표현한다. 
- 부모 컴포넌트 : [AView](./AView.md), [AFlexLayout](./AFlexLayout.md), [AGridLayout](./AGridLayout.md) 과 같은 부모 컴포넌트는 Object 또는 Array 데이터로 자식 컴포넌트들에 데이터를 세팅한다.
<br />Object 이면 key 값과 동일한 컴포넌트를 찾아서 데이터를 세팅하고, Array 이면 인덱스 순서와 동일한 순서의 자식 컴포넌트에 데이터를 세팅한다.

- `data` \<All> 컴포넌트에 세팅할 데이터(모든 데이터 타입)
```js
this.label.setData('data1');
this.view.setData(['data1', 'data2', 'data3']);
this.view.setData({name1: 'data1', name2: 'data2', name3: 'data3'});
```
<br>

### setDataMask( func, param, ele )

컴포넌트에 데이터를 세팅할 때 자동으로 호출되는 마스킹(데이터를 가공하는) 함수를 지정한다. 자세한 사항은 [마스크 세팅하기]() 를 참고.

- `func` \<Function> 마스킹(데이터를 가공하는) 함수
- `param` \<Array> 마스킹 함수에 전달될 파라미터 배열
- `ele` \<HTMLElement> 마스킹 함수를 세팅할 엘리먼트 객체(기본값: 컴포넌트 엘리먼트 객체)
```js
this.label.setDataMask(function(val, param, ele)
{
	ele.style.color = '#ff0000';
	return param[0] + val + param[1];
}, ['param1', 'param2']);
//XXX -> param1XXXparam2
this.label.setDataMask(ADataMask.Number.money.func);
//12345 -> 123.45
```

<br>

### setEventSync( dstEventEle )

자신에게 발생한 **ACTION_DOWN, ACTION_MOVE, ACTION_UP** 이벤트를 dstEventEle 에게도 동시에 발생되도록 해준다. 기존에 셋팅된 element 가 있으면 삭제하고 새로운 값으로 셋팅한다.<br> <[EventSync 샘플 참조]()>
- `dstEventEle` \<HTMLElement> 이벤트를 발생시킬 html element 

<br>

### setFocus()

자신이 포커스를 갖도록 해준다.

<br/>

### setGroupName( groupName )

컴포넌트 그룹 명을 지정해 준다. 그룹명은 중복 가능하며 같은 그룹명을 가지 컴포넌트들을 배열로 얻어올 수 있다.

- `groupName` \<String> 컴포넌트 그룹명

```js
function MainView*onInitDone()
{
	super.onInitDone();

    this.myBtn1.setGroupName('form1');
    this.myBtn2.setGroupName('form1');
    this.myTxt1.setGroupName('form1');
};

function MainView*removeTestGroup()
{
    //comps is Array
    var comps = this.findCompByGroup('form1');
    
    for(var comp of comps)
    {
        //comp is AComponent
        comp.removeFromView();
    }
};
```

<br>

### setHeight( h )

컴포넌트의 높이를 셋팅한다.

- **`h`** \<Number> 컴포넌트의 높이

<br>

### setName( name )

컴포넌트에 name 속성값을 지정한다. 

- **`name`** \<String> 지정한 Name 속성값

<br>

### setOption( option, noOverwrite )

컴포넌트의 옵션을 세팅한다. this.[option](#-option-\<Object>) 에 값을 셋팅해 주는 역할을 하며, option 의 세부 내용은 각 컴포넌트 마다 다르다.

- `option` \<Object> 설정 값
- `noOverwrite` \<Boolean> true 이면, 기존의 값이 존재할 경우 덮어쓰지 않는다.
```js
this.myBtn.setOption({
	isToolBtn: true,
    isCheckBtn: true
});
```

<br>

### setPos( x, y )

컴포넌트의 위치를 세팅한다.

- `x` \<Number> 가로 위치 (left) **또는** \<Object> {left:100, top:100}
- `y` \<Number> 세로 위치 (top)

```js
this.myBtn.setPos(10, 10);
this.myBtn.setPos({left:10, top:10});
```

<br>

### setShrinkInfo( info )

컴포넌트 텍스트의 자동 축소 기능이 작동 되도록 설정한다. 최대 글자 개수를 넘어가면 상황에 맞게 폰트 사이즈를 축소해 준다.

* `info` \<Object> 축소 정보 객체, { maxChar:8, fontSize:24 }
  * `maxChar` \<Number> 최대 글자 개수 
  * `fontSize` \<Number> 시작 폰트 사이즈

```js
this.myLabel.setShrinkInfo({ maxChar:8, fontSize:24 });

//폰트 사이즈 24를 기본으로 셋팅하고,
// 8 글자를 넘어가면 상황에 맞게 폰트 사이즈를 축소한다.
this.myLabel.setText('이름을 입력해 주세요');
```

<br>

### setSize( w, h )

컴포넌트의 넓이와 높이를 변경한다.

- `w` \<Number> 넓이 (width)
- `h` \<Number> 높이 (height)

<br>

### setStyle( key, value )

컴포넌트의 스타일(css) 값을 셋팅한다. 이 함수의 내부 코드는 다음과 같다.<br>
`this.element.style[key] = value;`

- `key` \<String> 스타일 속성 이름
- `value` \<String> 스타일 속성 값

```js
this.myBtn.setStyle('width', '100%');
```

<br>

### setStyleObj( obj )

컴포넌트의 스타일(css) 값을 Object 로 셋팅한다. 

- `obj` \<Object> 스타일 정보 객체

```js
this.myBtn.setStyleObj({color: 'black', width: '100px'});
```

<br/>

### setTooltip( ttMsg )

컴포넌트의 툴팁 메시지를 설정한다.

- `ttMsg` \<String> 메시지

<br>

### setWidth( w )

컴포넌트의 넓이를 셋팅한다.

- `w` \<Number> 컴포넌트의 넓이

<br>

### show()

this.[invisible](#-invisible)() 또는 this.[hide](#-hide)() 함수로 숨긴 컴포넌트를 보이게 한다.

<br>

### hide()

컴포넌트를 숨긴다.(display: none;)

<br>

### showTooltip()

툴팁 메시지를 보여준다.

<br/>

### toString()

컴포넌트의 정보를 문자열로 리턴한다.

- **Returns** \<String>

```js
console.log(this.myBtn.toString());
---------------------------------------
{
    element : [object HTMLButtonElement],
    $ele : jQuery,
    parent : AView,
    eventStop : true,
    isEnable : true,
    events : Object,
    baseName : AButton,
    className : AButton,
    compId : testBtn,
    groupName : null,
    dataKeyMap : null,
    mappingType : 0,
    sgapW : null,
    sgapH : null,
    rect : ARect,
    option : Object,
    btnStyles : Array,
    isTabable : true,
    reInitComp : false,
    defStyle :  testbtn,
    baseState : Object,
    aevent : AButtonEvent,
    ttMsg : null,
    $img : jQuery,
    isSafeClick : true,
    isChecked : false,
}
```

<br>

### updatePosition( pWidth, pHeight )

브라우저의 사이즈가 변경되면 자동으로 모든 컴포넌트의 updatePosition 함수가 호출된다. 부모뷰의 사이즈가 변경됨에 따라 추가로 처리해야 할 사항이 있을 경우, 이 함수를 override 하여 처리해 준다.

- `pWidth` \<Number> 부모뷰의 넓이
- `pHeight` \<Number> 부모뷰의 높이

```js
class MyCanvas()
{
	super();

}
extends ACanvas;

function MyCanvas*updatePosition(pWidth, pHeight)
{
    super.updatePosition(pWidth, pHeight);
	
    console.log(pWidth + ', ' + pHeight);

	this.resizeMyCanvas();
	
	...
};
```
<br>

### visible()

this.[invisible](#-invisible())() 함수로 숨긴 컴포넌트를 보이게 한다.

<br>
<br>


## Events

해당 이벤트에 대한 처리 함수는 사용자가 지정하며 함수로 전달되는 파라미터는 공통이다.

- **Parameters**: 
	- `comp` \<[AComponent](#AComponent)> 이벤트가 발생한 컴포넌트
	- `info` \<Object> 발생한 이벤트 정보, 이벤트 종류에 따라 내용이 다름
	- `event` \<Event> 자바스크립트 이벤트 객체

```js
function MainView*onInitDone()
{
	super.onInitDone();

    this.myBtn.addEventListener('click', this, 'onMyBtnClick');
};

function MainView*onMyBtnClick(comp, info, event)
{
    //comp is this.myBtn
    console.log(info);
    console.log(event);
}
```

<br>

### actiondown

mousedown 또는 touchstart 인 경우 발생하는 이벤트, 컴포넌트 영역에 mouse down 하거나 touch 하게 되면 발생되는 이벤트

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>

### actionenter

mouseenter 인 경우 발생하는 이벤트, 마우스 커서가 컴포넌트 내부로 진입하는 경우 발생하는 이벤트

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>

### actionleave

mouse leave 인 경우에 발생하는 이벤트, 마우스 커서가 컴포넌트 내부에서 벗어난 경우 발생하는 이벤트 
- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>

### actionmove

mousemove 또는 touchmove 인 경우 발생하는 이벤트, 컴포넌트 영역에서 mouse move 하거나 touch move 하게 되면 발생되는 이벤트

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>

### actionup

mouseup 또는 touchend 인 경우 발생하는 이벤트, 컴포넌트 영역에서 mouse up 하거나 touch end 하게 되면 발생되는 이벤트

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>

### keydown

컴포넌트가 포커스된 상태에서 키보드가 눌려지면 발생되는 이벤트

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>

### keyup

컴포넌트가 포커스된 상태에서 키보드가 떼어지면 발생되는 이벤트

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>

