# ASelectBox
> **Extends**: `AComponent`

셀렉트박스

<br/>

## Properties

### isTabable



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### addItem( text, value, data )

셀렉트박스에 아이템을 추가한다.

* **Parameters**: 
	* **`text`** {String} 아이템명
	* **`value`** {String} 아이템값
	* **`data`** {All} 아이템데이터

* **Usage**: 
```js
this.select1.addItem('text1', 'value1', 'data1');
```

<br/>

### getItem( index )

매개변수 index에 해당하는 아이템을 반환한다.<br/>index는 0부터 시작한다.

* **Returns**: Object

* **Parameters**: 
	* **`index`** {Number} 아이템위치

* **Usage**: 
```js
var i = this.select1.getItem(0);
```

<br/>

### getItemData( index )

매개변수 index에 해당하는 아이템의 데이터를 반환한다.<br/>index는 0부터 시작한다.

* **Returns**: Any

* **Parameters**: 
	* **`index`** {Number} 인덱스

* **Usage**: 
```js
var d = this.select1.getItemData(0);
```

<br/>

### getItemSize()

셀렉트박스 아이템의 갯수를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var i = this.select1.getItemSize();
```

<br/>

### getItemValue( index )

매개변수 index에 해당하는 아이템의 값을 반환한다.<br/>index는 0부터 시작한다.

* **Returns**: String

* **Parameters**: 
	* **`index`** {Number} 인덱스

* **Usage**: 
```js
var v = this.select1.getItemValue(0);
```

<br/>

### getPadding()

셀렉트박스에 설정된 padding 값을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var p = this.select1.getPadding();
```

<br/>

### getSelectedIndex()

선택된 아이템의 index를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var i = this.select1.getSelectedIndex();
```

<br/>

### getSelectedItem()

선택된 아이템을 반환한다.

* **Returns**: Object

* **Usage**: 
```js
var o = this.select1.getSelectedItem();
```

<br/>

### getSelectedItemData()

선택된 아이템의 데이터를 반환한다.

* **Returns**: Any

* **Usage**: 
```js
var d = this.select1.getSelectedItemData();
```

<br/>

### getSelectedItemValue()

선택된 아이템의 값을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var v = this.select1.getSelectedItemValue();
```

<br/>

### getTextAlign()

셀렉트박스의 텍스트 정렬 속성을 리턴합니다.

* **Returns**: String

<br/>

### indexOfData( data )

매개변수 data와 같은 데이터를 가지는 아이템의 index를 반환한다.<br/>index는 0부터 시작하고 해당하는 아이템이 없다면 -1을 반환한다.

* **Returns**: Number

* **Parameters**: 
	* **`data`** {All} 데이터

* **Usage**: 
```js
var i = this.select1.indexOfData('data1');
```

<br/>

### indexOfValue( value )

매개변수 value 에 값을 가지는 아이템의 index를 반환한다.<br/>index는 0부터 시작하고 해당하는 아이템이 없다면 -1을 반환한다.

* **Returns**: Number

* **Parameters**: 
	* **`value`** {String} 값

* **Usage**: 
```js
var i = this.select1.indexOfValue('value1');
```

<br/>

### insertItem( text, value, data, index )

셀렉트박스에 아이템을 추가한다.<br/>매개변수 index 에 값이 없다면 가장 뒤에 아이템을 추가한다.<br/>index는 0부터 시작한다.

* **Parameters**: 
	* **`text`** {String} 아이템명
	* **`value`** {String} 아이템값
	* **`data`** {All} 아이템데이터
	* **`index`** {Number} 아이템 추가 위치

* **Usage**: 
```js
this.select1.insertItem('text1', 'value1', 'data1', 1);
```

<br/>

### removeAll()

셀렉트박스의 아이템을 모두 삭제한다.

* **Usage**: 
```js
this.select1.removeAll();
```

<br/>

### removeItem( index )

매개변수 index 위치에 해당하는 아이템을 삭제한다.<br/>index는 0부터 시작한다.

* **Parameters**: 
	* **`index`** {Number} 아이템위치

* **Usage**: 
```js
this.select1.removeItem(0);
```

<br/>

### selectItem( index )

매개변수 index에 해당하는 아이템을 선택상태로 설정한다.<br/>index는 0부터 시작한다.

* **Parameters**: 
	* **`index`** {Number} 아이템위치

* **Usage**: 
```js
this.select1.selectItem(2);
```

<br/>

### selectItemByData( data )

매개변수 data와 같은 데이터를 가지는 아이템을 선택상태로 설정한다.

* **Parameters**: 
	* **`data`** {All} 데이터

* **Usage**: 
```js
this.select1.selectItemByData('data1');
```

<br/>

### selectItemByValue( value )

매개변수 value와 같은 값을 가지는 아이템을 선택상태로 설정한다.

* **Parameters**: 
	* **`value`** {String} 아이템값

* **Usage**: 
```js
this.select1.selectItemByValue('value1');
```

<br/>

### setItemData( index, data )

매개변수 index 에 해당하는 아이템에 데이터를 설정한다.<br/>index는 0부터 시작한다.

* **Parameters**: 
	* **`index`** {Number} 아이템위치
	* **`data`** {All} 아이템데이터

* **Usage**: 
```js
this.select1.setItemData(0, 'data1');
```

<br/>

### setItemValue( index, value )

매개변수 index에 해당하는 아이템의 값을 설정한다.<br/>index는 0부터 시작한다.

* **Parameters**: 
	* **`index`** {Number} 아이템위치
	* **`value`** {String} 아이템값

* **Usage**: 
```js
this.select1.setItemValue(0, 'value1');
```

<br/>

### setPadding( padding )

셀렉트박스의 padding 값을 설정한다.

* **Parameters**: 
	* **`padding`** {Number} 패딩값

* **Usage**: 
```js
this.select1.setPadding(10);
```

<br/>

### setTextAlign( align )

셀렉트박스의 텍스트 정렬 속성을 셋팅합니다.

* **Parameters**: 
	* **`align`** {String} 정렬 속성

<br/>
### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setItemText()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getItemText()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getSelectedItemText()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### indexOfText()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### selectItemByText()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### removeItemByText()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### removeItemByData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### removeItemByValue()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### indexOf()



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

### setQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>

## Events

### change( comp, info, e )

값을 변경하면 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} 선택된 값
	* **`e`** {String} null

<br/>
<br/>

## Attribute

### Data 

* **Default Data** : 셀렉트박스에 보여질 리스트 데이터를 설정합니다. 텍스트와 값은 (,) 콤머로 구분하고 이이템들은 개행(엔터)으로 구분합니다. 

<br/>
 
