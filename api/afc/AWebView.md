# AWebView
> **Extends**: `AComponent`

웹뷰 컴포넌트는 컴포넌트 영역에 다른 웹 문서를 넣을 수 있다.

<br/>

## Properties

### iframe \<HTMLElement>

웹뷰를 구성하고있는 iframe 태그

<br/>

### maxScale

웹뷰의 scale 최대값

<br/>

### minScale 

웹뷰의 scale 최소값

<br/>

## Methods

### clear()

웹뷰의 내용을 모두 지우고 빈페이지로 만든다.

<br/>

### enableZoom( enable )

웹뷰의 확대,축소 기능의 활성여부를 지정한다.

- `enable` \<Boolean> 활성여부

<br/>

### getDoc()

웹뷰의 contentDocument 를 반환한다.

- **Returns** \<Document>

<br/>

### getScrollEle()

웹뷰의 contentDocument에서 body 요소를 반환한다.

- **Returns** \<HTMLElement>
  
<br/>

### getUrl()

웹뷰의 현재 페이지 경로를 얻어온다.

- **Returns** \<String>

<br/>

### getWnd()

웹뷰의 contentWindow 를 반환한다.

- **Returns** \<contentWindow>

<br/>

### reload()

웹뷰를 리로드 한다.

<br/>

### scrollOffset( offset )

문서의 y좌표값에서 매개변수 offset값만큼 더한 위치로 문서를 스크롤한다.

- `offset` \<Number> 더해지는 값

```js
this.webview.scrollOffset(50);
```

<br/>

### scrollTo( pos )

매개변수 pos값 위치로 문서를 스크롤한다.

- `pos` \<Number> y좌표값

```js
this.webview.scrollTo(50);
```

<br/>

### scrollToBottom()

문서의 최하단으로 스크롤한다.

<br/>

### scrollToCenter()

문서의 가운데로 스크롤한다.

<br/>

### scrollToTop()

문서의 최상단으로 스크롤한다.

<br/>

### setDelegator( delegator )

delegate 함수를 호출할 객체를 컴포넌트에 세팅한다. 

- `delegator` \<Object>
```js
class MainView()
{
	super();

	//TODO:edit here

}
extends AView;

function MainView*init(context, evtListener)
{
	super.init(context, evtListener);
	
	//아래의 두가지 리스너를 사용하려면
	//url을 세팅하기전에  delegator 지정해야한다.
	this.webView1.setDelegator(this);
	this.webView1.setUrl('sample/index.html');
	
};

//delegator를 세팅하면 아래의 두가지 리스너를 통해 결과를 전달 받을수있다.
//document가 준비되면 호출된다.
function MainView*onDocReady(comp, doc)
{
	...
};

//웹뷰 iframe의 src 로드가 완료되면 호출된다.
function MainView*onDocLoad(comp, doc)
{
	...
};
```

<br/>

### setHtml( html )

웹뷰 document에 매개변수 html 을 지정한다.

- `html` \<String> html 형식의 태그
```js
this.webview.setHtml('<span>샘플</span>');
```

<br/>

<br/>

### setUrl( url )

웹뷰에 매개변수 url 경로의 문서를 로드한다.

- `url` \<String> 문서 경로

```js
this.webview.setUrl('Source/test.lay');
```

<br/>

### zoom( ratio )

현재의 스케일에서 매개변수 ratio 의 비율만큼 확대,축소한다. 

- `ratio` \<Float> 확대 / 축소 비율

```js
this.webview.zoom(0.1) // 현재 배율에서 10% 확대
this.webview.zoom(-0.1) // 현재 배율에서 10% 축소
```

<br/>

### setScale()

웹뷰영역의 스케일을 지정한다. 

<br/>

## Events

### onDocLoad()

html 문서가 로드되면 delegator로 위임받은 객체가 있을경우 호출된다.
[참조](#-setDelegator(-delegator-)) 

<br/>

### onDocReady()

html 문서가 조작이 가능해지면 delegator 로 위임받은 객체가 있을경우 호출된다. [참조](#-setDelegator(-delegator-)) 

<br/>

