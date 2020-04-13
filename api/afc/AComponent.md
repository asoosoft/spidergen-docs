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

현재 포커스 되어있는 컴포넌트를 리턴한다.

- **Returns** \<[AComponent](#AComponent)>

<br/>


## Instance Methods

### actionToFocusComp()
터치나 마우스 다운 시, 자동으로 포커스를 얻으려면 호출해 준다. 
<br>컴포넌트 개발 시점에 상황에 따라 내부적으로 사용된다.
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
컴포넌트에 이벤트 리스너와 처리함수를 추가한다.
* `evtName` \<String> 이벤트 이름
* `listener` \<Object> 이벤트 처리 함수가 호출될 객체
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
<br/>

### enableDrag( isDraggable, listener )
컴포넌트를 드래그로 이동 가능하도록 만들어 준다. ( Library 폴더 > Add System Lib > DDManager.js 추가 )<br>
일반적인 DOM 의 드래그와는 다르며 드래그 시 바로 컴포넌트를 이동 시켜준다. [DDManager 샘플 참조]()
* `isDraggable` \<Boolean> 드래그 가능 여부
* `listener` \<Object> 다음과 같은 드래그 이벤트를 수신할 객체
    * `onDragScrollLeft(state)` DDManager 의 dragBound 를 설정한 경우, 드래그가 좌측 끝에 다다른 경우 호출<br>state 는 -1(scrollLeft) 또는 1(scrollRight)
    * `onDragScrollTop(state)` DDManager 의 dragBound 를 설정한 경우, 드래그가 상단 끝에 다다른 경우 호출<br>state 는 -1(scrollTop) 또는 1(scrollBottom)
    * `onDragStart(dragComp, event)` 드래그가 시작되면 호출
    * `onDragEnd(dragComp, event)` 드래그가 종료되면 호출
    * `onDropFail(dragComp, event)` 드랍 가능한 영역에 드랍되지 않은 경우 호출
```js
function MainView*onInitDone()
{
	super.onInitDone();

	this.myBtn.enableDrag(true, this);
};

function MainView*onDragStart(dragComp, event)
{
    //dragComp is this.myBtn
    //event is javascript event object, ex) touchstart

};

...

```
<br>

### enableDrop( isDroppable, listener )
다른 컴포넌트가 자신에게 드랍 가능하도록 만들어 준다. ( Library 폴더 > Add System Lib > DDManager.js 추가 )<br> [DDManager 샘플]()
* `isDroppable` \<Boolean> 드랍 가능 여부
* `listener` \<Object> 다음과 같은 드랍 이벤트를 수신할 객체
  * `onCompDrop(dropComp, event)` 다른 컴포넌트가 자신에게 드랍할 경우 호출
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
    //event is Object

    console.log(event);
    //{ dragComp: .. , touchX: .. , touchY: .. }
    //event.dragComp is this.myBtn

};

...
```

<br/>

### enableKeyPropagation( enable )
>> _이 함수를 외부에 오픈해야 하는지 검토 필요_ 

* `enable` \<Boolean> 활성화 여부
```js
```

<br/>

### get$ele()
this.[$ele](#\$ele-\<jQuery>) 객체를 리턴한다.
- **Returns** \<jQuery> 
```js
this.myComp.get$ele().css('color', 'blue');
```
<br>


### getBoundRect()

컴포넌트의 영역 정보를 리턴한다.

- **Returns** \<Object> 
```js
var rt = this.myComp.getBoundRect();
console.log(rt);
//{ left:0, top:0, right: 100, bottom: 100, ... }
```
<br>

### getClassName()

컴포넌트의 클래스명을 리턴한다.

- **Returns** \<String>

<br/>

### getComponentId()

컴포넌트에 셋팅한 아이디를 리턴한다.
- **Returns** \<String>

<br>

### getContainer()

자신을 담고 있는 컨테이너 객체를 리턴한다. 
- **Returns** \<[AContainer](AContainer.md#AContainer)>

<br>

### getContainerId()

자신을 담고 있는 컨테이너의 아이디를 리턴한다.
- **Returns** \<String>

<br>

### getCursor()

컴포넌트의 커서 스타일을 리턴한다.

- **Returns** \<Cursor>

<br>

### getElement()

this.[element](#element-\<HTMLElement>) 객체를 리턴한다.

- **Returns** \<HTMLElement>

<br>

### getGroupName()

컴포넌트에 셋팅한 그룹명을 리턴한다.

- **Returns** \<String>

<br/>

### getHeight()

컴포넌트의 높이를 리턴한다.
- **Returns** \<Number>

<br/>

### getNextComp()

부모를 기준으로 레이아웃 트리에서 바로 다음에 위치한 컴포넌트를 리턴한다.

- **Returns** \<[AComponent](#AComponent)>

<br/>

### getParent()

자신을 담고 있는 부모 컴포넌트를 리턴

- **Returns** \<[AView](AView.md#AView)>

<br/>


---
여기부터...



### getPos()

오프셋 부모를 기준으로 컴포넌트의 좌표(top, left 속성이 포함된 객체)를 리턴한다.<br/>* 컴포넌트가 숨겨져있으면 좌표는 얻을 수 없다.

* **Returns**: Position

* **Usage**: 
```js
var result = acomp.getPos();
```

<br/>

### getPrevComp()

바로 이전 컴포넌트를 리턴한다.

* **Returns**: AComponent

* **Usage**: 
```js
var result = acomp.getPrevComp();
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다. dataArr은 AQueryData 특정부분의 참조자이다. <br><br> ※ 자세한 구조 및 상세설명은 QuerySystem.pptx 문서를 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조

<br/>

### getRootView()

자신을 담고 있는 루트 뷰 객체를 리턴한다. 루트 뷰란 레이아웃 파일상의 최상위 뷰를 가르킨다.

* **Returns**: AView

* **Usage**: 
```js
var rootView = acomp.getRootView();
```

<br/>

### getSgapH()

부모뷰와의 상대 마진높이값을 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var result = acomp.getSgapH();
```

<br/>

### getSgapW()

부모뷰와의 상대 마진너비값을 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var result = acomp.getSgapW();
```

<br/>

### getStyle( key )

파라미터로 넘어온 키에 대응되는 스타일 값을 리턴한다.

* **Parameters**: 
	* **`key`** {String} 스타일 키

* **Usage**: 
```js
var left= acomp.getStyle('left');
```

<br/>

### getTooltip()

툴팁메시지를 리턴한다.

* **Returns**: String

<br/>

### getWidth()

컴포넌트의 넓이 값을 단위없는 픽셀값으로 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var result = acomp.getWidth();
```

<br/>

### hideTooltip()

툴팁 메시지를 숨긴다.

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {String} context 에 매핑된 이벤트 수신자

* **Usage**: 
```js
//AComponent의 init은 상속받는 컴포넌트에서 오버라이딩해서 사용한다.
// 해당 컴포넌트의 init함수에서 다음과 같은 방식으로 호출한다.

AComponent.prototype.init.call(this, context, evtListener);
```

<br/>

### invisible()

컴포넌트를 숨긴다.

* **Usage**: 
```js
acomp.invisible();
```

<br/>

### isShow()

컴포넌트가 현재 보여지고 있는지를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = acomp.isShow();
```

<br/>

### isValid()

컴포넌트가 유효한지 여부를 리턴한다. 생성이 아직 안 됐거나 소멸된 경우 null값을 리턴한다.

* **Returns**: Object

* **Usage**: 
```js
acomp.isValid();
```

<br/>

### loadDataMask( ele )

컴포넌트에 설정되어있는 데이터 마스크를 리턴한다.

* **Returns**: ADataMask

* **Parameters**: 
	* **`ele`** {HTML Object} 컴포넌트의 엘리먼트

<br/>

### loadEventInfo( evtListener )

컴포넌트의 이벤트구현 클래스를 로드한다.

* **Parameters**: 
	* **`evtListener`** {Object} 이벤트 리스너

<br/>

### loadQueryInfo()

컴포넌트의 쿼리 정보를 로드한다.

<br/>

### offsetPos( dx, dy )

컴포넌트의 현재 위치에서 파라미터만큼 이동한다.

* **Parameters**: 
	* **`dx`** {String} 이동 할 x값 (left)
	* **`dy`** {String} 이동 할 y값 (top)

* **Usage**: 
```js
// %는 입력불가능. px는 생략하고 입력해야한다.
acomp.offsetPos(10, 20);
```

<br/>

### offsetSize( dw, dh )

컴포넌트의 현재 크기에서 파라미터의 크기만큼 각각 더한다.

* **Parameters**: 
	* **`dw`** {String} 변경할 너비값
	* **`dh`** {String} 변경할 높이값

* **Usage**: 
```js
//%는 입력불가, px는 생략하고 입력해야한다.
acomp.offsetSize(10, 30);
```

<br/>

### preValMerge( comp, data, keyArr )

받은 데이터의 key 값이 없을 경우 이전 데이터를 merge하여 채운다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`data`** {Array} 데이터 배열
	* **`keyArr`** {Array} 키 배열

<br/>

### AComponent.realizeContext( context, container, rootView, parentView, listener )

동적으로 로드한 뷰를 사용할 수 있도록 초기화 합니다.

* **Returns**: AComponent

* **Parameters**: 
	* **`context`** {String} 컨텍스트
	* **`container`** {String} 자신을 담을 컨테이너
	* **`rootView`** {String} 루트 뷰
	* **`parentView`** {String} 부모 뷰
	* **`listener`** {String} 이벤트를 전달받을 객체

<br/>

### release()

컴포넌트와 연관된 자원들을 해제한다. 직접 호출하지 말아야 한다.

* **Usage**: 
```js
acomp.release();
```

<br/>

### reloadTooltip()

툴팁 메시지를 다시 로드한다.

<br/>

### removeAttr( key )

컴포넌트의 속성값을 삭제한다.

* **Parameters**: 
	* **`key`** {String} 속성 키

* **Usage**: 
```js
acomp.removeAttr('data-flag');
```

<br/>

### removeEventListener( evtName, listener )

컴포넌트에 등록된 listener 정보를 제거한다. 이 함수를 호출하면 이벤트 전달이 중단된다.

* **Parameters**: 
	* **`evtName`** {String} 이벤트 이름(click, focus, ...)
	* **`listener`** {String} 이벤트를 전달받는 객체

* **Usage**: 
```js
acomp.removeEventListener('change', this);
```

<br/>

### removeFromAQuery()

AQuery로부터 컴포넌트의 쿼리정보를 삭제한다. 컴포는트의 release될때 자동으로 호출된다.

<br/>

### reportEvent( evtName, info, event )

컴포넌트에 evtName 으로 등록된 모든 리스너에게 이벤트를 전달한다.

* **Parameters**: 
	* **`evtName`** {String} 이벤트 이름(click, focus, ...)
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값
	* **`event`** {String} 이벤트

* **Usage**: 
```js
acomp.reportEvent('select', info, event);
```

<br/>

### reportEventDelay( evtName, info, delay, event )

설정한 시간 후에 이벤트를 발생시킨다.

* **Parameters**: 
	* **`evtName`** {String} 발생 시킬 이벤트
	* **`info`** {String} 이벤트 발생 시 넘겨줄 데이터
	* **`delay`** {String} 딜레이 시간
	* **`event`** {String} 이벤트정보

* **Usage**: 
```js
acomp.reportEventDelay('select',info, 100, event);
```

<br/>

### setAttr( key, value )

컴포넌트에 속성 값을 적용한다.

* **Parameters**: 
	* **`key`** {String} 속성 키
	* **`value`** {String} 속성 값

* **Usage**: 
```js
acomp.setAttr('data-flag','1111');
```

<br/>

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

### AComponent.setFocusComp( newComp )

새로 포커스 된 컴포넌트를 등록합니다.

* **Parameters**: 
	* **`newComp`** {AComponent} 새로 포커스 된 컴포넌트

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

### setParent( parent )

컴포넌트의 부모를 설정한다. addComponent 만 호출하면 이전 부모에서 삭제하지 않아도 자동으로 새로운 부모로 이동한다. <br><br> ※ 주의 : 내부적으로 사용하는 함수로 직접 호출하지 말것! 실제로 컴포넌트의 부모를 바꾸려면 parentObj.addComponent 를 사용해야 한다.

* **Parameters**: 
	* **`parent`** {String} 타입 AView

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

### setSgapH( sgapH )

컴포넌트의 높이를 부모뷰로부터의 상대값으로 설정한다. (stretch)

* **Parameters**: 
	* **`sgapH`** {String} 높이값

* **Usage**: 
```js
acomp.setSgapH(100);
acomp.setSgapH('100px');
acomp.setSgapH('10%');
```

<br/>

### setSgapW( sgapW )

컴포넌트의 너비를 부모뷰로부터의 상대값으로 설정한다. (stretch)

* **Parameters**: 
	* **`sgapW`** {String} 너비값

* **Usage**: 
```js
acomp.setSgapW(100);
acomp.setSgapW('100px');
acomp.setSgapW('10%');
```

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

* **Parameters**: 
	* **`ttMsg`** {String} 메시지

<br/>

### setWidth( w )

컴포넌트의 넓이를 변경한다.

* **Parameters**: 
	* **`w`** {String or Number} 픽셀단위의 숫자 또는 숫자값에 단위를 포함한 문자 또는 넓이값을 반환하는 함수

* **Usage**: 
```js
acomp.setWidth(100);
acomp.setWidth('100px');
acomp.setWidth('10%');
```

<br/>

### showTooltip()

툴팁 메시지를 표시한다.

<br/>

### toString()

컴포넌트의 정보를 스트링으로 리턴한다.

<br/>

### unbindEvent( eventName, callback )

등록되어있는 이벤트를 해제한다.

* **Parameters**: 
	* **`eventName`** {String} 이벤트명
	* **`callback`** {Function} 콜백함수

<br/>

### updateChildMappingComp( dataArr, queryData )

queryData값을 자식 컴포넌트에도 반영한다.

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`queryData`** {Array} AQueryData의 전체 값, 필요시 참조

<br/>

### updateComponent( queryData )

AQueryData 의 값을 컴포넌트에 반영한다. 내부적으로 setQueryData 를 호출한다.

* **Parameters**: 
	* **`queryData`** {AQueryData} AQueryData의 전체 값

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

### createElement()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### getContainerView()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### getAttr()


* **Parameters**:

* **Usage**: 
```js
```

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


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### centerY()


* **Parameters**:

* **Usage**: 
```js
```

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

<br/>

### actionDelay()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### initTooltip()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### getCompStyleObj()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

### setCompStyleObj()


* **Parameters**:

* **Usage**: 
```js
```

<br/>

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

<br/>
<br/>
## Events


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

