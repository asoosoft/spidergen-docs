# ATextBox
> **Extends**: `AComponent`

텍스트박스 컴포넌트

<br/>

## Methods

### getHtml()

텍스트박스안의 내용을 html 태그를 포함해서 반환한다.<br/>ex) var h = this.textbox.getHtml();

* **Returns**: String

<br/>

### getText()

텍스트박스안의 내용을 텍스트형식으로 반환한다.<br/>ex) var t = this.textbox.getText();

* **Returns**: String

<br/>

### setHtml( strHtml )

html 형식의 매개변수 strHtml 값을 텍스트박스안 요소로 지정한다.<br/>ex) this.textbox.setHtml(strHtml);

* **Parameters**: 
	* **`strHtml`** {String} 텍스트

<br/>

### setText( text )

매개변수 text 값을 텍스트박스안 요소로 지정한다.<br/>ex) this.textbox.setText('text');

* **Parameters**: 
	* **`text`** {String} 문자열

<br/>

### setTextAlign( align )

텍스트박스의 텍스트 정렬방식을 설정한다.<br/>정렬방향) 왼쪽 : flex-start<br/>    가운데 : center<br/>    오른쪽 : flex-end<br/>ex) this.textbox.setTextAlign('flex-start');

* **Parameters**: 
	* **`align`** {String} 정렬방향

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
* **Text:** 멀티라인 텍스트를 설정하는 속성입니다. <br> 태그를 이용해서 개행을 할 수 있습니다. 
* **H-Align:** 좌우 정렬을 설정하는 속성입니다. 
> * **left:** 텍스트를 좌측으로 정렬하는 속성입니다. 
> * **center:** 텍스트를 중앙으로 정렬하는 속성입니다.  
> * **right:** 텍스트를 우측으로 정렬하는 속성입니다. 
* **V-Align** : 상하 정렬을 설정하는 속성입니다.
> * **top:** 텍스트를 상단으로 정렬하는 속성입니다.
> * **center:** 텍스트를 중앙으로 정렬하는 속성입니다.
> * **bottom:** 텍스트를 하단으로 정렬하는 속성입니다.
