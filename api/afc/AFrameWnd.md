# AFrameWnd
**Extends** `AWindow`

AFrameWnd

<br/>

## Properties


### title \<>

<br/>


### oldInfo \<>

<br/>


### titleLbl \<>

<br/>


### titleHeight \<Number>

<br/>


### statusHeight \<Number>

<br/>


### statusBar \<>

<br/>


### calcHeight \<Number>

<br/>


### icon \<>

<br/>
<br/>

## Instance Methods

### getTitleText()

프레임윈도우의 타이틀 텍스트를 리턴한다.

- **Returns** \<String>

```js
var result = frameWnd.getTitleText();
```

<br/>

### init( context )

AFrameWnd의 초기화 작업을 한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보

```js
var frameWnd = new AFrameWnd();
frameWnd.init();
```

<br/>

### makeTitle()

타이틀 영역 생성합니다.

<br/>

### onMaxBtnClick( acomp, info )

프래임을 최대화 한다.

- `acomp` <AButton> 컴포넌트 객체
- `info` <Object> lisener의 이벤트 함수에 두번째 파라미터로 전달되는 값.

<br/>

### onMinBtnClick( acomp, info )

프래임을 최소화한다.

- `acomp` <String> 컴포넌트 객체
- `info` <String> lisener의 이벤트 함수에 두번째 파라미터로 전달되는 값.

<br/>

### setTitleHtml( str )

타이틀의 html을 세팅하는 함수이다.

- `str` \<String> HTML Tag

```js
var tag = '<html 태그...>';
frameWnd.setTitleHtml(tag);
```

<br/>

### setTitleText( str )

프레임윈도우의 타이틀 텍스트를 세팅한다.

- `str` \<String> 타이틀명

```js
frameWnd.setTitleText('타이틀');
```

<br/>

### onCreate()

```js

```

<br/>


### showTitle()

```js

```

<br/>


### hideTitle()

```js

```

<br/>


### makeStatusBar()

```js

```

<br/>


### setStatusInfo( info )

- `info` \<String>

```js

```

<br/>


### restore()

```js

```

<br/>


### minimize()

```js

```

<br/>


### maximize()


```js

```

<br/>


### onCloseBtnClick( acomp, info )

- `acomp` \<>
- `info` \<>

```js

```

<br/>


### setIconMap( iconMap )

- `iconMap` \<>

```js

```

<br/>


### setIcon( icon )

- `icon` \<>

```js

```

<br/>


### changeIcon( icon )

- `icon` \<>

```js

```

<br/>
<br/>
