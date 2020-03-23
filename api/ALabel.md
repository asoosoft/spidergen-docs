# ALabel
> **Extends**: `AComponent`

라벨 컴포넌트

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

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>

## Attribute

### Data
레이블의 텍스트 및 텍스트 정렬을 설정하는 속성입니다. 

* **Text** 레이블의 텍스트를 설정하는 속성입니다.
* **Align** 레이블 텍스트의 정렬을 설정하는 속성입니다.
> * **left** 텍스트를 좌측 정렬합니다. 
> * **center** 텍스트를 가운데 정렬합니다.  
> * **right** 텍스트를 추측 정렬합니다.  
* **Line Breaks** 레이블의 텍스트 줄바꿈 옵션을 설정하는 속성입니다. 
> * **break word** 단어 단위로 줄바꿈을 실행합니다.
> * **break all** 글자 단위로 줄바꿈을 실행합니다. 
* **pre formatted** 설명이 필요합니다. 
