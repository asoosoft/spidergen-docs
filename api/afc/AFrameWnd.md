# AFrameWnd( containerId )
**Extends** [`AWindow`](./AWindow.md)

* `containerId` \<String> 컨테이너 아이디

기본 윈도우 기능에 프레임을 추가한 컨테이너. 상단의 타이틀바, 최대, 최소, 닫기 버튼과 하단의 상태바를 가지고 있다.
<br><br>
기본적인 사용법은 [AWindow](./AWindow.md) 와 같다.
```js
var frm = new AFrameWnd('myFrame');

//넓이와 높이를 생략하면 lay 파일의 넓이와 높이로 오픈된다.
frm.open('Source/TestView.lay', null, 100, 100);
```

<br/>

## Class Variables

<br/>

## Instance Variables

### title \<HTMLElement>

상단 표현 엘리먼트 객체

<br/>

### titleLbl \<[ALabel](./ALabel.md)>

상단에 문자열을 표현하는 라벨 컴포넌트 

<br/>

### titleHeight \<Number>

상단 표현 엘리먼트 높이

* `default` `24`

<br/>

### statusHeight \<Number>

하단의 상태 표시 엘리먼트 높이

<br/>

### statusBar \<HTMLElement>

하단의 상태 표시 엘리먼트 객체

<br/>

### calcHeight \<Number>

상단, 하단에 엘리먼트가 표시되는 경우 중간의 내용을 표시하는 엘리먼트의 높이를 지정할 때 사용하는 마이너스 값

<br/>

### icon \<Number>

상단 표시 엘리먼트의 내부 엘리먼트 중 좌측 끝의 아이콘을 표시하기 위한 위치값. 아이콘의 이미지 위치 단위는 16px 이다.

<br/>
<br/>

## Class Methods

<br/>

## Instance Methods

### getTitleText()

프레임윈도우의 상단 표시 문자열을 가져온다.

- **Returns** \<String> 상단 표시 문자열

<br/>

### makeTitle()

상단 표시 영역을 생성한다.

<br/>

### setTitleHtml( str )

상단의 라벨 컴포넌트에 HTML 을 세팅한다.

- `str` \<String> HTML Tag 문자열

```js
var tag = '<font style="color: red;">중요한</font>내용';
frameWnd.setTitleHtml(tag);
```

<br/>

### setTitleText( str )

상단의 라벨에 문자열을 세팅한다.

- `str` \<String> 상단 표현 문자열

<br/>

### showTitle()

상단과 하단 표시 영역을 보여준다.

<br/>

### hideTitle()

상단과 하단 표시 영역을 숨긴다.

<br/>

### makeStatusBar()

하단 표시 영역을 생성한다.

<br/>

### setStatusInfo( html )

하단 상태 영역에 HTML 을 설정한다.

- `html` \<String> HTML Tag 문자열

<br/>

### restore()

윈도우가 최소화나 최대화가 된 경우 다시 이전 사이즈로 변경한다.

<br/>

### minimize()

윈도우를 최소화한다.

<br/>

### maximize()

윈도우를 최대화한다.

<br/>

### setIconMap( iconMap )

상단 표시 엘리먼트의 내부 엘리먼트 중 좌측 끝의 아이콘에 표시할 이미지를 지정한다.

- `iconMap` \<String> 이미지 경로 또는 이미지 CSS

```js
//이미지를 경로 지정하는 방법
framewnd.setIconMap('Assets/img/frmIcon.png');

//이미지를 CSS 로 지정하는 방법
//stl 에 추가할 내용
//.frmwnd_icon1 { background-image: 'url("Assets/img/frmIcon.png")' }
framewnd.setIconMap('frmwnd_icon1');
```

<br/>

### setIcon( icon )

상단 표시 엘리먼트의 내부 엘리먼트 중 좌측 끝의 아이콘을 표시하기 위한 위치값을 지정한다. 아이콘의 이미지 위치 단위는 16px 이다.

- `icon` \<Number> 아이콘 이미지의 위치 [ 0 | 1 | ... ]

```js
framewnd.setIconMap('Assets/img/frmIcon.png');
framewnd.setIcon(5); //좌측에서 5번째(80px)에 위치한 이미지가 표현된다.
```

<br/>

