# AView
> **Extends**: `AComponent`

뷰 컴포넌트

<br/>

## Properties

### isActiveActionDelay

탭뷰 컨트롤의 서브뷰가 활성화 될 경우, 일정시간 터치가 불가능하도록 만든다.

* **Type**: `Boolean`
* **Default**: `true`

<br/>

### document



* **Type**: ``
* **Default**: ``

<br/>

### url



* **Type**: ``
* **Default**: ``

<br/>

### compIdPrefix



* **Type**: ``
* **Default**: ``

<br/>

### scrlManagerX



* **Type**: ``
* **Default**: ``

<br/>

### scrlManagerY



* **Type**: ``
* **Default**: ``

<br/>

### ldView



* **Type**: ``
* **Default**: ``

<br/>

### ldCntr



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### addComponent( acomp, isPrepend, posComp )

뷰 내부애 컴포넌트를 추가한다.

* **Parameters**: 
	* **`acomp`** {AComponent} 추가할 컴포넌트
	* **`isPrepend`** {Boolean} 추가 할 위치가 앞인지 여부 (true: 앞,  false: 뒤)
	* **`posComp`** {AComponent} 기준 컴포넌트

* **Usage**: 
```js
var button = new AButton();
button.init();
this.view.addComponent(button, false, this.label);
```

<br/>

### changeCompIdPrefix( newPrefix )

컴포넌트 id 를 변경한다.

* **Parameters**: 
	* **`newPrefix`** {String} compid prefix

* **Usage**: 
```js
this.view.changeCompIdPrefix('newCompId');
```

<br/>

### createView( item, url, owner, eventListener, skipUpdatePos )

뷰를 생성한다.

* **Returns**: AView

* **Parameters**: 
	* **`item`** {Object} dom element (null : div 를 생성)
	* **`url`** {String} 생성할 뷰의 경로
	* **`owner`** {AContainer or AComponent} 자신을 로드한 주체
	* **`eventListener`** {AView} 이벤트를 받을 객체 (null : 자기 자신)
	* **`skipUpdatePos`** {Boolean} .

* **Usage**: 
```js
var view = AView.createView(null, 'Source/t1.lay', this);
```

<br/>

### disableScrlX()

가로스크롤을 사용하지 않도록 설정한다.

* **Usage**: 
```js
this.view.disableScrlX();
```

<br/>

### eachChild( callback, isReverse )

뷰 내부의 컴포넌트를 인자로 하는 콜백함수를 순차적으로 호출한다.

* **Parameters**: 
	* **`callback`** {Function} 콜백함수
	* **`isReverse`** {Boolean} 호출순서를 역순으로 할지 여부

* **Usage**: 
```js
this.view.eachChild(function(comp, index) {
	console.log(comp, index); // 컴포넌트, 순서
}, false);
```

<br/>

### enableActiveFocus( enable )

뷰가 활성화될때 포커스를 가게 할것인지 설정한다.

* **Parameters**: 
	* **`enable`** {Boolean} 설정여부

* **Usage**: 
```js
this.view.enableActiveFocus(true);
```

<br/>

### enableCache( enable )

ajax의 cache 옵션을 사용할지 설정한다.

* **Parameters**: 
	* **`enable`** {Boolean} 사용여부

* **Usage**: 
```js
AView.enableCache(true);
```

<br/>

### enableScrlManagerX()

ScrollManager 의 자체 가로 스크롤이 적용되도록 한다.

* **Usage**: 
```js
this.view.enableScrlManagerX();
```

<br/>

### enableScrlManagerY()

ScrollManager 의 자체 세로 스크롤이 적용되도록 한다.

* **Usage**: 
```js
this.view.enableScrlManagerY();
```

<br/>

### enableScrlX()

가로스크롤을 사용하도록 설정한다.

* **Usage**: 
```js
this.view.enableScrlX();
```

<br/>

### findCompByClass( className )

매개변수 className과 클래스명이 일치하는 뷰 내부의 컴포넌트를 배열로 반환한다.

* **Returns**: Array

* **Parameters**: 
	* **`className`** {String} 컴포넌트 클래스명

* **Usage**: 
```js
var comps = this.view.findCompByClass('ALabel');
console.log(comps);
```

<br/>

### findCompByGroup( strGroup )

매개변수  strGroup과 그룹명이 일치하는 뷰 내부의 컴포넌트를 배열로 반환한다.

* **Returns**: Array

* **Parameters**: 
	* **`strGroup`** {String} 컴포넌트 그룹명

* **Usage**: 
```js
var comps = this.view.findCompByGroup('header');
console.log(comps);
```

<br/>

### findCompById( strId )

매개변수 strId와 컴포넌트id가 일치하는 뷰 내부의 컴포넌트를 반환한다.

* **Returns**: AComponent

* **Parameters**: 
	* **`strId`** {String} 컴포넌트 아이디

* **Usage**: 
```js
var title = this.view.findCompById('title');
console.log(title);
```

<br/>

### getChild( index )

뷰 내부의 컴포넌트중 index 번째 컴포넌트를 반환한다.

* **Returns**: AComponent

* **Parameters**: 
	* **`index`** {Number} 인덱스 넘버 (0부터 시작)

* **Usage**: 
```js
var comp = this.view.getChild(1);
```

<br/>

### getChildCount()

뷰 내부의 컴포넌트의 갯수를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var len = this.view.getChildCount();
```

<br/>

### getChildren()

뷰 내부의 컴포넌트들을 배열로 반환한다.

* **Returns**: Array

* **Usage**: 
```js
var comps = this.view.getChildren();
```

<br/>

### getDocument()

뷰의 document 객체를 반환한다.

* **Returns**: Object

* **Usage**: 
```js
var doc = this.view.getDocument();
```

<br/>

### getFirstChild()

뷰 내부의 첫번째 컴포넌트를 반환한다.

* **Returns**: AComponent

* **Usage**: 
```js
var first = this.view.getFirstChild();
```

<br/>

### getLastChild()

뷰 내부의 마지막 컴포넌트를 반환한다.

* **Returns**: AComponent

* **Usage**: 
```js
var last = this.view.getLastChild();
```

<br/>

### getLoadView()

동적로드된 뷰를 반환한다.

* **Returns**: AView

* **Usage**: 
```js
var v = this.view.getLoadView();
console.log(v);
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채웁니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다

<br/>

### getUrl()

뷰의 url을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var url = this.view.getUrl();
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출합니다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출합니다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {Object} context 에 매핑된 이벤트 수신자

<br/>

### inlineChildren()

뷰 내부의 컴포넌트들을 인라인 스타일로 변경한다.

* **Usage**: 
```js
this.view.inlineChildren();
```

<br/>

### isHscroll()

현재 가로 스크롤이 가능한 상태인지 여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.view.isHscroll();
console.log(b);
```

<br/>

### isMoreScrollBottom()

하단으로 추가적인 스크롤이 가능한지 여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.view.isMoreScrollBottom();
console.log(b);
```

<br/>

### isMoreScrollLeft()

좌측으로 추가적인 스크롤이 가능한지 여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.view.isMoreScrollLeft();
console.log(b);
```

<br/>

### isMoreScrollRight()

우측으로 추가적인 스크롤이 가능한지 여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.view.isMoreScrollRight();
console.log(b);
```

<br/>

### isMoreScrollTop()

상단으로 추가적인 스크롤이 가능한지 여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.view.isMoreScrollTop();
console.log(b);
```

<br/>

### isScroll()

현재 스크롤이 가능한 상태인지 여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.view.isScroll();
console.log(b);
```

<br/>

### isVscroll()

현재 세로 스크롤이 가능한 상태인지 여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.view.isVscroll();
console.log(b);
```

<br/>

### loadContainer( viewUrl, cntrId, cntrClass )

뷰 안에 컨테이너를 설정한다.

* **Returns**: AContainer

* **Parameters**: 
	* **`viewUrl`** {String} 컨테이너안에 설정할 url
	* **`cntrId`** {String} 컨테이너 id
	* **`cntrClass`** {String} 컨테이너 클래스 (null 일 경우 APanel)

* **Usage**: 
```js
this.view.loadContainer('Source/t1.lay', 'cont', null);
```

<br/>

### loadView( url )

뷰 내부에 매개변수 url로 뷰를 동적으로 로드한다.

* **Parameters**: 
	* **`url`** {String} 파일경로

* **Usage**: 
```js
var inner = this.view.createView(null, 'Source/t1.lay', this);
this.view.loadView(inner);
```

<br/>

### removeChildren( onlyRelease )

뷰 내부의 컴포넌트를 모두 삭제한다. onlyRelease 는 내부적으로 사용되므로 생략한다.

* **Parameters**: 
	* **`onlyRelease`** {Boolean} true일 경우 실제로 컴포넌트를 제거하지 않고 연관된 자원만 해제한다.

* **Usage**: 
```js
this.view.removeChildren();
```

<br/>

### removeComponent( acomp )

뷰에서 컴포넌트를 제거한다.

* **Parameters**: 
	* **`acomp`** {AComponent} 제거하고자 하는 컴포넌트 객체

* **Usage**: 
```js
this.view.removeComponent(this.label);
```

<br/>

### removeFromView( onlyRelease )

부모뷰로부터 자신을 제거한다. onlyRelease 는 내부적으로 사용되므로 생략한다.

* **Parameters**: 
	* **`onlyRelease`** {Boolean} true일 경우 실제로 컴포넌트를 제거하지 않고 연관된 자원만 해제한다.

* **Usage**: 
```js
this.view.removeFromView();
```

<br/>

### removeLoadView()

뷰 내부에 동적 로드된 뷰를 제거한다.

* **Usage**: 
```js
this.view.removeLoadView();
```

<br/>

### scrollOffset( offset )

뷰를 현 위치에서 offset 만큼 스크롤 시킨다.

* **Parameters**: 
	* **`offset`** {Number} 스크롤 시킬 거리

* **Usage**: 
```js
this.view.scrollOffset(50);
```

<br/>

### scrollTo( pos )

뷰를 pos 의 위치로 스크롤 시킨다.

* **Parameters**: 
	* **`pos`** {Number} 이동 시킬 위치

* **Usage**: 
```js
this.view.scrollTo(50);
```

<br/>

### scrollToBottom()

뷰를 최하단의 위치로 스크롤 시킨다.

* **Usage**: 
```js
this.view.scrollToBottom();
```

<br/>

### scrollToCenter()

뷰를 중앙의 위치로 스크롤 시킨다.

* **Usage**: 
```js
this.view.scrollToCenter();
```

<br/>

### scrollToTop()

뷰를 최상단의 위치로 스크롤 시킨다.

* **Usage**: 
```js
this.view.scrollToTop();
```

<br/>

### setHtml( html )

뷰 객체 내부에 매개변수 html 을 설정한다.

* **Parameters**: 
	* **`html`** {String} 태그 문자열

* **Usage**: 
```js
var html = '&lt;span&gt;hello&lt;/span&gt;';
this.view.setHtml(html);
```

<br/>

### setScrollArrowX()

뷰에 가로 ScrollArrow을 설정한다.

* **Usage**: 
```js
this.view.setScrollArrowX();
```

<br/>

### setScrollArrowY()

뷰에 세로 ScrollArrow을 설정한다.

* **Usage**: 
```js
this.view.setScrollArrowY();
```

<br/>

### setScrollXComp( acomp )

뷰의 가로스크롤이 움직일때 같이 움직일 컴포넌트를 설정한다.

* **Parameters**: 
	* **`acomp`** {AComponent} 컴포넌트

* **Usage**: 
```js
this.view.setScrollXComp(this.label);
```

<br/>

### setViewInItem( aview, item, owner )

매개변수 aview를 item에 설정하고 aview 를 반환한다.

* **Returns**: AView

* **Parameters**: 
	* **`aview`** {AView} 뷰
	* **`item`** {Object} dom element
	* **`owner`** {AContainer or AComponent} 자신을 로드한 주체

* **Usage**: 
```js
var aview = this.view;
var item = '&lt;div&gt;&lt;/div&gt;';
AView.setViewInItem(aview, item, this);
```

<br/>

### shrinkChildren( radio )

뷰 내부에 있는 컴포넌트들의 높이, 폰트값을 매개변수 ratio 만큼 확대 / 축소한다.

* **Parameters**: 
	* **`radio`** {Float} 배율

* **Usage**: 
```js
this.view.shrinkChildren(0.5);
```

<br/>

### _findTextContains()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### initCrudComponent()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### findChildCrudComp()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### rMateManage()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### ()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### _initDoneManage()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### callSubActiveEvent()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onInitDone()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onWillActive()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onActive()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onActiveDone()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onWillDeactive()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onDeactive()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onDeactiveDone()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### enableScrollIndicatorX()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### enableScrollIndicatorY()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollXImplement()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollYImplement()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollTopManage()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollBottomManage()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollLeftManage()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollRightManage()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### realizeChildren()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setParent()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### findCompByBase()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### findCompByText()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### findCompByName()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setWidth()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setHeight()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### updatePosition()



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

### show()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### hide()



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

### setQueryData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### bindDocument()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setView()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getLoadCntr()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getMappingCount()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getDroppable()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getTabData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setTabData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getItemData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setItemData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getCntrData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setCntrData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### reset()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>

## Events


### longtab( comp, info, e )

길게 탭하는 경우 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트 객체
	* **`info`** {Object} null
	* **`e`** {Object} MouseEvent 객체

### onActive( reload )

ATabView 의 서브뷰인 경우 호출된다. onWillActive 이후에 호출되며 뷰 활성화가 시작되면 매번 호출된다.

* **Parameters**: 
	* **`reload`** {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

### onActiveDone( reload )

ATabView 의 서브뷰인 경우 호출된다. onActive 이후 뷰 활성화 과정이 모두 종료되면 매번 호출된다. show 의 에니메이션이나 특정 이펙트가 완전히 종료된 후 호출

* **Parameters**: 
	* **`reload`** {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

### onDeactive()

ATabView 의 서브뷰인 경우 호출된다. onWillDeactive 이후에 호출되며 뷰 비활성화가 시작되면 매번 호출된다.

### onDeactiveDone()

ATabView 의 서브뷰인 경우 호출된다. onDeactive 이후 뷰 비활성화 과정이 모두 종료되면 매번 호출된다. hide 의 에니메이션이나 특정 이펙트가 완전히 종료된 후 호출

### onWillActive( reload )

ATabView 의 서브뷰인 경우 호출된다. 뷰의 활성화가 시작되기 바로 전에 매번 호출된다.

* **Parameters**: 
	* **`reload`** {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

### onWillDeactive()

ATabView 의 서브뷰인 경우 호출된다. 뷰 비활성화가 시작되기 바로 전에 매번 호출된다.

### scroll( comp, info, e )

스크롤시 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AView} 컴포넌트 객체
	* **`info`** {String} 스크롤 방향(h: 좌우, v: 상하)
	* **`e`** {Object} Event 객체

### scrollbottom( comp, info, e )

스크롤이 바닥에 붙을 때 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AView} 컴포넌트 객체
	* **`info`** {Object} null
	* **`e`** {Object} Event 객체

### scrollleft( comp, info, e )

스크롤이 왼쪽에 붙을 때 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AView} 컴포넌트 객체
	* **`info`** {Object} null
	* **`e`** {Object} Event 객체

### scrollright( comp, info, e )

스크롤이 오른쪽에 붙을 때 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AView} 컴포넌트 객체
	* **`info`** {Object} null
	* **`e`** {Object} Event 객체

### scrolltop( comp, info, e )

스크롤이 위로 붙을 때 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AView} 컴포넌트 객체
	* **`info`** {Object} null
	* **`e`** {Object} Event 객체

### swipe( comp, info, e )

스와이프시 호출되는 이벤트 함수.  info 객체의 direction은 방향이고, distance는 이번 위치값에서 현재 위치값을 뺀 값이다.

* **Parameters**: 
	* **`comp`** {AView} 컴포넌트 객체
	* **`info`** {Object} swipe에 대한 정보 객체 { direction: 'left/right', distance: -100 }
	* **`e`** {Object} MouseEvent 객체

<br/>
<br/>

## Attribute

### Info  

* **Load Url:** 뷰에 로드할 레이아웃 파일(.lay)을 설정하는 속성입니다.  

<br/>
