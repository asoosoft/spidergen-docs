# ALabel
**Extends**: [`AComponent`](AComponent.html#AComponent)

라벨 컴포넌트

<br/>

## Instance Methods

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getText()

라벨의 텍스트를 리턴한다.

<br/>

### setHtml( html )

라벨에 html태그를 세팅한다.

- `html` \<String> html 태그

```js
var tag = 'html tag....';
label.setHtml(tag);
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setText( text )

텍스트를 세팅한다.

- `text` \<String> 텍스트

<br/>

### setTextAlign( align )

텍스트의 text-align 속성을 세팅한다.

- `align` \<String> text-align css value

```js
label.setTextAlign('center');
```

<br/>
<br/>

## Attribute

### Data
레이블의 텍스트 및 텍스트 정렬을 설정하는 속성

* **Text:** 레이블의 텍스트를 설정하는 속성
* **Align:** 레이블 텍스트의 정렬을 설정하는 속성
    * **left:** 텍스트를 좌측 정렬한다.
    * **center:** 텍스트를 가운데 정렬한다.
    * **right:** 텍스트를 추측 정렬한다.

* **Line Breaks:** 레이블의 텍스트 줄바꿈 옵션을 설정하는 속성
    * **break word:** 단어 단위로 줄바꿈을 실행한다.
    * **break all:** 글자 단위로 줄바꿈을 실행한다.

* **pre formatted:** 라벨의 텍스트를 \<pre> 태그로 감싸도록 한다.
