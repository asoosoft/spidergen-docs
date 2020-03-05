# ALabel
> **Extends**: `AComponent`

라벨 컴포넌트

<br/>

## Properties


### maskVal

마스크값

* **Type**: `Number`
* **Default**: `afc.MASK_NONE`

<br/>
<br/>

## Methods

### getText()

라벨의 텍스트를 반환한다.

* **Usage**: 
```js
var result = label.getText();
```

<br/>

### setHtml( html )

라벨에 html태그를 세팅한다.

* **Parameters**: 
	* **`html`** {String} html 태그

* **Usage**: 
```js
var tag = 'html tag....';
label.setHtml(tag);
```

<br/>

### setLineHeight( lineHeight )

텍스트 라인 높이를 셋팅합니다.

* **Parameters**: 
	* **`lineHeight`** {String} 라인 높이

<br/>

### setText( text )

텍스트를 세팅한다.

* **Parameters**: 
	* **`text`** {String} 텍스트

* **Usage**: 
```js
label.setText('텍스트');
```

<br/>

### setTextAlign( align )

텍스트의 text-align 속성을 세팅한다.

* **Parameters**: 
	* **`align`** {String} text-align css value

* **Usage**: 
```js
label.setTextAlign('center');
```

<br/>
<br/>
