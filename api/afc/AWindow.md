# AWindow( containerId )
**Extends** [`AContainer`](./AContainer.md)

- `containerId` \<String> 컨테이너 아이디

윈도우는 다른 컨테이너 위로 팝업이 가능한 컨테이너를 말한다. 프레임, 타이틀바, 닫기버튼 등의 기본 모양은 갖춰져 있지 않은 상태이며 원하는 모양이나 기능을 추가할 수 있다. 기본적으로 내장되어 있는 컨테이너를 사용하고 싶다면 [`AFrameWnd`](./AFrameWnd.md), [`ADialog`](./ADialog.md) 등이 있다.

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
		isModal: afc.isMobile,		//모바일이면 기본을 modal 로 셋팅, 위에 설명 참조.
		isCenter: false,			//자동 중앙정렬 할지
		isFocusLostClose: false,	//모달인 경우 포커스를 잃을 때 창을 닫을지
		isFocusLostHide: false,		//모달인 경우 포커스를 잃을 때 창을 숨길지
		modalBgOption: afc.isMobile ? 'dark' : 'none',		//none, light, dark 모달인 경우 배경을 어둡기 정도
		overflow: 'hidden',			//hidden, auto, visible, scroll
		dragHandle: null,			//드래가 핸들이 될 클래스명이나 아이디, .windowHandle or #windowHandle
		isResizable: false,         //윈도우 창을 리사이즈 가능하게 할지
		isDraggable: false,         //윈도우 창을 드래그로 움직이게 할지
		inParent: false,			//부모 컨테이너 안에 창을 띄울 경우, 모달리스(isModal:false)이고 부모를 클릭해도 항상 부모보다 위에 보이게 하려면 이 값을 true 로 셋팅해야 한다.
		focusOnInit: true,			//init될때 자동으로 윈도우의 첫번째 컴포넌트(tabIndex기준)에 포커스
		activePropagation: true		//윈도우가 닫힐 때 활성화 되는 컨테이너의 active 호출여부(onWillActive, onActive, onActiveDone)
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


### enableResize( enable )

윈도우의 리사이즈 기능을 활성/비활성 시킨다.
- `enable` \<Boolean>

### move( x, y )

윈도우의 위치를 매개변수 x, y 의 위치로 이동시킨다.

- `x` \<Number> or \<String> 이동할 x 좌표, `10, 10px, 10%`
- `y` \<Number> or \<String> 이동할 y 좌표, `10, 10px, 10%`

```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay', this.getContainer(), 500, 500);
wnd.move(10, 10);
```

<br>

### moveToCenter()

윈도우를 상하 좌우 중앙으로 이동시킨다.

<br>

### moveX( x )

윈도우의 x좌표를 변경하여 이동시킨다.

- `x` \<Number> or \<String> 이동할 x 좌표, `10, 10px, 10%`

<br/>

### moveY( y )

윈도우의 y좌표를 변경하여 이동시킨다.

- `y` \<Number> or \<String> 이동할 x 좌표, `10, 10px, 10%`

<br/>

### offset( dx, dy )

윈도우의 현재 위치에서 dx, dy 값 만큼 추가적으로 이동시킨다.

- `dx` \<Number> 이동할 x 거리
- `dy` \<Number> 이동할 y 거리


<br/>

### open( viewUrl, parent, left, top, width, height )

윈도우를 오픈한다. 내부적으로 AContainer 의 [open](#open(-url,-parent,-left,-top,-width,-height,-isPopup-)) 함수를 호출한다.

- `viewUrl` \<String> 윈도우에 보여질 뷰 리소스 url
- `parent` \<[AContainer](./AContainer.md)> 자신의 부모 컨테이너
- `left` \<String> or \<Number> 윈도우의 x 좌표 `10, '10px', '5%'`
- `top` \<String> or \<Number> 윈도우의 y 좌표
- `width` \<String> or \<Number> 윈도우의 넓이
- `height` \<String> or \<Number> 윈도우의 높이

```js
var wnd = new AWindow('window1');
 wnd.open('Source/t1.lay', null, 10, 10, 500, 500);
```

<br/>

### openAsDialog( viewUrl, parent, width, height )

다이얼로그처럼 작동되도록 옵션을 셋팅하여 윈도우를 오픈한다.<br>
다음의 옵션이 적용된다.`{ isModal:true, isCenter:true }`

- `viewUrl` \<String> 윈도우에 보여질 뷰 리소스 url
- `parent` \<[AContainer](./AContainer.md)> 자신의 부모 컨테이너
- `width` \<String> or \<Number> 윈도우의 넓이
- `height` \<String> or \<Number> 윈도우의 높이

<br/>

### openAsMenu( viewUrl, parent, width, height )

팝업메뉴와 같은 속성으로 윈도우를 오픈한다.<br>
다음의 옵션이 적용된다.`{ isModal:true, isCenter:true, isFocusLostClose:true }`

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

윈도우를 화면전체로 오픈한다.

- `viewUrl` \<String> 윈도우에 보여질 뷰 리소스 url
- `parent` \<[AContainer](./AContainer.md)> 자신의 부모 컨테이너

<br>


### setModalBgOption( option )

모달창의 백그라운드 색상을 설정한다.

- `option` \<String> light: 투명도를 약하게, dark: 투명도를 진하게, 그 외 설정안함

<br/>

### setResultCallback( callback )

윈도우 클로즈 시 실행할 콜백함수를 셋팅한다.

- `callback` \<Function> 콜백함수

```js
var w = new AWindow('w1');
w.open(...);

w.setResultCallback(function(result) {
    console.log(result);
});
```

<br/>

### setResultListener( resultListener )

윈도우 클로즈 시 결과값에 대한 리스너를 설정한다. 해당 리스너의 onWindowResult 함수가 호출된다.

* `resultListener` \<Object> 결과를 받을 리스너 객체

```js
var wnd  = new AWindow('window1');
wnd.setResultListener(this);

//리스너
function MainView*onWindowResult(result, data, thisObj) 
{

};
```

<br>
<br>

## Events

### onBackKey()

<br>

### onClose()

<br>

### onCreate()

<br>

### onResize()

<br>

