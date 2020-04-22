# ADatePicker
**Extends**: [`AComponent`](AComponent.md#AComponent)

데이트피커

<br/>

## Properties


### date \<Date>

날짜

<br/>

### type \<String>

타입

<br/>

### isPickerOpen \<Boolean>

피커가 오픈되어있는지 여부

<br/>
<br/>

## Instance Methods

### androidFormatDate( date )

파라미터로 받은 날짜를 안드로이드 포맷으로 변환해서 리턴한다.

- **Returns** \<String>

- `date` \<Object> 날짜

```js
var date = new Date();
.
.
.
dataPicker.androidFormatDate(date);
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getType()

타입을 리턴한다.

- **Returns** \<String>

```js
var result = dataPicker.getType();
```

<br/>

### getValue()

날짜를 리턴한다.

- **Returns** \<String>

```js
var result = dataPicker.getValue();
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var dataPicker = new ADatePicker();
dataPicker .init();
```

<br/>

### iosFormatDate( date )

파라미터로 받은 날짜를 ios 포맷으로 변환해서 리턴한다.

- `date` \<String> 날짜
- **Returns** \<String>

<br/>

### openPicker()

데이트피커를 오픈한다.

```js
dataPicker.openPicker();
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setType( type )

타입을 세팅한다.

- `type` \<String> 타입 / ex) 'date', 'time'

```js
dataPicker.setType('date');
```

<br/>

### setValue( date )

날짜를 세팅한다.

- `date` \<String> 날짜

```js
dataPicker.setValue('20180401');

or

var date = new Date();
dataPicker.setValue(date);
```

<br/>

### show_android()

안드로이드 데이트피커를 오픈합니다.

```js
dataPicker.show_android();
```

<br/>

### show_ios()

ios 데이트피커를 오픈합니다.

```js
dataPicker.show_ios();
```

<br/>
<br/>

## Events


### change( comp, info, e )

데이트피커의 값이 변경될 때 호출 된다.

- `comp` \<AComponent> 컴포넌트
- `info` \<String> Date Value
- `e` \<Object> 이벤트 정보

<br/>

