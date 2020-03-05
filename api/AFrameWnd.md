# AFrameWnd
> **Extends**: `AWindow`

AFrameWnd

<br/>

## Methods

### getTitleText()

프레임윈도우의 타이틀 텍스트를 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = frameWnd.getTitleText();
```

<br/>

### init( context )

AFrameWnd의 초기화 작업을 한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보

* **Usage**: 
```js
var frameWnd = new AFrameWnd();
frameWnd.init();
```

<br/>

### makeTitle()

타이틀 영역 생성합니다.

<br/>

### makeViewItem()

makeViewItem

<br/>

### onCloseBtnClick( acomp, info )

프래임을 닫습니다.

* **Parameters**: 
	* **`acomp`** {AButton} 컴포넌트 객체
	* **`info`** {Object} 리스너의 이벤트함수에서 전달되는 값

<br/>

### onMaxBtnClick( acomp, info )

프래임을 최대화 한다.

* **Parameters**: 
	* **`acomp`** {AButton} 컴포넌트 객체
	* **`info`** {Object} lisener의 이벤트 함수에 두번째 파라미터로 전달되는 값.

<br/>

### onMinBtnClick( acomp, info )

프래임을 최소화한다.

* **Parameters**: 
	* **`acomp`** {String} 컴포넌트 객체
	* **`info`** {String} lisener의 이벤트 함수에 두번째 파라미터로 전달되는 값.

<br/>

### setTitleHtml( str )

타이틀의 html을 세팅하는 함수이다.

* **Parameters**: 
	* **`str`** {String} HTML Tag

* **Usage**: 
```js
var tag = '<html 태그...>';
frameWnd.setTitleHtml(tag);
```

<br/>

### setTitleText( str )

프레임윈도우의 타이틀 텍스트를 세팅한다.

* **Parameters**: 
	* **`str`** {String} 타이틀명

* **Usage**: 
```js
frameWnd.setTitleText('타이틀');
```

<br/>
<br/>
