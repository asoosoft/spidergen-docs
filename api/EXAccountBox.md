# EXAccountBox
> **Extends**: `AComponent`

계좌번호

<br/>

## Properties

### accInfo

선택한 계좌정보

* **Type**: `Object`
* **Default**: `null`

<br/>

### accList

계좌목록 리스트

* **Type**: `Array`
* **Default**: `new Array()`

<br/>

### accNmField

계좌명 표시 필드 묶음

* **Type**: `ALabel`
* **Default**: `null`

<br/>

### accNoField

계좌번호 표시 필드 묶음

* **Type**: `Array`
* **Default**: `new Array()`

<br/>

### accType

계좌목록에서 필터할 구분값

* **Type**: `Number`
* **Default**: `4`

<br/>

### accWindow

계좌를 선택하는 팝업창

* **Type**: `AWindow`
* **Default**: `null`

<br/>

### isGroup

계좌 그룹 여부

* **Type**: `Boolean`
* **Default**: `false`

<br/>

### isShowChildAccount

자계좌 표시여부

* **Type**: `Boolean`
* **Default**: `true`

<br/>

### preData

이전 선택한 계좌정보

* **Type**: `Object`
* **Default**: `null`

<br/>

### pwCallback

계좌 비번 일치시 다음에 실행되어야할 콜백 함수

* **Type**: `Function`
* **Default**: `null`

<br/>

### pwViewShowType

비밀번호 입력창 숨김 여부

* **Type**: `Number`
* **Default**: `AComponent.VISIBLE`

<br/>

### frwName



* **Type**: ``
* **Default**: ``

<br/>

### accButton



* **Type**: ``
* **Default**: ``

<br/>

### accChangeCnt



* **Type**: ``
* **Default**: ``

<br/>

### isBtnClickOpen



* **Type**: ``
* **Default**: ``

<br/>

### filterMap



* **Type**: ``
* **Default**: ``

<br/>

### filterType



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### accPwSaveCheck( callback )

선택한 계좌의 비밀번호 인증 후 파라미터로 넘어온 함수를 실행합니다.

* **Parameters**: 
	* **`callback`** {Function} 비밀번호 인증 후 처리할 함수

<br/>

### addNoLabel( labelArr )

계좌번호를 추가로 표시할 라벨을 셋팅합니다.

* **Parameters**: 
	* **`labelArr`** {Array} 라벨배열[ALabel, ALabel, ...]

<br/>

### clearNoLabel()

계좌번호를 추가로 표시할 라벨들을 삭제합니다.

<br/>

### clearPassword ()()

보안키패드로 입력받은 계좌의 비밀번호를 클리어합니다.

<br/>

### getAccData()

계좌컴포넌트에 셋팅된 계좌정보를 리턴합니다.

* **Returns**: Object

<br/>

### getAccNmText()

계좌명을 리턴합니다.

* **Returns**: String

<br/>

### getAccNoText()

계좌번호를 리턴합니다.

* **Returns**: String

<br/>

### getAccType()

계좌타입을 리턴합니다.

* **Returns**: Number

<br/>

### getFilterType( containerId )

파라미터로 넘어온 containerId에 셋팅된 계좌필터타입을 리턴합니다.

* **Returns**: Number

* **Parameters**: 
	* **`containerId`** {String} 컨테이너id

<br/>

### selectItemByText( text )

계좌드롭박스를 파라미터로 넘어온 계좌번호로 선택되게 합니다.

* **Parameters**: 
	* **`text`** {String} 계좌번호

<br/>

### setAccData( accInfo )

파라미터로 넘어온 계좌정보를 계좌컴포넌트에 셋팅합니다.

* **Parameters**: 
	* **`accInfo`** {Object} 계좌정보

<br/>

### setAccType( accType )

파라미터로 넘어온 accType(계좌타입)을 계좌컴포넌트에 셋팅합니다.

* **Parameters**: 
	* **`accType`** {Number} 계좌타입

<br/>

### setDefaultData()

기존에 선택했던 계좌를 디폴트값으로 셋팅합니다.

<br/>

### setGroupByAccInfo()

계좌번호를 그룹핑합니다.

<br/>

### setNameLabel( labelComp )

계좌명을 표시할 라벨을 셋팅합니다.

* **Parameters**: 
	* **`labelComp`** {ALabel} .

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### setWindow( window )

계좌선택과 비밀번호를 입력할 윈도우 팝업을 셋팅합니다.

* **Parameters**: 
	* **`window`** {AWindow} 계좌선택과 비밀번호를 입력할 윈도우

<br/>

### showChildAccount( isShowChildAccount )

자계좌 표시여부를 셋팅합니다.

* **Parameters**: 
	* **`isShowChildAccount`** {Boolean} 표시여부

<br/>

### showPwView( showType )

계좌선택팝업창에서 비밀번호입력창 표시여부를 설정합니다.

* **Parameters**: 
	* **`showType`** {Boolean} 표시여부

<br/>

### init()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### defaultAction()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### refreshAccData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getExistAccInfoIdx()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### removeLastAccInfo()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### addLastAccInfo()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setAccText()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setAccNoText()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### openWindow()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### onWindowResult()



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

### getMappingCount()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
