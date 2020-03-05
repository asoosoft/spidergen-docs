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
<br/>
