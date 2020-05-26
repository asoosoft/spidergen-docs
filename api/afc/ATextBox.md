# ATextBox
**Extends**: [`AComponent`](AComponent.html#AComponent)

텍스트 박스

<br/>

## Instance Methods

### getHtml()

텍스트박스 안의 내용을 html 태그를 포함하여 반환한다.

* **Returns** \<String>

<br/>

### getText()

텍스트박스 안의 내용을 텍스트 형식으로 반환한다.

* **Returns** \<String>

<br/>

### setHtml( strHtml )

html 형식의 매개변수 strHtml 값을 텍스트 박스 안의 요소로 지정한다.

* `strHtml` \<String> html 형식의 텍스트

<br/>

### setText( text )

매개변수 text 값을 텍스트 박스 안의 요소로 지정한다.

* `text` \<String> 문자열

```js
this.textbox.setText('text');
```

<br/>

### setTextAlign( align )

텍스트 정렬방식을 설정한다.

- `align` \<String> 정렬방향
	* 왼쪽 : flex-start
	* 가운데 : center
	* 오른쪽 : flex-end

```js
this.textbox.setTextAlign('flex-start');
```

<br/>
<br/>

## Attribute

### Data

* `Text` 멀티라인 텍스트를 설정하는 속성입니다.
* `H-Align` 좌우 정렬을 설정하는 속성입니다. 
    * `left` 텍스트를 좌측으로 정렬하는 속성입니다. 
    * `center` 텍스트를 중앙으로 정렬하는 속성입니다.  
    * `right` 텍스트를 우측으로 정렬하는 속성입니다. 

* `V-Align` 상하 정렬을 설정하는 속성입니다.
    * `top` 텍스트를 상단으로 정렬하는 속성입니다.
    * `center` 텍스트를 중앙으로 정렬하는 속성입니다.
    * `bottom` 텍스트를 하단으로 정렬하는 속성입니다.

