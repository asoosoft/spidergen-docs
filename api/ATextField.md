# ATextField
> **Extends**: `AComponent`

텍스트필드

<br/>

## Properties


### floatLenth

소수점 표현 자리수

* **Type**: `Number`
* **Default**: `2`

<br/>

### maskVal

마스크

* **Type**: `Number`
* **Default**: `afc.MASK_NONE`

<br/>

### maxLen

입력 최대길이

* **Type**: `Number`
* **Default**: `null`

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

### enableKeyPropagation( enable )

부모태그로부터 이벤트 전파를 stop 중지할지 여부를 정합니다.

* **Parameters**: 
	* **`enable`** {Boolean} true | false

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

