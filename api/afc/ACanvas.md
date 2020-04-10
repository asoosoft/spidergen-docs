# ACanvas
> **Extends**: `AComponent`

캔버스 컴포넌트

<br/>

## Properties

### ctx

Canvas Context

* **Type**: `Object`
* **Default**: `null`

<br/>

### data



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다. <br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {String} context 에 매핑된 이벤트 수신자

* **Usage**: 
```js
var canvas = new ACanvas();
canvas.init();
```

<br/>

### resizeCanvas()

cavas의 사이즈를 재조정한다. updatePosition함수가 호출 될 때 호출된다.

<br/>

### setData( data )

데이터를 세팅한다.

* **Parameters**: 
	* **`data`** {String} 데이터

* **Usage**: 
```js
var data = 'abc';
canvas.setData(data);
```

<br/>

### updatePosition( pWidth, pHeight )

캠버스의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. <br/>브라우저의 사이즈가 변경될 경우 자동으로 호출된다.

* **Parameters**: 
	* **`pWidth`** {String} 부모의 너비 = Canvas의 넓이
	* **`pHeight`** {String} 부모의 높이 = Canvas의  높이

<br/>
<br/>
