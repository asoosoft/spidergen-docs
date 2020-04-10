# ACheckBox
> **Extends**: `AComponent`

체크박스

<br/>

## Properties


### checkClass

* **Type**: ``
* **Default**: `''`

<br/>

### isChecked



* **Type**: ``
* **Default**: `''`

<br/>

### isSafeClick



* **Type**: ``
* **Default**: `''`

<br/>

### isTabable



* **Type**: ``
* **Default**: `''`

<br/>
<br/>

## Methods

### getCheck()

체크여부를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = chk.getCheck();
```

<br/>

### getCheckAlign()

CheckBox컴포넌트에서 체크영역 정렬속성을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = chk.getCheckAlign();
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채웁니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### getText()

CheckBox의 텍스트를 리턴한다.

* **Usage**: 
```js
var result = chk.getText();
```

<br/>

### getValue()

CheckBox에 저장된  데이터값을 리턴한다.

* **Usage**: 
```js
va result = chk.getValue();
```

<br/>

### init( context, evtListener )

체크박스 컴포넌트를 생성하고 초기화 할 때 호출한다. <br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {String} context 에 매핑된 이벤트 수신자

* **Usage**: 
```js
var chk = new ACheckBox();
chk.init();
```

<br/>

### setCheck( check )

CheckBox의 체크여부를 지정한다.

* **Parameters**: 
	* **`check`** {String} 체크여부

* **Usage**: 
```js
chk.setCheck(true);
```

<br/>

### setCheckAlign( align )

CheckBox컴포넌트에서 체크영역의 정렬을 설정한다.

* **Parameters**: 
	* **`align`** {String} left : 왼쪽정렬, right : 오른쪽정렬

* **Usage**: 
```js
chk.setCheckAlign('left');
```

<br/>

### setCheckStyle( cBg, ncBg )

CheckBox 스타일에 사용 될 클래스명을 지정한다.

* **Parameters**: 
	* **`cBg`** {String} 체크클래스명
	* **`ncBg`** {String} 미체크클래스명

* **Usage**: 
```js
chk.setCheckStyle('check','non-check');
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### setText( text )

CheckBox의 텍스트를 지정한다.

* **Parameters**: 
	* **`text`** {String} 텍스트

* **Usage**: 
```js
chk.setText('Hello');
```

<br/>

### setValue( value )

CheckBox에 저장할  데이터값을 세팅한다. 해당 값은 data-check-value속성에 저장된다.

* **Parameters**: 
	* **`value`** {String} 값

* **Usage**: 
```js
chk.setValue('hello world');
```

<br/>

### setData()



* **Parameters**:

* **Usage**: 
```js
```

<br/>
<br/>

## Events

### click( comp, info, e )

체크박스가 클릭될떄 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} null
	* **`e`** {Object} 이벤트 정보

<br/>

## Attribute

### Data  

* **Text:** 체크박스의 텍스트를 설정하는 속성입니다. 
* **Align:** 체크박스의 텍스트 정렬을 설정하는 속성입니다. 
    * **left:** 텍스트를 좌측으로 정렬합니다.
    * **center:** 텍스트를 중앙으로 정렬합니다.
    * **right:** 텍스트를 우측으로 정렬합니다.

* **Check Pos:** 체크박스의 체크 위치를 설정하는 속성입니다.  
    * **left:** 체크가 텍스트 좌측에 위치합니다. 
    * **right:** 체크가 텍스트 우측에 위치합니다. 
    
* **Value:** 체크박스의 보유값을 설정하는 속성입니다. 
