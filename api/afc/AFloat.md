# AFloat
**Extends**:

화면 위에 새로띄워지는 플로팅 객체

<br/>
<br/>

## Class Variables

<br/>
<br/>

## Instance Variables

### isBgCheck \<Boolean>

플로팅 시 화면을 덮는 백그라운드를 만들지 여부

<br/>

### isFocusLostClose \<Boolean>

포커스를 잃을 시 (백그라운드 터치 시) 닫힐지 여부

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### append( ele )

파라미터로 넘어온 ele값을 $frame에 추가한다.

- `ele` \<String> 엘리먼트 jquery 요소
 
```js
var ele = 'element요소';
float.append(ele);
```

<br/>

### close( result )

프래임을 닫는다. 팝업 함수를 호출할때 등록한 콜백함수가 있다면 닫은 다음에 호출한다.

- `result` \<Any> 콜백함수에 전달 할 결과값

<br/>

### enableBgCheck( enable )

플로팅 시 화면을 덮는 백그라운드를 만들지 여부를 세팅한다

- `enable` <Boolean> 백그라운드 생성 여부

<br/>

### init()

float객체를 초기화 한다. 프레임을 div태그로 세팅한다.

```js
var float= new AFloat();
float.init();
```

<br/>

### popup( left, top, width, height, closeCallback )

append 하거나 세팅한 객체를 화면에  띄운다

- `left` <String> 좌측 position
- `top` <String> 상단 position
- `width` <String> 가로크기
- `height` <String> 세로크기
- `closeCallback` <Function> 콜백함수(close함수가 호출될떄 콜백함수가 호출된다.)

```js
float.popup(0,0,'200px','200px');
```

<br/>

### popupEx( info, closeCallback )

append 하거나 세팅한 객체를 화면에  띄운다

- `info` <Object> left, top, width, height 정보
- `closeCallback` <Function> 콜백함수 (close함수가 호출될떄 콜백함수가 호출된다.)

```js
float.popupEx({ 'left': 0, 'top': 0, 'width': '200px', 'height': '200px' }, callbackFunction);
```

<br/>
<br/>
