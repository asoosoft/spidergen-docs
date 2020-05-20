# ARadioGroup
> **Extends**: `AView`

라디오그룹

<br/>

## Properties


### radioBtns

<br/>

### selectedBtn

<br/>
<br/>

## Instance Methods

### btnClickEvent( radioBtn, info, e )

btnClickEvent

- `radioBtn` \<String> radioBtn
- `info` \<String> info
- `e` \<String> e

<br/>

### clearAll()

라디오그룹내에 있는 라디오버튼들의 선택여부를 false로 설정한다.

* **Usage**: 
```js
this.rg1.clearAll();
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채웁니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### getRadioBtnById( id )

라디오그룹내에 매개변수 id값과 같은 id의 라디오버튼을 반환한다.

- `id` \<String> 라디오버튼 id
- **Returns** <ARadioButton>

```js
var radio = this.radioGroup1.getRadioBtnById('radioId1');
```

<br/>

### getRadioBtnByValue( value )

라디오 그룹 내의 매개변수 value의 값을 가지고 있는 라디오 버튼을 반환한다.

- **Returns** \<ARadioButton>
- `value` \<String> 라디오버튼의 value

```js
var radio = this.radioGroup1.getRadioBtnByValue('value1');
```

<br/>

### getRadioBtns()

라디오그룹내에 있는 라디오버튼을 배열로 반환한다.

- **Returns** \<Array>

* **Usage**: 
```js
var radios = this.radioGroup1.getRadioBtns();
```

<br/>

### getSelectBtn()

라디오그룹내에서 선택상태인 라디오버튼을 반환한다.

- **Returns** <ARadioButton>

```js
var selected = this.radioGroup1.getSelectBtn();
```

<br/>

### selectBtnByValue( value )

라디오그룹내에 매개변수 value 의 값을 가지고 있는 라디오버튼이 있다면 선택상태로 설정한다.

- `value` \<String> 라디오버튼 value

```js
this.radioGroup1.selectBtnByValue('value1');
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### setSelectBtn( radioBtn )

매개변수 radioBtn으로 받은 라디오버튼을 선택상태로 설정한다.

- `radioBtn` \<Object> ARadioButton

```js
this.radioGroup1.setSelectBtn(this.radioBtn1);
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.
<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var btn = new AButton();
btn.init();
```

<br/>

### getSelectIndex()

라디오 버튼 내의 선택되어 있는 버튼의 인덱스 값을 반환합니다.

- **Returns** \<Number>

```js
var a = this.radioGroup.getSelecteIndex();
```

<br/>

### getSelectValue()

라디오 버튼 내의 선택되어 있는 버튼의 값을 반환합니다.

- **Returns** \<Any>
```js
var a = this.radioGroup.getSelectValue();
```

<br/>

### setData( data )

데이터를 설정합니다.

- `data` <any> 입력하려는 데이터
	
```js
this.radioGroup.setData('test');
```

<br/>
<br/>

## Events


### change( comp, info, e )

그룹내의 선택된 라디오버튼이 변경될때 발생한다.

- `comp` \<AComponent> 컴포넌트
- `info` \<AComponent> 라디오버튼
- `e` \<Object> 이벤트

<br/>
<br/>

## Attribute

### Data  

- `Default ID`  그룹화된 라디오 버튼들 중 기본적으로 선택될 라디오 버튼 ID를 지정하는 속성입니다.  

<br/>



