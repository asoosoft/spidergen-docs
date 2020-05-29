# AWindow
> **Extends** : [AContainer](#AContainer)

윈도우

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
		dragHandle: null,
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

- **Returns** \<[AWindow](#AWindow)>

<br>
<br>

## Instance Methods


### enableResize( enable )

윈도우의 리사이즈 변경 가능여부를 설정한다.


### move( x, y )

윈도우의 위치를 매개변수 x, y 의 위치로 이동시킨다.

* `x` \<String> 이동할 x 좌표
* `y` \<String> 이동할 y 좌표

```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay', this.getContainer(), 500, 500);
wnd.move(10, 10);
```

<br>

### moveToCenter()

윈도우를 가운데로 이동시킨다.

<br/>

### moveX( x )

윈도우의 x좌표를 변경하여 이동시킨다.

* `x` {String or Number} 이동할 x 좌표 ex)10, '10px', '10%'

<br/>

### moveY( y )

윈도우의 y좌표를 변경하여 이동시킨다.

* `y` {String or Number} 이동할 y 좌표 ex)10, '10px', '10%'

<br/>

### offset( x, y )

윈도우의 현재 위치에서 매개변수 x, y 값 만큼 더 이동시킨다.

* `x` {Number} 이동할 x 거리 (px단위)
* `y` {Number} 이동할 y 거리 (px단위)

<br/>

### open( viewUrl, parent, left, top, width, height )

윈도우를 오픈한다.

* `viewUrl` {String} 윈도우에 보여질 뷰 리소스 url
* `parent` {AContainer} 윈도우를 open 한 주체, onWindowResult 콜백을 받을 객체
* `left` {String or Number} 윈도우의 x 좌표 ex) 10, '10px', '5%'
* `top` {String or Number} 윈도우의 y 좌표 ex) 100, '100px', '10%'
* `width` {String or Number} 윈도우의 넓이 ex) 600, '600px', '70%'
* `height` {String or Number} 윈도우의 높이 ex) 800, '800px', '90%'

```js
var wnd = new AWindow('window1');
 wnd.open('Source/t1.lay', null, 10, 10, 500, 500);
```

<br/>

### openAsDialog( viewUrl, parent, width, height )

다이얼로그처럼 작동되도록 옵션을 셋팅하여 윈도우를 오픈한다.<br/>다음의 옵션이 적용된다.<br/>{isModal:true, isCenter:true}

* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
* **`parent`** {AContainer} 윈도우를 open 한 주체, onWindowResult 콜백을 받을 객체
* **`width`** {String or Number} 윈도우의 넓이 ex) 600, '600px', '70%'
* **`height`** {String or Number} 윈도우의 높이 ex) 800, '800px', '90%'

```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay', null, 500, 500);
```

<br/>

### openAsMenu( viewUrl, parent, width, height )

팝업메뉴와 같은 속성으로 윈도우를 오픈한다.<br>
다음의 옵션이 적용된다.<br> 
{isModal:true, isCenter:true, isFocusLostClose:true}

* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
* **`parent`** {AContainer} 윈도우를 open 한 주체 onWindowResult 콜백을 받을 객체
* **`width`** {String or Number} 윈도우의 넓이 ex) 600, '600px', '70%'
* **`height`** {String or Number} 윈도우의 높이 ex) 800, '800px', '90%'

```js
var wnd = new AWindow('window1');
wnd.openAsMenu('Source/t1.lay', null, 500, 500);
```

<br/>

### openCenter( viewUrl, parent, width, height )

윈도우를 화면 가운데 위치하도록 오픈한다.

* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
* **`parent`** {AContainer} 윈도우를 open 한 주체, onWindowResult 콜백을 받을 객체
* **`width`** {String or Number} 윈도우의 넓이, ex) 600, '600px', '70%'
* **`height`** {String} 윈도우의 높이, ex) 800, '800px', '90%'

```js
var wnd = new AWindow('window1');
wnd.openCenter('Source/t1.lay', null, 500, 500);
```

<br/>

### openFull( viewUrl, parent )

윈도우를 화면전체로 오픈한다.

* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
* **`parent`** {AContainer} 윈도우를 open 한 주체, onWindowResult 콜백을 받을 객체

```js
var wnd = new AWindow('window1');
wnd.openFull('Source/t1.lay', null);
```

<br/>


### setModalBgOption( option )

모달창의 백그라운드 색상을 설정한다.

* **`option`** {String} light: 투명도를 약하게, dark: 투명도를 진하게, 그 외 설정안함

```js
var w = new AWindow('w1');
w.setModalBgOption('none');
```

<br/>

### setResultCallback( callback )

윈도우 클로즈시 실행할 콜백함수를 선언한다.

* **`callback`** {Function} 콜백함수

```js
var w = new AWindow('w1');
w.optn();

w.setResultCallback(function(result) {
    console.log(result);
});
```

<br/>

### setResultListener( resultListener )

close시 결과에 대한 이벤트를 주체가 되는 컨테이너의 onWindowResult 호출할 것인지를 세팅합니다.<br/><br/>윈도우 클로즈시 결과값에 대한 리스너를 설정한다.<br/>해당 리스너의 onWindowResult 함수가 호출된다.

* **`resultListener`** {AContainer} 주체가 되는 컨테이너

```js
var wnd  = new AWindow('window1');
wnd.setResultListener(this);

//리스너
function main:onWindowResult(result, data, thisObj) {
//결과 처리
};
```


<br>
<br>

## Events

### onBackKey()
### onClose()
### onCreate()

### onResize()


