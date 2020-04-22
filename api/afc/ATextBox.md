# ATextBox
> **Extends**: `AComponent`

텍스트박스 컴포넌트

<br/>

## Instance Methods

### getHtml()

텍스트박스 안의 내용을 html 태그를 포함하여 반환한다.

* **Returns** \<String>

```js
var h = this.textbox.getHtml();
```

<br/>

### getText()

텍스트박스 안의 내용을 텍스트 형식으로 반환한다.

* **Returns** \<String>

```js
var t = this.textbox.getText();
```

<br/>

### setHtml( strHtml )

html 형식의 매개변수 strHtml 값을 텍스트박스 안의 요소로 지정한다.

* `strHtml` \<String> 텍스트
	
```js
this.textbox.setHtml(strHtml);
```

<br/>

### setText( text )

매개변수 text 값을 텍스트박스 안의 요소로 지정한다.

* `text` \<String> 문자열

```js
this.textbox.setText('text');
```

<br/>

### setTextAlign( align )

텍스트 정렬방식을 설정한다.

* `align` \<String> 정렬방향
	* 왼쪽 : flex-start
	* 가운데 : center
	* 오른쪽 : flex-end

```js
this.textbox.setTextAlign('flex-start');
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화할 때 호출한다.
동적으로 객체를 생성할 경우, 파라미터를 생략하고 호출한다.

* `context` \<String> 컴포넌트 생성 및 초기화 정보
* `evtListener` \<String> context에 매핑된 이벤트 수신자

```js
var textbox = new ATextBox();
textbox.init();
```

<br/>

### setData( data )
새로운 데이터를 지정한다.

```js
this.textbox.setData('hello world');
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr의 정보에 따라 dataArr에 채운다.
dataArr은 AQueryData 특정부분의 참조자다.

자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* `dataArr` \<Array> \[ {key1:value, key2:value ...}, {}, ... ]
* `keyArr` \<Array> \[ key1, key3, key10 ]
* `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr의 정보를 참조하여 컴포넌트에 세팅한다.
dataArr은 AQueryData 특정부분의 참조자이다.

자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* `dataArr` \<Array> \[ {key1:value, key2:value ...}, {}, ... ]
* `keyArr` \<Array> \[ key1, key3, key10 ]
* `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>
<br/>

## Attribute

### Data
* **Text:** 멀티라인 텍스트를 설정하는 속성입니다.
* **H-Align:** 좌우 정렬을 설정하는 속성입니다. 
    * **left:** 텍스트를 좌측으로 정렬하는 속성입니다. 
    * **center:** 텍스트를 중앙으로 정렬하는 속성입니다.  
    * **right:** 텍스트를 우측으로 정렬하는 속성입니다. 

* **V-Align** : 상하 정렬을 설정하는 속성입니다.
    * **top:** 텍스트를 상단으로 정렬하는 속성입니다.
    * **center:** 텍스트를 중앙으로 정렬하는 속성입니다.
    * **bottom:** 텍스트를 하단으로 정렬하는 속성입니다.

