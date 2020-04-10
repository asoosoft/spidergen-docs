# AFloat
> **Extends**: `없음`

AFloat

<br/>

## Properties

### $frame



* **Type**: ``
* **Default**: ``

<br/>


### $bg



* **Type**: ``
* **Default**: ``



### isBgCheck



* **Type**: ``
* **Default**: ``



### isFocusLostClose



* **Type**: ``
* **Default**: ``



### zIndex



* **Type**: ``
* **Default**: ``



### closeCallback



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### append( ele )

파라미터로 넘어온 ele값을 $frame에 append한다.

* **Parameters**: 
	* **`ele`** {String} 엘리먼트 jquery 요소

* **Usage**: 
```js
var ele = 'element요소';
float.append(ele);
```

<br/>

### checkBg()

오픈된 윈도우의 한단계 밑(body 전체를 덮고 있는 div요소) 요소.<br/><br/>액션 이벤트가 발생 close 함수를 호출한다.

<br/>

### close()

프래임을 닫습니다. 팝업 함수를 호출할때 등록한 콜백함수가 있다면 닫은 다음에 호출한다.

* **Usage**: 
```js
float.close();
```

<br/>

### enableBgCheck( enable )

bgCheck Fuction 사용유무를 세팅한다.

* **Parameters**: 
	* **`enable`** {Boolean} true | false

* **Usage**: 
```js
float.enableBgCheck(true);
```

<br/>

### init()

float객체를 초기화 합니다. 프레임을 div태그로 세팅합니다.

* **Usage**: 
```js
var float= new AFloat();
float.init();
```

<br/>

### popup( left, top, width, height, closeCallback )

레이어형태(div 요소)인 프래임을 띄울 정보를 가공한 뒤 popupEx함수를 호출합니다.

* **Parameters**: 
	* **`left`** {String} 좌측 position
	* **`top`** {String} 상단 position
	* **`width`** {String} 가로크기
	* **`height`** {String} 세로크기
	* **`closeCallback`** {Function} 콜백함수(close함수가 호출될떄 콜백함수가 호출된다.)

* **Usage**: 
```js
float.popup(0,0,'200px','200px');
```

<br/>

### popupEx( info, closeCallback )

세팅된 프래임을 활성화한다.

* **Parameters**: 
	* **`info`** {Object} left, top, width, height 정보
	* **`closeCallback`** {Function} 콜백함수 (close함수가 호출될떄 콜백함수가 호출된다.)

* **Usage**: 
```js
float.popupEx({ 'left': 0, 'top': 0, 'width': '200px', 'height': '200px' }, callbackFunction);
```

<br/>
<br/>
