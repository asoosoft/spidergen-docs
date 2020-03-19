# EXIscdBox
> **Extends**: `ADropBox`

.

<br/>

## Properties


### filterType

필터 타입

* **Type**: `Number`
* **Default**: `0`

<br/>
<br/>

## Methods

### addIscdItem( text, data )

종목 컴포넌트에 아이템을 추가합니다.

* **Parameters**: 
	* **`text`** {String} 종목명
	* **`data`** {Object} 종목정보 ex) {iscd: '001720', mkcd: 'J' }

<br/>

### getIscd()

선택된 종목의 코드를 리턴합니다.

* **Returns**: String

<br/>

### getIscdFilterType()

종목 필터 타입을 리턴합니다.

<br/>

### getMkcd()

선택된 종목의 시장구분코드를 리턴합니다.

* **Returns**: String

<br/>

### indexOfIscd()

종목코드로 아이템의 index를 찾아 리턴합니다.(index가 없을 경우 -1)

* **Returns**: Number

<br/>

### selectItemByIscd( iscd )

종목코드로 아이템을 선택합니다.

* **Parameters**: 
	* **`iscd`** {String} ex) '001720'

<br/>

### setIscdFilterType( filterType )

종목 필터 타입을 셋팅합니다.

* **Parameters**: 
	* **`filterType`** {String} ex) EXIscdBox.J or EXIscdBox.JW

<br/>

### init()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### removeExistIscd()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### selectItem()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### findFirstIscdIdxByMkcd()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### bindData()



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

### setQueryData()



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
<br/>
