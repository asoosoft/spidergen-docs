# ASwitchButton
> **Extends**: [`AComponent`](AComponent.html#AComponent)

스위치버튼

<br/>

## Instance Variables

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

## Instance Methods

### getValue()

컴포넌트의 값을 반환한다.

- **Returns** \<Boolean>

<br/>

### setSwitchOffStyle( backOffStyle )

스위치버튼의 off 상태 스타일을 설정한다.

- `backOffStyle` \<String> 스타일명

<br/>

### setSwitchOnStyle( backOnStyle )

스위치버튼의 on 상태 스타일을 설정한다.

- `backOnStyle` \<String> 스타일명

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

<br/>
<br/>
