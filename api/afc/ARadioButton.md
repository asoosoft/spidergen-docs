# ARadioButton
**Extends**: `AComponent`

라디오버튼

<br/>

## Properties

### isSelected <Boolean>

라디오버튼의 선택여부이다.

<br/>

### selectClass <String>

라디오버튼의 선택시 추가할 클래스명이다.

<br/>

### isTabable <Boolean>

탭키로 이동이 가능한 컴포넌트 여부

<br/>
<br/>

## Instance Methods

### getCheckAlign()

라디오버튼의 방향을 반환한다.

- **Returns** \<String>

```js
var a = this.radio1.getCheckAlign();
```

<br/>

### getSelect()

선택여부를 반환한다.

- **Returns** \<Boolean>

```js
var a = this.radio1.getSelect();
```

<br/>

### getText()

라디오버튼의 라벨 텍스트를 반환한다.

- **Returns** \<String>

```js
var a = this.radio1.getText();
```

<br/>

### getValue()

라디오버튼의 값을 반환한다.

* **Returns** \<String>

```js
var v = this.radio1.getValue();
```

<br/>

### setCheckAlign( align )

라디오버튼의 방향을 설정한다.

- `align` \<String> left : 왼쪽, right : 오른쪽

```js
this.radio1.setCheckAlign('left');
```

<br/>

### setSelect( isSelect )

선택 여부를 설정한다.

- `isSelect` \<Boolean> 선택 여부

```js
this.radio1.setSelect(true);
```

<br/>

### setText( text )

라디오버튼의 글자를 설정한다.

- `text` \<String> 텍스트

```js
this.radio1.setText('라디오 버튼 라벨');
```

<br/>

### setValue( value )

라디오버튼의 값을 설정한다.

- `value` \<String> 값

```js
this.radio1.setValue('thisRadioValue');
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.
<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var radioBtn = new ARadioButton();
radioBtn.init();
```

### setSelectStyle( selectClass ) 수정필요

- `selectClass` \<Boolean>

### setData( data )

데이터를 설정한다.

- 'data' \<Any> 입력하고 싶은 데이터

```js
this.radio1.setData('test');
```

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr의 정보에 따라 dataArr에 채운다.
<br/>dataArr은 AQueryData 특정 부분의 참조자이다.
<br/><br/>
자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr의 정보를 참조하여 컴포넌트에 세팅한다. 
<br/>dataArr은 AQueryData 특정 부분의 참조자이다.
<br/><br/>
자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>
<br/>

## Events

### click( comp, info, e )

라디오버튼을 클릭할때 발생한다.

- `comp` \<AComponent> 컴포넌트
- `info` \<String> null
- `e` \<Object> 이벤트 정보

<br/>
<br/>

## Attribute

### Data

* **Text:** 설명이 필요합니다.
* **Align:** 설명이 필요합니다.
    * **left:** 설명이 필요합니다.
    * **center:** 설명이 필요합니다.
    * **right:** 설명이 필요합니다.
    
* **Check Pos:** 설명이 필요합니다.
    * **left:** 설명이 필요합니다.
    * **right:** 설명이 필요합니다.
    
* **Value:** 설명이 필요합니다.

<br/>
