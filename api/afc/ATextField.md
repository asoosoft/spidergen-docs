# ATextField
> **Extends**: `AComponent`

텍스트 필드

<br/>


## Properties

### txfStyles - 수정필요




<br/>

### isTimerChange \<Boolean>

텍스트 변경을 체크하는 타이머 실행 여부

<br/>

### isTabable \<Boolean>

탭키로 이동이 가능한 컴포넌트 여부

<br/>
<br/>


## Instance Methods

### setAttrValue()

### getAttrValue()

### defaultTxfState()

### enable( isEnable )

컴포넌트의 활성 여부를 설정한다.

- `isEnable` \<Boolean> 활성 여부

```js
this.textfield.enable(false);
```

<br/>

### enableTimerChange( enable )

컴포넌트의 텍스트 변경을 체크하는 타이머의 실행 여부를 설정한다.
 
- `enable` \<Boolean> 실행 여부

```js
this.textfield.enableTimerChange(true);
```

<br/>

### getDataType()

컴포넌트의 데이터타입을 반환한다.

- **Returns** \<String>

```js
var a = this.textfield.getDataType();
```

<br/>

### getPadding()

컴포넌트의 패딩속성 값을 반환한다.

- **Returns** \<Number>

```js
var a = this.textfield.getPadding();
```

<br/>

### getText()

컴포넌트의 값을 반환한다.

- **Returns** \<String>

```js
var a = this.textfield.getText();
```

<br/>

### getTextAlign()

컴포넌트의 정렬속성을 반환한다.

- **Returns** \<String>

```js
var a = this.textfield.getTextAlign();
```

<br/>

### setDataType( dataType )

컴포넌트의 데이터 타입을 설정한다.

- `dataType` \<String> 데이터타입(text/password/number/email/tel)

```js
this.textfield.setDataType('password');
```

<br/>

### setPadding( padding )

매개변수 padding값을 컴포넌트의 패딩값으로 설정한다.

- `padding` \<Number> 패딩값

```js
this.textfield.setPadding(20);
```

<br/>

### setPadOption( padOption )

패딩 옵션을 세팅합니다.

- `padOption` \<Object> 옵션정보

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### setReadOnly( isReadOnly )

컴포넌트의 읽기전용 여부를 설정한다.

- `isReadOnly` \<Boolean> 읽기전용 여부

```js
this.textfield.setReadOnly(true);
```

<br/>

### setText( text )

매개변수 text 값을 컴포넌트의 값으로 설정한다.

- `text` \<String> 텍스트

```js
this.textfield.setText('텍스트');
```

<br/>

### setTextAlign( align )

컴포넌트의 정렬속성을 설정한다.

- `align` \<String> 정렬방향 (left/right/center)

```js
this.textfield.setTextAlign('left');
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var textField = new ATextField();
textField.init();
```

<br/>

### setPlaceholder()

아무런 값이 입력되지 않았을 때 보여줄 텍스트(Placeholder)를 설정한다.

```js
this.textfield.setPlaceholder('여기에 텍스트를 입력하면 됩니다.');
```

<br/>
<br/>

### clearStateClass()

컴포넌트의 상태를 삭제한다.

### changeBtnState( newState )

컴포넌트의 상태를 변경한다.

- `newState` \<String> 변경할 상태값 / ATextField.OVER, ATextField.DOWN, ATextField.DISABLE

```js
btn.changeBtnState(ATextField.DISABLE);
```

<br/>

### applyBaseState()

컴포넌트의 defStyle변수에 저장해둔 기본클래스를 적용한다.<br/>
저장해둔 defStyle이 없다면 baseState변수에서 background-color와 border style만 적용한다.

<br/>

### saveBaseState()

컴포턴트가 초기화될때 호출되는 함수로, data-style 속성을 defStyle 변수에 저장해 둔다. <br>
만약 data-style 속성에 값이 없다면 baseState 변수에 background-color, border style값을 저장해둔다.

<br/>

### setData( data )

매개변수 data의 값을 컴포넌트 값으로 설정한다.
setText()와 동일하다.

- `data` \<String> 텍스트

```js
this.textfield.setData('텍스트');
```

<br/>

### getQueryData()

컴포넌트가 갖고 있는 정보를 keyArr의 정보에 따라 dataArr에 채운다.
dataArr은 AQueryData 특정 부분의 참조자다.

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

### reset()

입력된 텍스트를 모두 제거한다.

```js
this.textarea.reset();
```

<br/>

### setSelectionRange(start, end, dir)

- `start` \<>
- `end` \<>
- `dir` \<>

<br/>
<br/>

## Events

### blur( comp, info, e )

포커스가 해제되면 발생한다.

- `comp` \<AComponent> 컴포넌트
- `info` \<String> null
- `e` \<Object> 이벤트 객체

### change( comp, info, e )

값을 변경하면 발생한다.

- `comp` \<AComponent> 컴포넌트
- `info` \<String> 값
- `e` \<Object> 이벤트 객체

### focus( comp, info, e )

포커스되면 발생한다.

- `comp` \<AComponent> 컴포넌트
- `info` \<String> null
- `e` \<Object> 이벤트 객체

### keydown()

키보드를 눌렀을 때 호출합니다.

### keyup()

키보드를 눌렀다 뗐을 때 호출합니다.

<br/>
<br/>

## Attribute 
 
### Data 

* **Text:** 텍스트 값을 설정하는 속성입니다. 
* **Placeholder:** 플레이스홀더 값을 설정하는 속성입니다. 
* **Data Type:** 텍스트필드의 데이터 타입을 설정하는 속성입니다. 
    * **text:** 수정 가능한 텍스트 입니다. 
    * **search:** 모든 기능이 text 타입과 동일하나 특정 브라우저에서 클리어 버튼이 노출됩니다. 
    * **password:** 입력 내용을 확인 할 수 없는 모양으로 입력값이 표시됩니다. 
    * **number:** 숫자만 입력이 가능합니다. 
    * **email:** 이메이 주소 형식으로만 입력이 가능합니다. 
    * **tel:** 전화번호 형식으로 입력이 가능합니다. 
    * **file:** 파일 형식으로 입력이 가능합니다.
   
* **Align:** 텍스트의 정렬을 설정하는 속성입니다. 
    * **left:** 텍스트를 좌측으로 정렬 합니다. 
    * **center:** 텍스트를 중앙으로 정렬 합니다. 
    * **right:** 텍스트를 우측으로 정렬합니다. 

* **MaxLength:** 설명이 필요합니다.
* **IME:** 텍스트 입력모드(국문/영문속성입니다.)을 설정하는 (IE 브라우저만 가능) 
    * **none:** 입력 모드를 설정하지 않고 현재 로컬 상태를 그대로 사용합니다. 
    * **english:** 영문 입력 모드로 설정합니다. 
    * **korean:** 국문 입력 모드로 설정합니다. 

### Option
* **TimerChange:** 설명이 필요합니다.
* **FocousSelection:** 설명이 필요합니다.
