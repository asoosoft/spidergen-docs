# AToast
> **Extends**: 

토스트 메세지

<br/>

## Properties


### isBgCheck



* **Type**: ``
* **Default**: ``

<br/>

### curSpan



* **Type**: ``
* **Default**: ``

<br/>

### divCss



* **Type**: ``
* **Default**: ``

<br/>

### spanCss



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods


### AToast.callback( text, callback, duration )

매개변수 text의 값으로 토스트를 표시한다. 매개변수 duration 값(생략시 기본값 2) 단위 만큼 토스트를 표시한다.<br/>매개변수 duration 값만큼 후에 매개변수 callback 함수를 호출한다.<br/>ex1) AToast.callback('텍스트 내용', function() {alert('callback');}, 2);<br/>ex2) var t = new AToast();<br/>t.callback('텍스트 내용', function() {alert('callback');}, 2);

* **Parameters**: 
	* **`text`** {String} 텍스트
	* **`callback`** {Function} 콜백함수
	* **`duration`** {Number} 토스트 표시 지속시간 (단위 : 초)

<br/>

### createSpan( text )

토스트안에 사용될 엘리먼트를 생성한다.<br/>매개변수 text 를 엘리먼트안 요소로 지정한다.

* **Parameters**: 
	* **`text`** {String} 텍스트

* **Usage**: 
```js
var t = new AToast();
t.createSpan('text');
```

<br/>

### AToast.show( text, duration )

매개변수 text의 값으로 토스트를 표시한다. 매개변수 duration 값(생략시 기본값 2) 단위 만큼 토스트를 표시한다.<br/>ex1) AToast.show('텍스트 내용', 2);<br/>ex2) var t = new AToast();<br/>t.show('텍스트 내용', 2);

* **Parameters**: 
	* **`text`** {String} 텍스트
	* **`duration`** {Number} 토스트 표시 지속시간 (단위 : 초)

<br/>

### init()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### show()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### callback()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
