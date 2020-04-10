# ATextField
> **Extends**: `AComponent`

텍스트필드

<br/>

## Properties

### txfStyles

 

* **Type**: ``
* **Default**: ``

<br/>

### isTimerChange

 

* **Type**: ``
* **Default**: ``

<br/>

### isTabable

 

* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods


### enable( isEnable )

컴포넌트의 활성여부를 설정한다.

* **Parameters**: 
	* **`isEnable`** {Boolean} 활성여부

* **Usage**: 
```js
this.textfield.enable(false);
```

<br/>

### enableTimerChange( enable )

컴포넌트의 텍스트 변경을 체크하는 타이머의 실행여부를 설정한다.

* **Parameters**: 
	* **`enable`** {Boolean} 실행여부

* **Usage**: 
```js
this.textfield.enableTimerChange(true);
```

<br/>

### getDataType()

컴포넌트의 데이터타입을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var t = this.textfield.getDataType();
```

<br/>

### getPadding()

컴포넌트의 패딩속성 값을 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var p = this.textfield.getPadding();
```

<br/>

### getText()

컴포넌트의 값을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var t = this.textfield.getText();
```

<br/>

### getTextAlign()

컴포넌트의 정렬속성을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var a = this.textfield.getTextAlign();
```

<br/>

### setDataType( dataType )

컴포넌트의 데이터 타입을 설정한다.

* **Parameters**: 
	* **`dataType`** {String} 데이터타입(text/password/number/email/tel)

* **Usage**: 
```js
this.textfield.setDataType('password');
```

<br/>

### setPadding( padding )

매개변수 padding값을 컴포넌트의 패딩값으로 설정한다.

* **Parameters**: 
	* **`padding`** {Number} 패딩값

* **Usage**: 
```js
this.textfield.setPadding(20);
```

<br/>

### setPadOption( padOption )

패딩 옵션을 세팅합니다.

* **Parameters**: 
	* **`padOption`** {Object} 옵션정보

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### setReadOnly( isReadOnly )

컴포넌트의 읽기전용 여부를 설정한다.

* **Parameters**: 
	* **`isReadOnly`** {Boolean} 읽기전용 여부

* **Usage**: 
```js
this.textfield.setReadOnly(true);
```

<br/>

### setText( text )

매개변수 text 값을 컴포넌트의 값으로 설정한다.

* **Parameters**: 
	* **`text`** {String} 텍스트

* **Usage**: 
```js
this.textfield.setText('텍스트');
```

<br/>

### setTextAlign( align )

컴포넌트의 정렬속성을 설정한다.

* **Parameters**: 
	* **`align`** {String} 정렬방향 (left/right/center)

* **Usage**: 
```js
this.textfield.setTextAlign('left');
```

<br/>

### beforeInit()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setPlaceholder()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setAttrValue()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getAttrValue()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### defaultTxfState()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### clearStateClass()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### changeBtnState()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### applyBaseState()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### saveBaseState()



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

### setImeOnIE()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setIme()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### reset()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setSelectionRange()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>

## Events


### blur( comp, info, e )

포커스가 해제되면 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 객체

### change( comp, info, e )

값을 변경하면 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} 값
	* **`e`** {Object} 이벤트 객체

### focus( comp, info, e )

포커스되면 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 객체

### keydown()

키보드를 눌렀을때 호출합니다.

### keyup()

키보드를 눌렀다 뗐을때 호출합니다.

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

