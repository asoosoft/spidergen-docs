# ATextArea
> **Extends**: `AComponent`

텍스트영역

<br/>

## Methods

### appendText( text )

매개변수 text의 값을 컴포넌트에 있는 값에 추가한다.

* **Parameters**: 
	* **`text`** {String} 텍스트

* **Usage**: 
```js
this.textarea.appendText('추가할 텍스트');
```

<br/>

### enable( isEnable )

컴포넌트의 활성상태를 설정한다.

* **Parameters**: 
	* **`isEnable`** {Boolean} 상태값

* **Usage**: 
```js
this.textarea.enable(false);
```

<br/>

### enableTimerChange( enable )

텍스트 변경을 체크하는 타이머 실행여부를 설정한다.

* **Parameters**: 
	* **`enable`** {Boolean} 실행여부

* **Usage**: 
```js
this.textarea.enableTimerChange(false);
```

<br/>

### getPadding()

컴포넌트에 설정된 패딩값을 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var p = this.textarea.getPadding();
```

<br/>

### getPlaceHolder()

컴포넌트에 설정된 플레이스 홀더 텍스트를 반환한다.

* **Returns**: String

* **Usage**: 
```js
var p = this.textarea.getPlaceHolder();
```

<br/>

### getText()

컴포넌트에 설정된 값을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var t = this.textarea.getText();
```

<br/>

### getTextAlign()

컴포넌트에 설정된 정렬방향을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var a = this.textarea.getTextAlign();
```

<br/>

### isScroll()

컴포넌트 스크롤 가능여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.textarea.isScroll();
```

<br/>

### setPadding( padding )

매개변수 padding값을 컴포넌트의 패딩값으로 설정한다.

* **Parameters**: 
	* **`padding`** {Number} 패딩값

* **Usage**: 
```js
this.textarea.setPadding(20);
```

<br/>

### setPlaceHolder( placeholder )

매개변수 placeholder 값을 컴포넌트의 플레이스홀더로 설정한다.

* **Parameters**: 
	* **`placeholder`** {String} 표시할 텍스트

* **Usage**: 
```js
this.textarea.setPlaceHolder('플레이스홀더');
```

<br/>

### setReadOnly( isReadOnly )

컴포넌트의 읽기전용 속성을 설정한다.

* **Parameters**: 
	* **`isReadOnly`** {Boolean} 읽기전용 여부

* **Usage**: 
```js
this.textarea.setReadOnly(true);
```

<br/>

### setText( text )

매개변수 text의 값을 컴포넌트 값으로 설정한다.

* **Parameters**: 
	* **`text`** {String} 텍스트

* **Usage**: 
```js
this.textarea.setText('텍스트');
```

<br/>

### setTextAlign( align )

매개변수 align 의 값으로 컴포넌트의 정렬방향을 설정한다.

* **Parameters**: 
	* **`align`** {String} 정렬방향 (left/right/center)

* **Usage**: 
```js
this.textarea.setTextAlign('center');
```

<br/>
<br/>
## Events


### blur( comp, e )

컴포넌트에서 포커스가 사라지면 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`e`** {Object} 이벤트 객체

### change( comp, info )

값이 변경되면 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} 값

### focus( comp, e )

포커스시 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`e`** {Object} 이벤트 객체

<br/>

