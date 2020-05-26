# ATextArea
**Extends** [`AComponent`](AComponent.html#AComponent)

텍스트 영역

<br/>

## Instance Variables

### isTabable \<Boolean>

탭키로 이동이 가능한 컴포넌트 여부

<br/>

### isTimerChange \<Boolean>

텍스트 변경을 체크하는 타이머 실행 여부

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

- `enable` \<Boolean> 실행 여부

```js
this.textarea.enableTimerChange(false);
```

<br/>

### getInnerText()

내부 텍스트(Attribute - Text)의 텍스트값을 반환한다.

- **Returns** \<String>

```js
var a = this.textarea.getInnerText();
```

<br/>

### getPadding()

컴포넌트에 설정된 패딩값을 반환한다.

- **Returns** \<Number>

```js
var a = this.textarea.getPadding();
```

<br/>

### getPlaceholder()

아무런 값이 입력되지 않았을 때 보여줄 텍스트(Placeholder)의 값을 반환한다.

- **Returns** \<String>

```js
var a = this.textarea.getPlaceholder();
```

<br/>

### getText()

컴포넌트에 설정된 텍스트값을 반환한다.

- **Returns** \<String>

<br/>

### getTextAlign()

컴포넌트에 설정된 정렬방향을 반환한다.

- **Returns** \<String>

<br/>

### isScroll()

컴포넌트 스크롤 가능여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### reset()

입력된 텍스트를 모두 제거한다.

<br/>

### scrollToBottom()

텍스트 영역의 최하단으로 이동한다.

<br/>

### scrollToTop()

텍스트 영역 최상단으로 이동한다.

<br/>

### selectableReadOnly( isReadOnly )

글자를 입력할 수 없는 읽기 전용 상태로 만든다.

- `isReadOnly` \<Boolean> 읽기 전용 여부

<br/>

### setIme()

IE(Internet Explorer)를 제외한 곳에서 IME(Input Method Editor)를 적절한 css 형태로 변경한다.

<br/>

### setImeOnIE()

IE(Internet Explorer)에서 IME(Input Method Editor)를 적절한 css 형태로 변경한다.

<br/>

### setInnerText( text )

내부 텍스트(Attribute - Text)에 텍스트값을 입력한다.

- `test` \<String> 추가할 텍스트

<br/>

### setPadding( padding )

매개변수 padding값을 컴포넌트의 패딩값으로 설정한다.

- `padding` \<Number> 패딩값

<br/>

### setPlaceholder( placeholder )

아무런 값이 입력되지 않았을 때 보여줄 텍스트(Placeholder)를 설정한다.

- `placeholder` \<String> 입력하고 싶은 텍스트

<br/>

### setReadOnly( isReadOnly )

컴포넌트의 읽기전용 속성을 설정한다.

- `isReadOnly` \<Boolean> 읽기전용 여부

<br/>

### setText( text )

매개변수 text의 값을 컴포넌트 값으로 설정한다.

- `text` \<String> 텍스트

<br/>

### setTextAlign( align )

매개변수 align의 값으로 컴포넌트의 정렬방향을 설정한다.

- `align` \<String> 정렬방향 (left/right/center)

<br/>
<br/>

## Events

### blur( comp, e )

컴포넌트에서 포커스가 사라지면 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `e` \<Object> 이벤트 객체

### change( comp, info )

값이 변경되면 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `info` \<String> 값

### focus( comp, e )

포커스 시 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `e` \<Object> 이벤트 객체

<br/>
<br/>

## Attribute

### Data   

* `Text` 내부 텍스트를 입력하는 속성입니다.
* `Placeholder` 아무런 값이 입력되지 않았을 때 보여줄 텍스트(Placeholder)를 설정하는 속성입니다. 
* `*Align` 텍스트의 정렬을 설정하는 속성입니다. 
    * `left` 텍스트를 좌측으로 정렬합니다. 
    * `center` 텍스트를 중앙으로 정렬합니다. 
    * `right` 텍스트를 우측으로 정력합니다. 

* `Alt` 텍스트 영역의 대체 텍스트를 설정하는 속성입니다. 
* `IME` 텍스트 입력모드(국문/영문)를 설정하는 속성입니다. (IE에서만 가능) 
    * `none` 입력모드를 설정하지 않고 현재 설정된 로컬 상태를 그대로 사용합니다. 
    * `english` 텍스트 입력 모드를 영문 모드로 설정합니다. 
    * `korean` 텍스트 입력 모드를 국문 모드로 설정합니다.  
