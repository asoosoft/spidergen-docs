# AWindow
> **Extends**: `AContainer`

윈도우 컨테이너

<br/>

## Properties


### frame

로드한 layout 리소스를 감싸고 있는 frame(div)

* **Type**: `jQuery Object`
* **Default**: `null`

<br/>

### isOpenActionDelay

윈도우가 open 된 후 잠깐동안 터치가 되지 않도록 할지 여부 윈도우 내부에 ATextField 가 있는 경우 키패드가 자동으로 올라오는 오류를 막기위함.

* **Type**: `Boolean`
* **Default**: `true`

<br/>

### modalBg

모달용 배경 div

* **Type**: `HTML Object`
* **Default**: `null`

<br/>

### openContainer

윈도우를 open 한 주체가 속한 컨테이너 opener 와 openContainer 는 같을 수 있다

* **Type**: `AContainer`
* **Default**: `null`

<br/>

### opener

윈도우를 open 한 주체 onWindowResult 콜백을 받을 객체

* **Type**: `AContainer`
* **Default**: `null`

<br/>

### option

윈도우 옵션 <br/>isModal: true, //모달 윈도우인지 <br/>isAutoCenter: false, //자동 중앙정렬 할지 <br/>isFocusLostClose: false, //모달인 경우 포커스를 잃을 때 창을 닫을지 <br/>isFocusLostHide: false, //모달인 경우 포커스를 잃을 때 창을 숨길지 <br/>modalBgOption: 'dark', //none, light, dark 모달인 경우 배경을 어둡기 정도 <br/>overflow: 'hidden', //hidden, auto, visible, scroll

* **Type**: `Object`
* **Default**: 

<br/>

### url

윈도우로 사용할 리소스 url, /main/test.lay

* **Type**: `String`
* **Default**: `null`

<br/>
<br/>

## Methods

### addWindow( awnd )

윈도우를 오픈하면 자동으로 호출된다.<br/>내부에 있는 저장소에 윈도우를 추가한다.

* **Returns**: boolean

* **Parameters**: 
	* **`awnd`** {AWindow} 윈도우객체

<br/>

### close( result, data )

윈도우를 닫는다. 매개변수 result , data 값이 윈도우에 setResultCallback 으로 등록된 콜백함수에 전달된다.

* **Parameters**: 
	* **`result`** {String} 콜백으로 전달할 결과
	* **`data`** {Object} 콜백으로 전달할 데이터

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.setResultCallback(function(result, data) {
  console.log(result, data);
});
wnd.close('result', {data: 'data1'});
```

<br/>

### enableResize( enable )

윈도우의 리사이즈 변경 가능여부를 설정한다.

* **Parameters**: 
	* **`enable`** {Boolean} 가능여부

* **Usage**: 
```js
var w = new AWindow('w1');
w.enableResize(true);
```

<br/>

### findWindow( cntrId )

내부에 있는 저장소에서 매개변수 cntrId 에 대응하는 윈도우를 반환한다.

* **Returns**: AWindow

* **Parameters**: 
	* **`cntrId`** {String} 컨테이너 ID

* **Usage**: 
```js
var w = AWindow.findWindow('window1');
```

<br/>

### getTopWindow()

보여지고 있는 윈도우 중 최상단 윈도우를 반환한다.

* **Returns**: AWindow

* **Usage**: 
```js
var w = AWindow.getTopWindow();
```

<br/>

### hide()

윈도우를 오픈한후 삭제하지 않고 숨길경우 사용한다.<br/>show 메서드를 통해 다시 표시할 수 있다.

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.hide();
```

<br/>

### makeTopWindow( toTopWnd, isFirst )

매개변수 toTopWnd 객체를 최상위 윈도우로 올리고 active, deactive 이벤트등을 발생시킨다.

* **Parameters**: 
	* **`toTopWnd`** {AWindow} 윈도우 객체
	* **`isFirst`** {Boolean} 최초 실행여부

* **Usage**: 
```js
var w = AWindow.findWindow('window2');
AWindow.makeTopWindow(w, true);
```

<br/>

### modalManage( zIndex )

내부적으로 사용되는 함수입니다.<br/>또한<br/>윈도우가 모달 모드인 경우에 처리되는 함수이며 모달창 아래 div요소를 활성화합니다.

* **Parameters**: 
	* **`zIndex`** {Number} z-index의 배치 순서

<br/>

### move( x, y )

윈도우의 위치를 매개변수 x, y 의 위치로 이동시킨다.

* **Parameters**: 
	* **`x`** {String} 이동할 x 좌표 ex)10, '10px', '10%'
	* **`y`** {String} 이동할 y 좌표 ex)10, '10px', '10%'

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay', this.getContainer(), 500, 500);
wnd.move(10, 10);
```

<br/>

### moveToCenter()

윈도우를 가운데로 이동시킨다.

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.moveToCenter();
```

<br/>

### moveX( x )

윈도우의 x좌표를 변경하여 이동시킨다.

* **Parameters**: 
	* **`x`** {String or Number} 이동할 x 좌표 ex)10, '10px', '10%'

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay', this.getContainer(), 500, 500);
wnd.moveX(10);
```

<br/>

### moveY( y )

윈도우의 y좌표를 변경하여 이동시킨다.

* **Parameters**: 
	* **`y`** {String or Number} 이동할 y 좌표 ex)10, '10px', '10%'

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay', this.getContainer(), 500, 500);
wnd.moveY(10);
```

<br/>

### offset( x, y )

윈도우의 현재 위치에서 매개변수 x, y 값 만큼 더 이동시킨다.

* **Parameters**: 
	* **`x`** {Number} 이동할 x 거리 (px단위)
	* **`y`** {Number} 이동할 y 거리 (px단위)

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay', this.getContainer(), 500, 500);
wnd.offset(10, 10);
```

<br/>

### open( viewUrl, parent, left, top, width, height )

윈도우를 오픈한다.

* **Parameters**: 
	* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
	* **`parent`** {AContainer} 윈도우를 open 한 주체, onWindowResult 콜백을 받을 객체
	* **`left`** {String or Number} 윈도우의 x 좌표 ex) 10, '10px', '5%'
	* **`top`** {String or Number} 윈도우의 y 좌표 ex) 100, '100px', '10%'
	* **`width`** {String or Number} 윈도우의 넓이 ex) 600, '600px', '70%'
	* **`height`** {String or Number} 윈도우의 높이 ex) 800, '800px', '90%'

* **Usage**: 
```js
var wnd = new AWindow('window1');
 wnd.open('Source/t1.lay', this.getContainer(), 10, 10, 500, 500);
```

<br/>

### openAsDialog( viewUrl, parent, width, height )

다이얼로그처럼 작동되도록 옵션을 셋팅하여 윈도우를 오픈한다.<br/>다음의 옵션이 적용된다.<br/>{isModal:true, isCenter:true}

* **Parameters**: 
	* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
	* **`parent`** {AContainer} 윈도우를 open 한 주체, onWindowResult 콜백을 받을 객체
	* **`width`** {String or Number} 윈도우의 넓이 ex) 600, '600px', '70%'
	* **`height`** {String or Number} 윈도우의 높이 ex) 800, '800px', '90%'

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.openAsDialog('Source/t1.lay', this.getContainer(), 500, 500);
```

<br/>

### openAsMenu( viewUrl, parent, width, height )

팝업메뉴와 같은 속성으로 윈도우를 오픈한다.<br/>다음의 옵션이 적용된다.<br/> {isModal:true, isCenter:true, isFocusLostClose:true}

* **Parameters**: 
	* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
	* **`parent`** {AContainer} 윈도우를 open 한 주체 onWindowResult 콜백을 받을 객체
	* **`width`** {String or Number} 윈도우의 넓이 ex) 600, '600px', '70%'
	* **`height`** {String or Number} 윈도우의 높이 ex) 800, '800px', '90%'

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.openAsMenu('Source/t1.lay', this.getContainer(), 500, 500);
```

<br/>

### openCenter( viewUrl, parent, width, height )

윈도우를 화면 가운데 위치하도록 오픈한다.

* **Parameters**: 
	* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
	* **`parent`** {AContainer} 윈도우를 open 한 주체, onWindowResult 콜백을 받을 객체
	* **`width`** {String or Number} 윈도우의 넓이, ex) 600, '600px', '70%'
	* **`height`** {String} 윈도우의 높이, ex) 800, '800px', '90%'

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.openCenter('Source/t1.lay', this.getContainer(), 500, 500);
```

<br/>

### openFull( viewUrl, parent )

윈도우를 화면전체로 오픈한다.

* **Parameters**: 
	* **`viewUrl`** {String} 윈도우에 보여질 뷰 리소스 url
	* **`parent`** {AContainer} 윈도우를 open 한 주체, onWindowResult 콜백을 받을 객체

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.openFull('Source/t1.lay', this.getContainer());
```

<br/>

### preventTouch()

내부적으로 사용되는 함수입니다.<br/><br/>윈도우가 아니 배경에서 터치시 이벤트 전달되어 스크롤되는 버그를 막는 함수입니다.

<br/>

### removeWindow( awnd )

윈도우를 클로즈하면 자동으로 호출된다.<br/>내부에 있는 저장소에서 윈도우를 석재한다.

* **Parameters**: 
	* **`awnd`** {AWindow} 윈도우객체

<br/>

### reportBackKeyEvent()

보여지고 있는 윈도우 중에서 최상단 윈도우에게 backKey 이벤트를 전달한다.<br/>디바이스에서 backKey 가 눌려지면 자동으로 호출된다.

* **Returns**: boolean

<br/>

### reportResizeEvent()

오픈된 윈도우들에게 resize 이벤트를 전달한다.<br/>네이티브 웹뷰의 사이즈가 변경되면 자동으로 호출된다.

<br/>

### setDragOption( key, value )

jQuery draggable를 설정한다.

* **Parameters**: 
	* **`key`** {String} 키
	* **`value`** {String} 값

* **Usage**: 
```js
var w = new AWindow('w1');
w.setDragOption('disabled', true);

//http://api.jqueryui.com/draggable/
```

<br/>

### setModalBgOption( option )

모달창의 백그라운드 색상을 설정한다.

* **Parameters**: 
	* **`option`** {String} light: 투명도를 약하게, dark: 투명도를 진하게, 그 외 설정안함

* **Usage**: 
```js
var w = new AWindow('w1');
w.setModalBgOption('none');
```

<br/>

### setResultCallback( callback )

윈도우 클로즈시 실행할 콜백함수를 선언한다.

* **Parameters**: 
	* **`callback`** {Function} 콜백함수

* **Usage**: 
```js
var w = new AWindow('w1');
w.setResultCallback(function(result) {
    console.log(result);
});
```

<br/>

### setResultListener( resultListener )

close시 결과에 대한 이벤트를 주체가 되는 컨테이너의 onWindowResult 호출할 것인지를 세팅합니다.<br/><br/>윈도우 클로즈시 결과값에 대한 리스너를 설정한다.<br/>해당 리스너의 onWindowResult 함수가 호출된다.

* **Parameters**: 
	* **`resultListener`** {AContainer} 주체가 되는 컨테이너

* **Usage**: 
```js
var wnd  = new AWindow('window1');
wnd.setResultListener(this);

//리스너
function main:onWindowResult(result, data, thisObj) {
//결과 처리
};
```

<br/>

### setWindowOption( option )

윈도우 옵션을 설정한다.

* **Parameters**: 
	* **`option`** {Object} 윈도우 옵션

* **Usage**: 
```js
var w = new AWindow('w1');
w.setWindowOption({
    isModal: true, //모달 윈도우여부
    isAutoCenter: false, //자동 중앙정렬 여부
    isFocusLostClose: false, //모달인 경우 포커스를 잃을 때 창을 닫을지 여부
    isFocusLostHide: false, //모달인 경우 포커스를 잃을 때 창을 숨길지 여부
    modalBgOption: 'dark', //none, light, dark 모달인 경우 배경을 어둡기 정도
    overflow: 'hidden', //hidden, auto, visible, scroll
});
```

<br/>

### show( delay )

윈도우를 오픈한 후 hide 메서드로 숨겨진 윈도우를 다시 표시한다.<br/>매개변수 dalay 값이 있다면 그만큼 지연시킨후 표시한다.

* **Parameters**: 
	* **`delay`** {String} 지연값

* **Usage**: 
```js
var wnd = new AWindow('window1');
wnd.hide();
wnd.show();
//2초후 show
// wnd.show(2000);
```

<br/>

### updateTopWindow()

최상위 윈도우 객체 정보를 변경합니다.

<br/>

### windowTouchBugFix( isOpen )

내부적으로 사용되는 함수입니다.<br/>자신을 띄운 하위 컨테이너에게 터치 정보가 전달되는 것을 막습니다.

* **Parameters**: 
	* **`isOpen`** {Boolean} 윈도우가 오픈되어 있는지 여부

<br/>

### windowTouchManage()

윈도우를 터치했을 시 최상위 윈도우로 변경한다.

<br/>
<br/>
## Events


### onClose()

close 호출시 윈도우가 닫히기 전에 호출된다. false 를 리턴하면 윈도우창이 닫히지 않는다.

<br/>

