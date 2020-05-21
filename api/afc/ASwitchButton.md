# ASwitchButton
> **Extends**: `AComponent`

스위치버튼

<br/>

## Properties


### backOffStyle \<String>

바탕Off스타일 
	
<br/>

### backOnStyle \<String>

바탕On스타일

<br/>

### barEl

바 버튼 돔 객체

<br/>

### isOn \<Boolean>

버튼의 on/off 상태

<br/>

### isTabable \<Boolean>
탭키 이동이 가능한 컴포넌트 여부

<br/>
<br/>

## Methods

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getValue()

컴포넌트의 값을 반환한다.

- **Returns** \<Boolean>

```js
var a = this.switch.getValue();
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>
동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context에 매핑된 이벤트 수신자

```js
var dropBox = new ADropBox();
dropBox.init();
```

<br/>

### setData( data )

데이터를 설정한다.

- `data` \<any> 설정할 데이터

```js
this.switchButton.setData('test');
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setSwitchOffStyle( backOffStyle )

스위치버튼의 off 상태 스타일을 설정한다.

- `backOffStyle` \<String> 스타일명

```js
this.switch.setSwitchOffStyle('offStyle');
```

<br/>

### setSwitchOnStyle( backOnStyle )

스위치버튼의 on 상태 스타일을 설정한다.

- `backOnStyle` \<String> 스타일명

```js
this.switch.setSwitchOnStyle('onStyle');
```

<br/>

### setSwitchStyle( backOnStyle, backOffStyle )

스위치버튼의 on / off 시 스타일 설정한다. 바의 스타일은 css에서 다음과 같은 방식으로 선언한다.

- `backOnStyle` \<String> 바탕On스타일
- `backOffStyle` \<String> 바탕Off스타일

```js
this.switch.setSwitchStyle('onClass', 'offClass');
//css 스타일 정의
.switch-on.onClass span{ 스타일정의 }
```

<br/>

### setValue( isOn )

컴포넌트의 on / off 값을 설정한다.

- `isOn` \<Boolean> On/Off여부

```js
this.switch.setValue(true);
```

<br/>
<br/>
