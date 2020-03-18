# ARadioButton
> **Extends**: `AComponent`

라디오버튼

<br/>

## Properties


### isSelected

라디오버튼의 선택여부이다.

* **Type**: `Boolean`
* **Default**: `null`

<br/>

### selectClass

라디오버튼의 선택시 추가할 클래스명이다.

* **Type**: `String`
* **Default**: `null`

<br/>

### isTabable


* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### getCheckAlign()

라디오버튼의 방향을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var a = this.radio1.getCheckAlign();
```

<br/>

### getSelect()

선택여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var r = this.radio1.getSelect();
```

<br/>

### getText()

라디오버튼의 라벨텍스트를 반환한다.

* **Returns**: String

* **Usage**: 
```js
var t = this.radio1.getText();
```

<br/>

### getValue()

라디오버튼의 값을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var v = this.radio1.getValue();
```

<br/>

### setCheckAlign( align )

라디오버튼의 방향을 설정한다.

* **Parameters**: 
	* **`align`** {String} left : 왼쪽, right : 오른쪽

* **Usage**: 
```js
this.radio1.setCheckAlign('left');
```

<br/>

### setSelect( isSelect )

선택여부를 설정한다.

* **Parameters**: 
	* **`isSelect`** {Boolean} 선택여부

* **Usage**: 
```js
this.radio1.setSelect(true);
```

<br/>

### setText( text )

라디오버튼의 라벨을 설정한다.

* **Parameters**: 
	* **`text`** {String} 텍스트

* **Usage**: 
```js
this.radio1.setText('라디오버튼라벨');
```

<br/>

### setValue( value )

라디오버튼의 값을 설정한다.

* **Parameters**: 
	* **`value`** {String} 값

* **Usage**: 
```js
this.radio1.setValue('thisRadioValue');
```

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

### setSelectStyle()



* **Parameters**: 

* **Usage**: 
```js

```

### setData()



* **Parameters**: 

* **Usage**: 
```js

```

### getQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

### setQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

### _getDataStyleObj()



* **Parameters**: 

* **Usage**: 
```js

```

### _setDataStyleObj()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>

## Events


### click( comp, info, e )

라디오버튼을 클릭할때 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

<br/>

