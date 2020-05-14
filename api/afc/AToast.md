# AToast
**Extends**: [`AFloat`](AFloat.html#AFloat)

토스트 메세지

<br/>

## Properties

### divCss \<Object>

토스트 텍스트를 감싸고 있는 div의 css

<br/>

### isBgCheck \<Boolean>

백그라운드 터치 시 닫을지 여부

<br/>

### spanCss \<Array>

토스트 텍스트의 css

<br/>
<br/>

## Class Methods

### AToast.callback( text, callback, duration )

매개변수 text의 값으로 토스트를 표시한다. 매개변수 duration 값(생략시 기본값 2) 단위 만큼 토스트를 표시한다.<br/>매개변수 duration 값만큼 후에 매개변수 callback 함수를 호출한다.

- `text` \<String> 텍스트
- `callback` \<Function> 콜백함수
- `duration` \<Number> 토스트 표시 지속시간 (단위 : 초)

```js
AToast.callback('텍스트 내용', function()
{
	alert('callback');
}, 2);
```

<br/>

### AToast.show( text, duration )

매개변수 text의 값으로 토스트를 표시한다. 매개변수 duration 값(생략시 기본값 2) 단위 만큼 토스트를 표시한다.

- `text` \<String> 텍스트
- `duration` \<Number> 토스트 표시 지속시간 (단위 : 초)

```js
AToast.show('텍스트 내용', 2);
```

<br/>
<br/>

## Instance Methods

### callback( text, callback, duration )

매개변수 text의 값으로 토스트를 표시한다. 매개변수 duration 값(생략시 기본값 2) 단위 만큼 토스트를 표시한다.<br/>매개변수 duration 값만큼 후에 매개변수 callback 함수를 호출한다.

```js
var toast = new AToast();
toast.callback('텍스트 내용', function()
{
	alert('callback');
}, 2);
```

<br/>

### init()

컴포넌트를 생성하고 초기화 할 때 호출한다.

```js
var toast = new AToast();
toast.init();
```

<br/>

### show( text, duration )

매개변수 text의 값으로 토스트를 표시한다. 매개변수 duration 값(생략시 기본값 2) 단위 만큼 토스트를 표시한다.

- `text` \<String> 텍스트
- `duration` \<Number> 토스트 표시 지속시간 (단위 : 초)

```js
var toast = new AToast();
toast.show('텍스트 내용', 2);
```

<br/>

### single()

호출 시 글로벌 토스트가 생성된다.<br/>프로젝트 내에서 하나의 토스트로 컨트롤 하고 싶을 때 사용한다.

<br/>
<br/>
