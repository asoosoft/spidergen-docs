# ASwitchButton
> **Extends**: `AComponent`

스위치버튼

<br/>

## Properties


### backOffStyle

바탕Off스타일

* **Type**: `String`
* **Default**: `'switch-back-off'`

<br/>

### backOnStyle

바탕On스타일

* **Type**: `String`
* **Default**: `'switch-back-on'`

<br/>

### barOffStyle

바Off스타일

* **Type**: `String`
* **Default**: `'switch-bar-off'`

<br/>

### barOnStyle

바On스타일

* **Type**: `String`
* **Default**: `'switch-bar-on'`

<br/>
<br/>

## Methods

### getValue()

컴포넌트의 값을 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var s = this.switch.getValue();
```

<br/>

### setSwitchOffStyle( backOffStyle )

스위치버튼의 off 상태 스타일을 설정한다.

* **Parameters**: 
	* **`backOffStyle`** {String} 스타일명

* **Usage**: 
```js
this.switch.setSwitchOffStyle('offStyle');
```

<br/>

### setSwitchOnStyle( backOnStyle )

스위치버튼의 on 상태 스타일을 설정한다.

* **Parameters**: 
	* **`backOnStyle`** {String} 스타일명

* **Usage**: 
```js
this.switch.setSwitchOnStyle('onStyle');
```

<br/>

### setSwitchStyle( backOnStyle, backOffStyle )

스위치버튼의 on / off 시 스타일 설정한다. 바의 스타일은 css에서 다음과 같은 방식으로 선언한다.

* **Parameters**: 
	* **`backOnStyle`** {String} 바탕On스타일
	* **`backOffStyle`** {String} 바탕Off스타일

* **Usage**: 
```js
this.switch.setSwitchStyle('onClass', 'offClass');
//css 스타일 정의
.switch-on.onClass span{ 스타일정의 }
```

<br/>

### setValue( isOn )

컴포넌트의 on / off 값을 설정한다.

* **Parameters**: 
	* **`isOn`** {Boolean} On/Off여부

* **Usage**: 
```js
this.switch.setValue(true);
```

<br/>
<br/>
