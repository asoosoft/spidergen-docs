# AView
**Extends**: [`AComponent`](./AComponent.md)

화면 구성은 AView 에 다른 컴포넌트를 담으면서 이루어진다. AView 클래스는 유일하게 다른 컴포넌트를 자식으로 담을 수 있는 컴포넌트이다. 즉, 모든 컴포넌트의 getParent 는 AView 이다. 컨테이너에 담겨 화면을 표현하는 시작 지점이 되기도 하며 부분적으로 화면 폼을 구성하는 역할도 한다. 

<br/>

## Class Variables

<br/>

## Instance Variables

<br/>

## Class Methods

<br/>

## Instance Methods

### addComponent( acomp, isPrepend, posComp ) 

뷰 내부에 컴포넌트를 추가한다.

- `acomp` \<[`AComponent`](./AComponent.md)> 추가할 컴포넌트
- `isPrepend` \<Boolean> 추가 할 위치가 앞인지 여부 (true: 앞,  false: 뒤)
- `posComp` \<[`AComponent`](./AComponent.md)> 기준 컴포넌트

```js
var button = new AButton();
button.init();
this.view.addComponent(button, false, this.label);
```
<br/>

### disableScrlX() 

가로 스크롤을 비활성화한다. [enableScrlManagerX](#enableScrlManagerX())를 통해 구현된 경우에만 동작한다.

<br/>

### eachChild( callback, isReverse ) 

뷰 내부의 컴포넌트를 인자로 하는 콜백함수를 순차적으로 호출한다.

- `callback` \<Function> 콜백함수
- `isReverse` \<Boolean> 호출순서를 역순으로 할지 여부
```js
this.view.eachChild(function(comp, index) {
	console.log(comp, index); // 컴포넌트, 순서
	//콜백함수내에서 return false는 each함수를 중단시킨다.
	//for문의 break와 동일한 역할
	return false; 

	//콜백함수내에서 return true는 다음 루프로 이동한다.
	//for문의 continue와 동일한 역할

}, false);
```

<br/>

### enableActiveFocus( enable ) 

뷰가 활성화 될때 포커스를 여부를 설정한다.

- `enable` \<Boolean> 포커스 여부

<br/>

### enableScrlManagerX() 
터치 이벤트를 핸들링하여 자체적으로 구현한 가로 스크롤 기능을 활성화 한다. 내부적으로 [ScrollManager](../library/ScrollManager.md) 가 사용된다.

<br/>

### enableScrlManagerY() 

터치 이벤트를 핸들링하여 자체적으로 구현한 세로 스크롤 기능을 활성화 한다. 내부적으로 [ScrollManager](../library/ScrollManager.md) 가 사용된다.

<br/>

### enableScrlX() 

가로 스크롤을 활성화한다. [enableScrlManagerX](#enableScrlManagerX())를 통해 구현된 경우에만 동작한다.

<br/>

### findCompByBase( baseName ) 

매개변수 baseName과 베이스명이 일치하는 뷰 내부의 컴포넌트를 배열로 반환한다. 여기서 베이스명은 컴포넌트가 확장되기 이전의 클래스명을 뜻한다.

- `baseName` \<String> 컴포넌트 베이스명
- **Returns** \<Array>

```js
var compArr = this.view.findCompByBase('ALabel');
//컴포넌트가 배열로 리턴된다.
console.log(compArr); 
```

<br/>

### findCompByClass( className ) 

매개변수 className과 클래스명이 일치하는 뷰 내부의 컴포넌트를 배열로 반환한다.

- `className` \<String> 컴포넌트 클래스명
- **Returns** \<Array>

```js
var compArr = this.view.findCompByClass('ALabel');
//컴포넌트가 배열로 리턴된다.
console.log(compArr); 
```

<br/>

### findCompByGroup( strGroup ) 

매개변수 strGroup과 그룹명이 일치하는 뷰 내부의 컴포넌트 그룹을 배열로 반환한다.

- `strGroup` \<String> 컴포넌트 그룹명
- **Returns** \<Array>

```js
var compArr = this.view.findCompByGroup('header');
//컴포넌트가 배열로 리턴된다.  ex) [ AButton, ALabel ... ]
console.log(compArr); 
```

<br/>

### findCompById( strId ) 

매개변수 strId와 컴포넌트 아이디가 일치하는 뷰 내부의 컴포넌트를 반환한다.

- `strId` \<String> 컴포넌트 아이디
- **Returns** \<[`AComponent`](./AComponent.md)>
```js
//아이디가 label1인 컴포넌트를 리턴받아서 사용하는 예제
var comp = this.view.findCompById('label1');
comp.setText('제목');
```

<br/>

### findCompByName( name ) 

컴포넌트의 name 속성이 매개변수 name과 일치하는 뷰 내부의 컴포넌트를 배열로 반환한다.

- `name` \<String> 컴포넌트 name 속성
- **Returns** \<Array>

```js
var compArr = this.view.findCompByName('name1');
//컴포넌트의 네임속성이 name1인 컴포넌트가 배열로 리턴된다.
console.log(compArr); 
```
<br/>

### findCompByText( text ) 

컴포넌트의 텍스트가 매개변수 text와 일치하는 뷰 내부의 컴포넌트를 배열로 반환한다.

- `text` \<String> 컴포넌트 텍스트
- **Returns** \<Array>

```js
var compArr = this.view.findCompByText('제목');
//텍스트가 제목인 컴포넌트를 배열로 리턴된다.
console.log(compArr); 
```
<br/>

<br/>

### getChild( index ) 

뷰 내부의 컴포넌트중 index 번째 컴포넌트를 반환한다.

- `index` \<Number> 인덱스 넘버 (0부터 시작)
- **Returns** \<[`AComponent`](./AComponent.md)>

<br/>

### getChildCount() 

뷰 내부의 컴포넌트의 갯수를 반환한다.

- **Returns** \<Number>

<br/>

### getChildren() 

뷰 내부의 컴포넌트들을 배열로 반환한다.

- **Returns** \<Array>

<br/>

### getCntrData() 

뷰 컴포넌트의 컨테이너의 데이터를 반환한다.

- **Returns** \<All> 저장된 데이터

<br/>

### getFirstChild() 

뷰 내부의 첫번째 컴포넌트를 반환한다.

- **Returns** \<[`AComponent`](./AComponent.md)>

<br/>

### getItemData() 

슬라이드뷰나 리스트뷰에 로드되어진 경우 선택시 넘겨준 데이터를 얻어온다.

- **Returns** \<All> 저장된 데이터

```js
//슬라이드뷰나 리스트뷰에서 서브아이템 SampleSubView에서
//getItemData를 통해 데이터를 전달받을수있다.
class SampleSubView()
{
	super();

}
extends AView;

function SampleSubView*onInitDone()
{
	var tabData = this.getItemData();
};
```

<br/>

### getLastChild() 

뷰 내부의 마지막 컴포넌트를 반환한다.

- **Returns** \<[`AComponent`](./AComponent.md)>

<br/>

### getLoadCntr() 

loadContaine 메소드로 불러온 컨테이너를 반환한다.

- **Returns** \<[`AContainer`](./AContainer.md)>

<br/>

### getLoadView() 

동적 로드된 뷰를 반환한다.

- **Returns** \<AView>

```js
var innerView = this.view.getLoadView();
```

<br/>

### getTabData() 

탭뷰에 로드되어진 경우 선택시 넘겨준 데이터를 얻어온다.

- **Returns** \<ALL> 저장된 데이터

```js
//탭뷰에서 아래의 SampleSubView가 선택됐을경우에
//해당 뷰에서 getTabData를 통해 데이터를 전달받을수있다.
class SampleSubView()
{
	super();
}
extends AView;

//선택될때 마다 데이터가 바뀐다면
//onActive에서 호출해야함.
function SampleSubView*onActive()
{
	super.onActive();
	var tabData = this.getTabData();
	...
};
```

### getUrl() 

뷰의 url을 반환한다.

- **Returns** \<String>

<br/>

### init( context, evtListener ) 

컴포넌트를 생성하고 초기화 할 때 호출합니다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출해야 합니다.

- `context` \<Object> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<Object> context 에 매핑된 이벤트 수신자

```js
var sampleView = new AView();
sampleView.init();
```

<br/>

### inlineChildren() 

뷰 내부의 컴포넌트들을 인라인 스타일로 변경한다.

<br/>

### isHscroll() 

현재 가로 스크롤이 가능한 상태인지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isMoreScrollBottom() 

하단으로 추가적인 스크롤이 가능한지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isMoreScrollLeft() 

좌측으로 추가적인 스크롤이 가능한지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isMoreScrollRight() 

우측으로 추가적인 스크롤이 가능한지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isMoreScrollTop() 

상단으로 추가적인 스크롤이 가능한지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isScroll() 

현재 스크롤이 가능한 상태인지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isVscroll() 

현재 세로 스크롤이 가능한 상태인지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### loadContainer( viewUrl, cntrId, cntrClass ) 

뷰 안에 컨테이너를 설정한다.

- `viewUrl` \<String> 컨테이너안에 설정할 url 경로
- `cntrId` \<String> 컨테이너 id
- `cntrClass` \<String> 컨테이너 클래스 (null 일 경우 APanel)

- **Returns** \<[`AContainer`](./AContainer.md)>

```js
this.view.loadContainer('Source/t1.lay', 'contId');
```

<br/>

### loadView( url ) 

뷰 내부에 매개변수 url로 뷰를 동적으로 로드한다.

- `url` \<String> 파일경로

- **Returns** \<AView>
```js
//로드된 뷰가 리턴된다.
var innerView = this.view.loadView('Source/t1.lay');
```

<br/>

### removeChildren( onlyRelease ) 

뷰 내부의 컴포넌트를 모두 삭제한다. onlyRelease 는 내부적으로 사용되므로 생략한다.

- `onlyRelease` \<Boolean> true일 경우 실제로 컴포넌트를 제거하지 않고 연관된 자원만 해제한다.

```js
this.view.removeChildren();
```

<br/>

### removeComponent( acomp ) 

뷰에서 컴포넌트를 제거한다.

- `acomp` \<[`AComponent`](./AComponent.md)> 제거하고자 하는 컴포넌트 객체

```js
//this.label1이 참조하는 컴포넌트를 뷰에서 제거한다.
this.view.removeComponent(this.label1);
```

<br/>

### removeFromView( onlyRelease ) 

부모뷰로부터 자신을 제거한다. onlyRelease 는 내부적으로 사용되므로 생략한다.

- `onlyRelease` \<Boolean> true일 경우 실제로 컴포넌트를 제거하지 않고 연관된 자원만 해제한다.

<br/>

### removeLoadView() 

뷰 내부에 동적 로드된 뷰를 제거한다.

<br/>

### scrollOffset( offset ) 

뷰를 현 위치에서 offset 만큼 스크롤 시킨다.

- `offset` \<Number> 스크롤 시킬 거리
```js
//현재 위치에서 50을 더한다.
this.view.scrollOffset(50);
```

<br/>

### scrollTo( pos ) 

뷰를 pos 의 위치로 스크롤 시킨다.

- `pos` \<Number> 이동 시킬 위치

<br/>

### scrollToBottom() 

뷰를 최하단의 위치로 스크롤 시킨다.

<br/>

### scrollToCenter() 

뷰를 중앙의 위치로 스크롤 시킨다.

<br/>

### scrollToTop() 

뷰를 최상단의 위치로 스크롤 시킨다.

<br/>

### setCntrData(data) 

뷰 컴포넌트의 컨테이너에 데이터를 세팅한다.

- `data` \<All> 저장할 데이터

<br/>

### setHtml( html ) 

뷰 객체 내부에 매개변수 html 을 설정한다.

- `html` \<String> 태그 문자열

```js
var html = '<span>hello</span>';
this.view.setHtml(html);
```

<br/>

### setScrollArrowX() 

뷰에 가로 ScrollArrow을 설정한다. 내부적으로 [ScrollArrow](../library/ScrollArrow.md#)를 사용한다.

<br/>

### setScrollArrowY() 

뷰에 세로 ScrollArrow을 설정한다. 내부적으로 [ScrollArrow](../library/ScrollArrow.md#)를 사용한다.

<br/>

### setScrollXComp( acomp ) 

뷰의 가로 스크롤이 움직인 만큼 같이 움직일 컴포넌트를 설정한다. [enableScrlManagerX](#enableScrlManagerX())를 통해 구현한 경우에만 동작한다.

- `acomp` \<[`AComponent`](./AComponent.md)> 컴포넌트
```js
this.view.setScrollXComp(this.label);
```

<br/>

### setItemData(data) 

슬라이드뷰나 리스트뷰에 로드 될 떄 데이터를 세팅한다.

- `data` \<All> 저장할 데이터

<br/>

### setTabData(data) 

탭뷰에 로드 될 때 데이터를 세팅한다. 일반적으로 탭뷰에서 [addTab](./ATabView.md#addTab)나 [selectTab](./ATabView.md#selectTab)될때 데이터를 지정하면 자동으로 호출해준다.

- `data` \<All> 저장할 데이터

<br/>

### shrinkChildren( radio ) 

뷰 내부에 있는 컴포넌트들의 높이, 폰트값을 매개변수 ratio 만큼 확대 / 축소한다.

- `radio` \<Float> 배율 (0~1)

<br/>

### setWidth(w) 

컴포넌트의 넓이를 지정한다.

- `w` \<String>or\<Number> 컴포넌트 넓이 값

```js
this.view.setWidth(10);
this.view.setWidth('10px');
this.view.setWidth('100%');
```

<br/>

### setHeight(h) 

컴포넌트의 높이를 지정한다.

- `h` \<String>or\<Number> 컴포넌트 높이 값

```js
this.view.setHeight(10);
this.view.setHeight('10px');
this.view.setHeight('100%');
```

<br/>

### updatePosition( pWidth, pHeight ) 

뷰 컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. 일반적으로 
브라우저의 사이즈가 변경되면 자동으로 뷰 컴포넌트와 모든 하위 컴포넌트의 updatePosition 함수가 자동으로 호출된다. 

- `pWidth` \<Number> 부모뷰의 넓이
- `pHeight` \<Number> 부모뷰의 높이

```js
class SampleView()
{
	super();

}
extends AView;

//부모뷰의 사이즈가 변경됨에 따라 추가로 처리해야 할 사항이 있을 경우, 
//이 함수를 override 하여 처리해 준다.
function SampleView*updatePosition(pWidth, pHeight)
{
    super.updatePosition(pWidth, pHeight);
	
    console.log(pWidth + ', ' + pHeight);

	//TODO:edit here
	
	...
};
```

```js
//view1 또는 view1의 하위 컴포넌트의 위치값이나 크기 조정 후에
//refresh 목적으로 다음과 같이 직접 호출해도 된다.
this.view1.updatePosition();
```
<br>

## Events

### longtab( comp, info, e )

길게 탭하는 경우 호출되는 이벤트 함수.

- `comp` \<AView> 컴포넌트 객체
- `info` \<null> null
- `e` \<Object> MouseEvent 객체
  
<br>

### onWillActive( isFirst )

ATabView 의 서브뷰인 경우 호출된다. 뷰의 활성화가 시작되기 바로 전에 매번 호출된다.

- `isFirst` \<String> 최초에만 true이다.

```js
//이벤트를 받으려는 화면에서 아래와 같이 구현하면 된다.
function SampleView*onWillActive(isFirst)
{
	//AView에 있는 onWillActive를 override한다.
	super.onWillActive(isFirst);

	//TODO:edit here
};
```

<br>

### onActive( isFirst )

ATabView 의 서브뷰인 경우 호출된다. onWillActive 이후에 호출되며 뷰 활성화가 시작되면 매번 호출된다.

- `isFirst` \<String> 최초에만 true이다.
```js
//이벤트를 받으려는 화면에서 아래와 같이 구현하면 된다.
function SampleView*onActive(isFirst)
{
	//AView에 있는 onWillActive를 override한다.
	super.onActive(isFirst);

	//TODO:edit here
};
```

<br>

### onActiveDone( isFirst )

ATabView 의 서브뷰인 경우 호출된다. onActive 이후 뷰 활성화 과정이 모두 종료되면 매번 호출된다. show 의 에니메이션이나 특정 이펙트가 완전히 종료된 후 호출된다.

- `isFirst` \<String> 최초에만 true이다.
```js
//이벤트를 받으려는 화면에서 아래와 같이 구현하면 된다.
function SampleView*onActiveDone(isFirst)
{
	//AView에 있는 onWillActive를 override한다.
	super.onActiveDone(isFirst);

	//TODO:edit here
};
```

<br>

### onWillDeactive()

ATabView 의 서브뷰인 경우 호출된다. 뷰 비활성화가 시작되기 바로 전에 매번 호출된다.

```js
//이벤트를 받으려는 화면에서 아래와 같이 구현하면 된다.
function SampleView*onWillDeactive()
{
	//AView에 있는 onWillActive를 override한다.
	super.onWillDeactive();

	//TODO:edit here
};
```

<br>

### onDeactive()

ATabView 의 서브뷰인 경우 호출된다. onWillDeactive 이후에 호출되며 뷰 비활성화가 시작되면 매번 호출된다.

```js
//이벤트를 받으려는 화면에서 아래와 같이 구현하면 된다.
function SampleView*onDeactive()
{
	//AView에 있는 onWillActive를 override한다.
	super.onDeactive();

	//TODO:edit here
};
```

<br>

### onDeactiveDone()

ATabView 의 서브뷰인 경우 호출된다. onDeactive 이후 뷰 비활성화 과정이 모두 종료되면 매번 호출된다. hide 의 에니메이션이나 특정 이펙트가 완전히 종료된 후 호출된다.

```js
//이벤트를 받으려는 화면에서 아래와 같이 구현하면 된다.
function SampleView*onDeactiveDone()
{
	//AView에 있는 onWillActive를 override한다.
	super.onDeactiveDone();

	//TODO:edit here
};
```

<br>

### scroll( comp, info, e )

스크롤시 호출되는 이벤트 함수.

- `comp` \<AView> 컴포넌트 객체
- `info` \<String> 스크롤 방향(h: 좌우, v: 상하)
- `e` \<Object> Event 객체
  
### scrollbottom( comp, info, e )

스크롤이 바닥에 붙을 때 호출되는 이벤트 함수.

- `comp` \<AView> 컴포넌트 객체
- `info` \<null> null
- `e` \<Object> Event 객체

### scrollleft( comp, info, e )

스크롤이 왼쪽에 붙을 때 호출되는 이벤트 함수.

- `comp` \<AView> 컴포넌트 객체
- `info` \<null> null
- `e` \<Object> Event 객체

### scrollright( comp, info, e )

스크롤이 오른쪽에 붙을 때 호출되는 이벤트 함수.

- `comp` \<AView> 컴포넌트 객체
- `info` \<null> null
- `e` \<Object> Event 객체

### scrolltop( comp, info, e )

스크롤이 위로 붙을 때 호출되는 이벤트 함수.

- `comp` \<AView> 컴포넌트 객체
- `info` \<null> null
- `e` \<Object> Event 객체

### swipe( comp, info, e )

스와이프시 호출되는 이벤트 함수.  info 객체의 direction은 방향이고, distance는 이번 위치값에서 현재 위치값을 뺀 값이다.

- `comp` \<AView> 컴포넌트 객체
- `info` \<Object> swipe에 대한 정보 객체 
  - { direction: 'left/right', distance: -100 }
- `e` \<Object> MouseEvent 객체

<br/>
