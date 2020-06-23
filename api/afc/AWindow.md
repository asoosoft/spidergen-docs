# AWindow( containerId )
**Extends** [`AContainer`](./AContainer.md)

- `containerId` \<String> 컨테이너 아이디

윈도우는 다른 컨테이너 위로 팝업이 가능한 컨테이너를 말한다. 프레임, 타이틀바, 최대, 최소, 닫기 버튼 등의 기본 모양은 갖춰져 있지 않은 상태이며 원하는 모양이나 기능을 추가할 수 있다. 기본적으로 내장되어 있는 컨테이너를 사용하고 싶다면 [`AFrameWnd`](./AFrameWnd.md), [`ADialog`](./ADialog.md) 등이 있다.

```js
var wnd = new AWindow('test');

//넓이와 높이를 생략하면 lay 파일의 넓이와 높이로 오픈된다.
wnd.open('Source/TestView.lay', null, 100, 100);
```

<br>
<br>

## Class Variables

<br>
<br>


## Instance Variables

### option

    기본값은 다음과 같다.
    this.option = 
    {
		isModal: false,		        //modal 여부, 모바일인 경우 기본값이 true 이다.
		isCenter: false,			//창을 중앙에 배치할 지
		isFocusLostClose: false,	//모달인 경우 포커스를 잃을 때 창을 닫을지
		isFocusLostHide: false,		//모달인 경우 포커스를 잃을 때 창을 숨길지
		modalBgOption: 'none',		//none, light, dark 모달인 경우 배경을 어둡기 정도
		overflow: 'hidden',			//hidden, auto, visible, scroll
		dragHandle: null,			//드래가 핸들이 될 클래스명이나 아이디, .windowHandle or #windowHandle
		isResizable: false,         //윈도우 창을 리사이즈 가능하게 할지
		isDraggable: false,         //윈도우 창을 드래그로 움직이게 할지
		inParent: false,			//부모 컨테이너 안에 창을 띄울 경우, 모달리스(isModal:false)이고 부모를 클릭해도 항상 부모보다 위에 보이게 하려면 이 값을 true 로 셋팅해야 한다.
		focusOnInit: true			//init될때 자동으로 윈도우의 첫번째 컴포넌트(tabIndex기준)에 포커스
    }
		
<br>
<br>


## Class Methods

### AWindow.getTopWindow

최상단으로 활성화 되어 있는 윈도우 객체를 얻어온다.<br>
윈도우 오픈 시 최상단으로 팝업되며 이후 show 를 호출해도 최상단으로 활성화 된다.

- **Returns** \<[AWindow](./AWindow.md)>

<br>
<br>

## Instance Methods


### enableDrag()
윈도우의 창 이동 기능을 활성화 시킨다. 윈도우 open 시점에 setOption 의 `isDraggable` 을 통해서도 설정할 수 있다. setDragOption('disabled', `true`/`false`) 를 통해 기능을 스위치 할 수 있다.

<br>

### enableResize()

윈도우의 리사이즈 기능을 활성화 시킨다. 윈도우 open 시점에 setOption 의 `isResizable` 을 통해서도 설정할 수 있다. setResizeOption('disabled', `true`/`false`) 를 통해 기능을 스위치 할 수 있다.

<br>

### move( x, y )

윈도우의 위치를 x, y 로 이동시킨다.

- `x` \<Number> or \<String> 이동할 x 좌표, `10, 10px, 10%`
- `y` \<Number> or \<String> 이동할 y 좌표, `10, 10px, 10%`

```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay');
wnd.move(10, 10);
```
<br>

### moveToCenter()

윈도우를 중앙으로 이동시킨다.

<br>

### moveX( x )

윈도우의 위치를 x 로 이동시킨다.

- `x` \<Number> or \<String> 이동할 x 좌표, `10, 10px, 10%`

<br>

### moveY( y )

윈도우의 위치를 y 로 이동시킨다.

- `y` \<Number> or \<String> 이동할 x 좌표, `10, 10px, 10%`

<br>

### offset( dx, dy )

윈도우의 현재 위치에서 dx, dy 값 만큼 추가적으로 이동시킨다.

- `dx` \<Number> 이동할 x 거리
- `dy` \<Number> 이동할 y 거리

<br/>

### open( url, parent, left, top, width, height )

윈도우를 오픈한다. 내부적으로 AContainer 의 [open](./AContainer.md#open(-url,-parent,-left,-top,-width,-height,-isPopup-)) 함수를 호출한다.

- `url` \<String> 뷰 객체를 로드할 lay 파일의 경로
- `parent` \<[AContainer](./AContainer.md)> 자신의 부모가 될 컨테이너 지정, `null` 인 경우 기본적으로 [mainContainer](#mainContainer)가 되고 설정되어 있지 않으면  [rootContainer](#rootContainer) 순서로 부모가 된다.
- `left` \<String> or \<Number> 윈도우의 x 좌표 `10, '10px', '5%'`
- `top` \<String> or \<Number> 윈도우의 y 좌표
- `width` \<String> or \<Number> 윈도우의 넓이, 생략하면 lay 파일의 뷰 넓이로 셋팅
- `height` \<String> or \<Number> 윈도우의 높이, 생략하면 lay 파일의 뷰 높이로 셋팅

```js
var wnd = new AWindow('window1');
wnd.open('Source/t1.lay', null, 10, 10, 500, 500);
```

<br>

### openAsDialog( viewUrl, parent, width, height )

다이얼로그처럼 작동되도록 옵션을 셋팅하여 윈도우를 오픈한다.<br>
다음과 같이 셋팅한 것과 같다. `{ isModal:true, isCenter:true }`

- `viewUrl` \<String> 윈도우에 보여질 뷰 리소스 url
- `parent` \<[AContainer](./AContainer.md)> 자신의 부모 컨테이너
- `width` \<String> or \<Number> 윈도우의 넓이
- `height` \<String> or \<Number> 윈도우의 높이

<br/>

### openAsMenu( viewUrl, parent, width, height )

팝업메뉴와 같은 속성으로 윈도우를 오픈한다.<br>
다음과 같이 셋팅한 것과 같다. `{ isModal:true, isCenter:true, isFocusLostClose:true }`

- `viewUrl` \<String> 윈도우에 보여질 뷰 리소스 url
- `parent` \<[AContainer](./AContainer.md)> 자신의 부모 컨테이너
- `width` \<String> or \<Number> 윈도우의 넓이
- `height` \<String> or \<Number> 윈도우의 높이

<br/>

### openCenter( viewUrl, parent, width, height )

윈도우를 화면 가운데 위치하도록 오픈한다.

- `viewUrl` \<String> 윈도우에 보여질 뷰 리소스 url
- `parent` \<[AContainer](./AContainer.md)> 자신의 부모 컨테이너
- `width` \<String> or \<Number> 윈도우의 넓이
- `height` \<String> or \<Number> 윈도우의 높이

<br/>

### openFull( viewUrl, parent )

윈도우를 전체 화면으로 오픈한다.

- `viewUrl` \<String> 윈도우에 보여질 뷰 리소스 url
- `parent` \<[AContainer](./AContainer.md)> 자신의 부모 컨테이너

<br>

### setDragOption( key, value )

내부 구현은 다음과 같다. `this.$ele.draggable('option', key, value);` 즉, 컨테이너 element 에 jQuery draggable 을 설정하는 것과 같다. 다음 링크 참조(https://api.jqueryui.com/draggable/)

- `key` \<String> 설정 키
- `value` \<String> 설정 값

```js
var wnd = AWindow();
wnd.setOption({isDraggable: true});
wnd.open(...);

//드래그 기능을 잠시 비활성, false 로 셋팅하면 다시 활성화 된다.
wnd.setDragOption('disabled', true);
```
<br>

### setModalBgOption( option )

윈도우가 modal 로 오픈된 경우 배경 상태를 설정한다.

- `option` \<String> 
  - `light` 불투명도를 밝게
  - `dark` 불투명도를 어둡게
  - `none` 배경 색상 없음

<br/>


### setResizeOption( key, value )
내부 구현은 다음과 같다. `this.$ele.resizable('option', key, value);` 즉, 컨테이너 element 에 jQuery resizable 을 설정하는 것과 같다. 다음 링크 참조(https://api.jqueryui.com/resizable/)

- `key` \<String> 설정 키
- `value` \<String> 설정 값

```js
var wnd = AWindow();
wnd.setOption({isResizable: true});
wnd.open(...);

//리사이즈 기능을 잠시 비활성, false 로 셋팅하면 다시 활성화 된다.
wnd.setResizeOption('disabled', true);
```
<br>

### setResultCallback( callback )

윈도우가 닫힌 후 실행할 콜백함수를 셋팅한다. AContainer 의 [close(result, data)](./AContainer.md#close(-result,-data-)) 함수 호출 시 넘긴 파라미터를 그대로 넘겨준다.

- `callback` \<Function> 콜백함수, function(result, data) { }
  - result \<Number>
  - data \<Object>

```js
var wnd = new AWindow();
wnd.open(...);
wnd.setResultCallback(function(result, data) 
{
    console.log(result);
    console.log(data);
});
```

<br/>

### setResultListener( resultListener )

윈도우 클로즈 시 결과값을 전달 받을 객체를 설정한다. 향후 윈도우가 닫히면 해당 객체의 onWindowResult 함수가 호출되며 AContainer 의 [close(result, data)](./AContainer.md#close(-result,-data-)) 함수 호출 시 넘긴 파라미터를 그대로 넘겨준다.

* `resultListener` \<Object> 결과를 받을 객체

```js
var wnd  = new AWindow('window1');
wnd.setResultListener(this);

//리스너 객체 의 멤버함수
function MainView*onWindowResult(result, data, cntr) 
{
    var cntrId = cntr.getContainerId();

    if(cntrId=='window1')
    {
        console.log(result);
        console.log(data);
    }
};
```

<br>
<br>

## Events


### onDragStart( event, ui )
윈도우의 창 이동이 시작되면 호출된다.
- `event` \<Event> 자바스크립트 이벤트 객체
- `ui` \<Object> jQuery 의 ui 객체

```js
// AWindow > AFrameWnd 를 상속받은 ADockingFrame 의 소스
function ADockingFrame*onDragStart(event, ui)
{
    super.onDragStart(event, ui);

    theApp.getMainContainer().dropPosWnd.show();
};
```
<br>

### onDragStop( event, ui )
윈도우의 창 이동이 중단되면 호출된다.
- `event` \<Event> 자바스크립트 이벤트 객체
- `ui` \<Object> jQuery 의 ui 객체

```js
// AWindow > AFrameWnd 를 상속받은 ADockingFrame 의 소스
function ADockingFrame*onDragStop(event, ui)
{
    super.onDragStop(event, ui);

    theApp.getMainContainer().dropPosWnd.hide();
};
```
<br>