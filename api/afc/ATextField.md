# ATextField
**Extends** [`AComponent`](AComponent.html#AComponent)

텍스트 필드

<br/>

## Instance Variables

### txfStyles \<Array> 
텍스트 필드 스타일

* `Default` ['', '']

<br/>

### isTabable \<Boolean>

탭키로 이동이 가능한 컴포넌트 여부

<br/>

### isTimerChange \<Boolean>

텍스트 변경을 체크하는 타이머 실행 여부

<br/>
<br/>

## Instance Methods

### applyBaseState()

컴포넌트의 defStyle변수에 저장해둔 기본클래스를 적용한다.<br/>
저장해둔 defStyle이 없다면 baseState변수에서 background-color와 border style만 적용한다.

<br/>

### changeBtnState( newState )

컴포넌트의 상태를 변경한다.

- `newState` \<String> 변경할 상태값 (ATextField.OVER / ATextField.DOWN / ATextField.DISABLE)

```js
btn.changeBtnState(ATextField.DISABLE);
```

<br/>

### clearStateClass()

컴포넌트의 상태를 제거한다.

<br/>

### defaultTxfState()

텍스트 필드를 처음 로드됐을 때로 초기화한다.

<br/>

### enableTimerChange( enable )

텍스트 변경을 체크하는 타이머의 실행 여부를 설정한다.
 
- `enable` \<Boolean> 실행 여부

```js
this.textfield.enableTimerChange(true);
```

<br/>

### getAttrValue()

텍스트 값을 반환한다.

- **Returns** \<String>

<br/>

### getDataType()

데이터타입을 반환한다.

- **Returns** \<String>

<br/>

### getPadding()

패딩속성 값을 반환한다.

- **Returns** \<Number>

<br/>

### getText()

값을 반환한다.

- **Returns** \<String>

<br/>

### getTextAlign()

정렬 속성을 반환한다.

- **Returns** \<String> 'left' / 'center' / 'right'

<br/>

### reset()

입력된 텍스트를 모두 제거한다.


<br/>

### setAttrValue( text )

value 속성과 텍스트에 값을 입력한다.

- `text` \<String> 입력할 값

<br\>

### saveBaseState()

컴포턴트가 초기화될때 호출되는 함수로, data-style 속성을 defStyle 변수에 저장해 둔다. <br>
만약 data-style 속성에 값이 없다면 baseState 변수에 background-color, border style값을 저장해둔다.

<br/>

### setDataType( dataType )

컴포넌트의 데이터 타입을 설정한다.

- `dataType` \<String> 데이터타입(text / password / number / email / tel)

```js
this.textfield.setDataType('password');
```

<br/>

### setImeOnIE()

IE(Internet Explorer)에서 IME(Input Method Editor)를 적절한 css 형태로 변경한다.

<br/>

### setIme()

IE(Internet Explorer)를 제외한 곳에서 IME(Input Method Editor)를 적절한 css 형태로 변경한다.

<br/>

### setPadding( padding )

패딩 값을 설정한다.

- `padding` \<Number> 패딩값

<br/>

### setPadOption( padOption )

패딩 옵션을 설정한다.

- `padOption` \<Object> 옵션정보

<br/>

### setPlaceholder()

아무런 값이 입력되지 않았을 때 보여줄 텍스트(Placeholder)를 설정한다.

```js
this.textfield.setPlaceholder('여기에 텍스트를 입력하면 됩니다.');
```

<br/>

### setReadOnly( isReadOnly )

읽기 전용 여부를 설정한다.

- `isReadOnly` \<Boolean> 읽기전용 여부

<br/>

### setSelectionRange(start, end, dir)

블록 선택을 설정한다.

- `start` \<Number> 첫 번째로 선택된 문자의 인덱스
- `end` \<Number> 마지막으로 선택된 문자의 인덱스
- `dir` \<String> 선택이 수행된 것으로 간주되는 방향(forward / backward / none)

<br/>

### setText( text )

매개변수 text 값을 컴포넌트의 값으로 설정한다.

- `text` \<String> 텍스트

<br/>

### setTextAlign( align )

정렬 속성을 설정한다.

- `align` \<String> 정렬방향 (left / right / center)

```js
this.textfield.setTextAlign('left');
```

<br/>
<br/>

## Events

### blur( comp, info, e )

포커스가 해제되면 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `info` \<String> null
- `e` \<Object> 이벤트 객체

### change( comp, info, e )

값을 변경하면 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `info` \<String> 값
- `e` \<Object> 이벤트 객체

### focus( comp, info, e )

포커스되면 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
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

- `Text` 텍스트 값을 설정하는 속성입니다. 
- `Placeholder` 플레이스홀더 값을 설정하는 속성입니다. 
- `Data Type` 텍스트필드의 데이터 타입을 설정하는 속성입니다. 
    - `text` 수정 가능한 텍스트 입니다. 
    - `search` 모든 기능이 text 타입과 동일하나 특정 브라우저에서 클리어 버튼이 노출됩니다. 
    - `password` 입력 내용을 확인 할 수 없는 모양으로 입력값이 표시됩니다. 
    - `number` 숫자만 입력이 가능합니다. 
    - `email` 이메이 주소 형식으로만 입력이 가능합니다. 
    - `tel` 전화번호 형식으로 입력이 가능합니다. 
    - `file` 파일 형식으로 입력이 가능합니다.
   
- `Align` 텍스트의 정렬을 설정하는 속성입니다. 
    - `left` 텍스트를 좌측으로 정렬 합니다. 
    - `center` 텍스트를 중앙으로 정렬 합니다. 
    - `right` 텍스트를 우측으로 정렬합니다. 

- `MaxLength` 설명이 필요합니다.
- `IME`텍스트 입력모드(국문/영문속성입니다.)을 설정하는 (IE 브라우저만 가능) 
    - `none`입력 모드를 설정하지 않고 현재 로컬 상태를 그대로 사용합니다. 
    - `english` 영문 입력 모드로 설정합니다. 
    - `korean` 국문 입력 모드로 설정합니다. 

### Option
- `TimerChange` 체인지 이벤트 시 시간으로 체크합니다.
- `FocousSelection` 포커스 이벤트 시 전체 텍스트를 블럭으로 선택합니다.
