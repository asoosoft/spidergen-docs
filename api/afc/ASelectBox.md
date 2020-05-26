# ASelectBox
**Extends**: [`AComponent`](AComponent.html#AComponent)

셀렉트 박스

<br/>

## Instance Variables

### isTabable \<Boolean>

탭 가능 여부

<br/>
<br/>

## Instance Methods

### addItem( text, value, data )

셀렉트박스에 아이템을 추가한다.

- `text` \<String> 아이템 이름
- `value` \<String> 아이템 값
- `data` \<Any> 아이템 데이터

<br/>

### getItem( index )

매개변수 index에 해당하는 아이템을 반환한다.<br/>
index는 0부터 시작한다.

- `index` \<Number> 아이템 위치
- **Returns** \<Object>

<br/>

### getItemData( index )

매개변수 index에 해당하는 아이템의 데이터를 반환한다.<br/>
index는 0부터 시작한다.

- `index` \<Number> 인덱스
- **Returns** \<Any>

<br/>

### getItemSize()

셀렉트박스 아이템의 갯수를 반환한다.

- **Returns** \<Number>

<br/>

### getItemText( index )

매개변수 index에 해당하는 아이템의 글자을 반환한다.<br/>
index는 0부터 시작한다.

- **Returns** \<String>

<br/>

### getItemValue( index )

매개변수 index에 해당하는 아이템의 값을 반환한다.<br/>
index는 0부터 시작한다.

- `index` \<Number> 인덱스
- **Returns** \<String>

<br/>

### getMappingCount()

매핑 가능한 배열을 반환한다. </br>
['value', 'text']

- `Returns` \<Array>

<br/>

### getPadding()

셀렉트박스에 설정된 padding 값을 반환한다.

- **Returns** \<String>

<br/>

### getSelectedIndex()

선택된 아이템의 index를 반환한다.

- **Returns** \<Number>

<br/>

### getSelectedItem()

선택된 아이템을 반환한다.

- **Returns** \<Object>

<br/>

### getSelectedItemData()

선택된 아이템의 데이터를 반환한다.

- **Returns** \<Any>

<br/>

### getSelectedItemText()

선택되어 있는 아이템의 글자를 반환한다.

- **Returns** \<String>

<br/>

### getSelectedItemValue()

선택된 아이템의 값을 반환한다.

- **Returns** \<String>

<br/>

### getTextAlign()

셀렉트박스의 텍스트 정렬 속성을 리턴합니다.

- **Returns** \<String>

<br/>

### indexOf( key, value )

키(글자, 값, 데이터)와 같은 값을 가진 아이템의 인덱스 값을 반환한다.</br>
index는 0부터 시작하고 해당하는 아이템이 없다면 -1을 반환한다.

- `key` \<Any> text / value / data
- **Returns** \<Number>

<br/>

### indexOfData( data )

매개변수 data와 같은 데이터를 가지는 아이템의 index를 반환한다.<br/>
index는 0부터 시작하고 해당하는 아이템이 없다면 -1을 반환한다.

- `data` \<Any> 데이터
- **Returns** \<Number>

<br/>

### indexOfText( text )

text와 같은 글자를 가진 아이템의 인덱스 값을 반환한다.</br>
index는 0부터 시작하고 해당하는 아이템이 없다면 -1을 반환한다.

- `text` \<String>
- **Returns** \<Number>

<br/>

### indexOfValue( value )

매개변수 value 에 값을 가지는 아이템의 index를 반환한다.<br/>
index는 0부터 시작하고 해당하는 아이템이 없다면 -1을 반환한다.

- `value` \<String> 값
- **Returns** \<Number>

<br/>

### insertItem( text, value, data, index )

셀렉트박스에 아이템을 추가한다.<br/>매개변수 index 에 값이 없다면 가장 뒤에 아이템을 추가한다.<br/>
index는 0부터 시작한다.

- `text` \<String> 아이템 이름
- `value` \<String> 아이템 값
- `data` \<All> 아이템 데이터
- `index` \<Number> 아이템 추가 위치

```js
this.select1.insertItem('text1', 'value1', 'data1', 1);
```

<br/>

### removeAll()

셀렉트박스의 아이템을 모두 삭제한다.

<br/>

### removeItem( index )

매개변수 index 위치에 해당하는 아이템을 삭제한다.<br/>
index는 0부터 시작한다.

- `index` \<Number> 아이템위치

<br/>

### removeItemByData( data )

data와 같은 데이터를 가진 아이템을 제거한다.

- `data` \<Any>

<br/>

### removeItemByText( text )

test와 같은 글자를 가진 아이템을 제거한다.

- `text` \<String>

<br/>

### removeItemByValue( value )

value와 같은 값을 가진 아이템을 제거한다.

- `value` \<Any>

<br/>

### selectItem( index )

매개변수 index에 해당하는 아이템을 선택상태로 설정한다.<br/>
index는 0부터 시작한다.

- `index` \<Number> 아이템 위치

<br/>

### selectItemByData( data )

매개변수 data와 같은 데이터를 가지는 아이템을 선택상태로 설정한다.

- `data` \<All> 데이터

<br/>

### selectItemByValue( value )

매개변수 value와 같은 값을 가지는 아이템을 선택상태로 설정한다.

- `value` \<String> 아이템값

<br/>

### setItemData( index, data )

매개변수 index 에 해당하는 아이템에 데이터를 설정한다.<br/>
index는 0부터 시작한다.

- `index` \<Number> 아이템위치
- `data` \<All> 아이템데이터

```js
this.select1.setItemData(0, 'data1');
```

<br/>

### setItemValue( index, value )

매개변수 index에 해당하는 아이템의 값을 설정한다.<br/>
index는 0부터 시작한다.

- `index` \<Number> 아이템위치
- `value` \<String> 아이템값

<br/>

### setPadding( padding )

셀렉트박스의 padding 값을 설정한다.

- `padding` \<Number> 패딩값

<br/>

### setTextAlign( align )

셀렉트박스의 텍스트 정렬 속성을 셋팅합니다.

- `align` \<String> 정렬 속성(left / right / center)

<br/>

### setItemText( index, text )

매개변수 index에 해당하는 아이템의 글자를 설정한다.<br/>
index는 0부터 시작한다.

<br/>

### selectItemByText( text )

text와 같은 글자를 가진 아이템을 선택한다.

- `text` \<String>

<br/>
<br/>

## Events

### change( comp, info, e )

값을 변경하면 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `info` \<String> 선택된 값
- `e` \<String> null

<br/>
<br/>

## Attribute

### Data 

- `Default Data` 셀렉트박스에 보여질 리스트 데이터를 설정합니다. 텍스트와 값은 콤마(,)로 구분하고 이이템들은 개행(엔터)으로 구분한다.

<br/>
 
