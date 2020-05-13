# ATextArea
**Extends**: `AComponent`

텍스트영역

<br/>

## Properties

### isTimerChange \<Boolean>

텍스트 변경을 체크하는 타이머 실행 여부

<br/>

### isTabable \<Boolean>

탭키 이동이 가능한 컴포넌트 여부

<br/>
<br/>


## Instance Methods

### appendText( text )

매개변수 text의 값을 컴포넌트에 있는 값에 추가한다.

- `text` \<String> 텍스트

```js
this.textarea.appendText('추가할 텍스트');
```
<br/>

### enable( isEnable )

컴포넌트의 활성상태를 설정한다.

- `isEnable` \<Boolean> 상태값

```js
this.textarea.enable(false);
```

<br/>

### enableTimerChange( enable )

텍스트 변경을 체크하는 타이머 실행 여부를 설정한다.

- `enable`** \<Boolean> 실행 여부

```js
this.textarea.enableTimerChange(false);
```

<br/>

### getPadding()

컴포넌트에 설정된 패딩값을 반환한다.

- **Returns** \<Number>

```js
var p = this.textarea.getPadding();
```

<br/>

### getText()

컴포넌트에 설정된 텍스트값을 반환한다.

- **Returns** \<String>

```js
var t = this.textarea.getText();
```

<br/>

### getTextAlign()

컴포넌트에 설정된 정렬방향을 반환한다.

- **Returns** \<String>

```js
var a = this.textarea.getTextAlign();
```

<br/>

### isScroll()

컴포넌트 스크롤 가능여부를 반환한다.

- **Returns** \<Boolean>

```js
var b = this.textarea.isScroll();
```

<br/>

### setPadding( padding )

매개변수 padding값을 컴포넌트의 패딩값으로 설정한다.

- `padding` \<Number> 패딩값

```js
this.textarea.setPadding(20);
```

<br/>

### setReadOnly( isReadOnly )

컴포넌트의 읽기전용 속성을 설정한다.

- `isReadOnly` \<Boolean> 읽기전용 여부

```js
this.textarea.setReadOnly(true);
```

<br/>

### setText( text )

매개변수 text의 값을 컴포넌트 값으로 설정한다.

- `text` \<String> 텍스트

* **Usage**: 
```js
this.textarea.setText('텍스트');
```

<br/>

### setData( data )

매개변수 data의 값을 컴포넌트 값으로 설정한다.
setText()와 동일하다.

- `data` \<String> 텍스트

* **Usage**: 
```js
this.textarea.setData('텍스트');
```
<br/>

### setTextAlign( align )

매개변수 align 의 값으로 컴포넌트의 정렬방향을 설정한다.

- `align` \<String> 정렬방향 (left/right/center)

```js
this.textarea.setTextAlign('center');
```

<br/>

### init( context, evtListener )

컴포넌트 객체를 생성한 후 초기화 할 때 호출한다. 코딩을 이용하여 동적으로 객체를 생성할 경우 사용한다. 일반적으로 파라미터를 생략하여 기본값으로 생성 되도록 해준다.

- `context` \<String> 컴포넌트 생성 정보
- `evtListener` \<String> 이벤트 발생 시 수신할 객체

<br/>

### setPlaceholder()

아무런 값이 입력되지 않았을 때 보여줄 텍스트(Placeholder)를 설정한다.

- **Returns** \<String>

```js
this.textarea.setPlaceholder('여기에 텍스트를 입력하면 됩니다.');
```

<br/>

### getPlaceholder()

아무런 값이 입력되지 않았을 때 보여줄 텍스트(Placeholder)의 값을 반환한다.

- **Returns** \<String>

<br/>

### selectableReadOnly( isReadOnly )

글자를 입력할 수 없는 읽기 전용 상태로 만든다.

- `isReadOnly` \<Boolean> 읽기 전용 여부

<br/>

### getQueryData()

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.
dataArr은 AQueryData 특정부분의 참조자다.

자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setQueryData()

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다.
dataArr은 AQueryData 특정 부분의 참조자이다.

자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setImeOnIE()

IE(Internet Explorer)에서 IME(Input Method Editor)를 적절한 css 형태로 변경한다.

<br/>

### setIme()

IE(Internet Explorer)를 제외한 곳에서 IME(Input Method Editor)를 적절한 css 형태로 변경한다.

<br/>

### setInnerText( text )

<textarea> 태그 내에 텍스트를 추가한다.

- `test` \<String> 추가할 텍스트

```js
this.textarea.setInnerText('여기에 텍스트를 입력하면 됩니다.');
```

<br/>

### getInnerText()

<textarea> 태그 내에 텍스트값을 반환한다.

- **Returns** \<String>

<br/>

### scrollToTop()

입력창의 최상단으로 이동한다.

<br/>

### scrollToBottom()

입력창의 최하단으로 이동한다.

<br/>

### reset()

입력된 텍스트를 모두 제거한다.

<br/>
<br/>

## Events

### blur( comp, e )

컴포넌트에서 포커스가 사라지면 발생한다.

- `comp` \<AComponent> 컴포넌트
- `e` \<Object> 이벤트 객체

### change( comp, info )

값이 변경되면 발생한다.

- `comp` \<AComponent> 컴포넌트
- `info` \<String> 값

### focus( comp, e )

포커스 시 발생한다.

- `comp` \<AComponent> 컴포넌트
- `e` \<Object> 이벤트 객체

<br/>
<br/>

## Attribute

### Data   

* **Text:** 설명이 필요합니다.
* **Placeholder:** 플레이스홀더를 설정하는 속성입니다. 
* **Align:** 텍스트의 정렬을 설정하는 속성입니다. 
    * **left:** 텍스트를 좌측으로 정렬합니다. 
    * **center:** 텍스트를 중앙으로 정렬합니다. 
    * **right:** 텍스트를 우측으로 정력합니다. 

* **Alt:** 텍스트영역의 대체 텍스트를 설정하는 속성입니다. 
* **IME:** 텍스트 입력모드(국문/영문)를 설정하는 속성입니다. (IE에서만 가능) 
    * **none:** 입력모드를 설정하지 않고 현재 설정된 로컬 상태를 그대로 사용합니다. 
    * **english:** 텍스트 입력 모드를 영문 모드로 설정합니다. 
    * **korean:** 텍스트 입력 모드를 국문 모드로 설정합니다.  

