# ARadioButton
**Extends**: [`AComponent`](AComponent.html#AComponent)

라디오버튼

<br/>

## Instance Variables

### isSelected <Boolean>

라디오버튼의 선택여부

<br/>

### isTabable <Boolean>

탭키로 이동이 가능한 컴포넌트 여부

<br/>

### selectClass <String>

라디오버튼의 선택시 추가할 클래스명

<br/>
<br/>

## Instance Methods

### getCheckAlign()

라디오버튼의 방향을 반환한다.

- **Returns** \<String>

<br/>

### getSelect()

선택여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### getText()

라디오버튼의 라벨 텍스트를 반환한다.

- **Returns** \<String>

<br/>

### getValue()

라디오버튼의 값을 반환한다.

* **Returns** \<String>

<br/>

### setCheckAlign( align )

라디오버튼의 방향을 설정한다.

- `align` \<String> 방향 (left / right)

```js
this.radio1.setCheckAlign('left');
```

<br/>

### setSelect( isSelect )

선택 여부를 설정한다.

- `isSelect` \<Boolean> 선택 여부

```js
this.radio1.setSelect(true);
```

<br/>

### setSelectStyle( selectClass )

- `selectClass` \<>

<br/>

### setText( text )

라디오버튼의 글자를 설정한다.

- `text` \<String> 텍스트

<br/>

### setValue( value )

라디오버튼의 값을 설정한다.

- `value` \<String> 값

<br/>
<br/>

## Events

### click( comp, info, e )

라디오버튼을 클릭할때 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `info` \<String> null
- `e` \<Object> 이벤트 정보

<br/>
<br/>

## Attribute

### Data

- `Text`
- `Align`
    - `left`
    - `center`
    - `right`
    
- `Check Pos`
    - `left`
    - `right`
    
- `Value` 
<br/>
