# AWebView
> **Extends**: `AComponent`

웹뷰 컴포넌트

<br/>

## Methods

### applyScale()

웹뷰의 scale 을 적용한다.

<br/>

### clear()

웹뷰의 내용을 모두 지우고 빈페이지로 만든다.

* **Usage**: 
```js
this.webview.clear();
```

<br/>

### docLoad()

iframe의 contentDocument를 delegator의 onDocLoad 함수를 호출하여 반환합니다.

<br/>

### docReady()

iframe의 contentDocument을 delegator onDocReady 함수를 호출하여 반환합니다.

<br/>

### enableScrlManager()

ScrollManager 의 자체 스크롤이 적용되도록 한다.

* **Usage**: 
```js
this.webview.enableScrlManager();
```

<br/>

### enableZoom( enable )

웹뷰의 확대,축소 기능의 활성여부를 지정한다.

* **Parameters**: 
	* **`enable`** {Boolean} 활성여부

<br/>

### getDoc()

웹뷰의 contentDocument 를 반환한다.

* **Returns**: Document

* **Usage**: 
```js
var c = this.webview.getDoc();
```

<br/>

### getScrollEle()

웹뷰의 contentDocument에서 body 요소를 반환한다.

* **Returns**: Object

* **Usage**: 
```js
var b = this.webview.getScrollEle();
```

<br/>

### getUrl()

웹뷰 현재 페이지의 경로를 얻어온다.

* **Returns**: String

* **Usage**: 
```js
var u = this.webview.getUrl();
```

<br/>

### getWnd()

웹뷰의 contentWindow 를 반환한다.

* **Returns**: contentWindow

* **Usage**: 
```js
var w = this.webview.getWnd();
```

<br/>

### readyCheck()

iframe의 문서를 실행하기 전 체크를 수행한다.

<br/>

### reload()

웹뷰를 리로드 한다.

* **Usage**: 
```js
this.webview.reload();
```

<br/>

### resetZoom()

줌 설정을 초기화한다.

* **Usage**: 
```js
this.webview.resetZoom();
```

<br/>

### scrollBugFix()

기기의 브라우저별로 문서로드가 완료된 후 바로 스크롤 안되는 경우 호출해준다.

<br/>

### scrollImplement()

자체적으로 스크롤 구현합니다.<br/>touchStart, touchMove, touchUp 이벤트가 동작합니다.

<br/>

### scrollOffset( offset )

문서의 y좌표값에서 매개변수 offset값만큼 더한 위치로 문서를 스크롤한다.

* **Parameters**: 
	* **`offset`** {Number} 더해지는 값

* **Usage**: 
```js
this.webview.scrollOffset(50);
```

<br/>

### scrollTo( pos )

매개변수 pos값 위치로 문서를 스크롤한다.

* **Parameters**: 
	* **`pos`** {Number} y좌표값

* **Usage**: 
```js
this.webview.scrollTo(50);
```

<br/>

### scrollToBottom()

문서의 최하단으로 스크롤한다.

* **Usage**: 
```js
this.webview.scrollToBottom();
```

<br/>

### scrollToCenter()

문서의 가운데로 스크롤한다.

* **Usage**: 
```js
this.webview.scrollToCenter();
```

<br/>

### scrollToTop()

문서의 최상단으로 스크롤한다.

* **Usage**: 
```js
this.webview.scrollToTop();
```

<br/>

### setDelegator( delegator )

delegate 함수를 호출할 객체를 셋팅한다. <br/># delegate functions # <br/>function onDocReady(awebview, contentDocument); <br/>function onDocLoad(awebview, contentDocument);

* **Parameters**: 
	* **`delegator`** {Object} .

<br/>

### setHtml( html )

웹뷰 document에 매개변수 html 을 지정한다.

* **Parameters**: 
	* **`html`** {String} 웹뷰에 표시할 html 태그

* **Usage**: 
```js
this.webview.setHtml('&lt;span&gt;테스트&lt;/span&gt;');
```

<br/>

### setParent( parent )

내부적으로 사용하는 함수로 직접 호출하지 말것! 실제로 컴포넌트의 부모를 바꾸려면 parentObj.addComponent 를 사용해야 합니다. addComponent 만 호출하면 이전 부모에서 삭제하지 않아도 자동으로 새로운 부모로 이동합니다.

* **Parameters**: 
	* **`parent`** {AView} .

<br/>

### setScale( scale )

웹뷰의 스케일(확대,축소) 값을 셋팅한다. 기본은 1.0 이며 두배로 확대하려면 2.0을 셋팅한다.<br/>스케일의 최소값은 1.0, 최대값은 3.0이다. 범위를 넘어가는 경우 최소/최대값을 설정된다.

* **Parameters**: 
	* **`scale`** {Float} 확대 / 축소 배율

* **Usage**: 
```js
this.webview.setScale(2.0);
```

<br/>

### setUrl( url )

웹뷰에 매개변수 url 경로의 문서를 로드한다.

* **Parameters**: 
	* **`url`** {String} 문서 경로

* **Usage**: 
```js
this.webview.setUrl('Source/test.lay');
```

<br/>

### zoom( ratio )

현재의 스케일에서 매개변수 ratio 의 비율만큼 확대,축소한다. 

* **Parameters**: 
	* **`ratio`** {Float} 확대 / 축소 비율

* **Usage**: 
```js
this.webview.zoom(0.1) // 현재 배율에서 10% 확대
this.webview.zoom(-0.1) // 현재 배율에서 10% 축소
```

<br/>
<br/>
## Events


### docLoad()

html 문서의 로드가 완료되면 호출된다. delegator 의 onDocLoad 함수를 호출한다.

### docReady()

html 문서의 조작이 가능해지면 호출된다. 문서의 로드가 완료된 것은 아니다. delegator 의 onDocReady 함수를 호출한다.

### onDocLoad()

html 문서가 로드되면 delegator 로 위임받은 객체가 있을경우 호출된다.

### onDocReady()

html 문서가 조작이 가능해지면 delegator 로 위임받은 객체가 있을경우 호출된다.

<br/>

