# ARadioGroup
**Extends**: [`AView`](AView.html#AView)

라디오 그룹

<br/>

## Instance Variables

### radioBtns \<Array>

라디오 버튼 그룹으로 이루어진 배열


<br/>

### selectedBtn \<[AComponenet](AComponenet.html#AComponenet)>

현재 선택 상태인 라디오 버튼

<br/>
<br/>

## Instance Methods

### btnClickEvent( radioBtn, info, e )

버튼이 클릭되어 발생되는 것처럼 이벤트를 발생한다.

- `radioBtn` \<String> 선택되는 라디오 버튼
- `info` \<String>
- `e` \<String>

<br/>

### clearAll()

라디오 버튼들의 선택 여부를 false로 설정한다.

<br/>

### getRadioBtnById( id )

매개변수 id값과 같은 id의 라디오버튼을 반환한다.

- `id` \<String> 라디오버튼 id
- **Returns** \<[ARadioButton](ARadioButton.html#ARadioButton)>

```js
var radio = this.radioGroup1.getRadioBtnById('radioId1');
```

<br/>

### getRadioBtnByValue( value )

매개변수 value의 값을 가지고 있는 라디오 버튼을 반환한다.

- **Returns** \<[ARadioButton](ARadioButton.html#ARadioButton)>
- `value` \<String> 라디오버튼의 value

```js
var radio = this.radioGroup1.getRadioBtnByValue('value1');
```

<br/>

### getRadioBtns()

라디오 버튼을 배열로 반환한다.

- **Returns** \<Array>

<br/>

### getSelectBtn()

라디오 그룹 내에서 선택 상태인 라디오버튼을 반환한다.

- **Returns** \<[ARadioButton](ARadioButton.html#ARadioButton)>

<br/>

### selectBtnByValue( value )

value와 같은 값을 가지고 있는 라디오 버튼이 있다면 선택 상태로 설정한다.

- `value` \<String> 라디오버튼 value

```js
this.radioGroup1.selectBtnByValue('value1');
```

<br/>

### setSelectBtn( radioBtn )

매개변수 radioBtn으로 받은 라디오 버튼을 선택 상태로 설정한다.

- `radioBtn` \<Object> ARadioButton

<br/>

### getSelectIndex()

선택되어 있는 버튼의 인덱스 값을 반환합니다.

- **Returns** \<Number>

<br/>

### getSelectValue()

선택되어 있는 버튼의 값을 반환합니다.

- **Returns** \<Any>

<br/>
<br/>

## Events

### change( comp, info, e )

그룹내의 선택된 라디오버튼이 변경될때 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `info` \<[AComponent](AComponent.html#AComponent)> 라디오버튼
- `e` \<Object> 이벤트

<br/>
<br/>

## Attribute

### Data  

- `Default ID`  그룹화된 라디오 버튼들 중 기본적으로 선택될 라디오 버튼 ID를 지정하는 속성입니다.  

<br/>
