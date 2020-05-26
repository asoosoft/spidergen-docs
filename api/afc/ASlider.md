# ASlider
**Extends**: [`AComponent`](AComponent.html#AComponent)

슬라이더

<br/>

## Instance Variables

<br/>
<br/>

## Instance Methods

### getMax()

슬라이더의 최대값을 반환한다.

- **Returns** \<Number>

<br/>

### getMappingCount()

매핑가능한 배열을 리턴한다.<br/>
('value', 'max', 'min', 'step')

<br/>

### getMin()

슬라이더의 최소값을 반환한다.

- **Returns** \<Number>

<br/>

### getStep()

슬라이더의 이동 단위값을 반환한다.

- **Returns** \<Number>

<br/>

### getValue()

슬라이더의 현재 값을 반환한다.

- **Returns** \<Number>

<br/>

### setMax( max )

슬라이더의 최대값을 매개변수 max 값으로 설정한다.

- `max` \<Number> 최대값

<br/>

### setMin( min )

슬라이더의 최소값을 매개변수 min 값으로 설정한다.

- `min` \<Number> 최소값

<br/>

### setStep( step )

슬라이더의 이동 단위 값을 매개변수 step 값으로 설정한다.

- `step` \<Number> 이동 단위 값

<br/>

### setValue( value )

슬라이더의 값을 매개변수 value 값으로 설정한다.

- `value` \<Number> 값

<br/>
<br/>

## Events

### change( comp, e )

슬라이더의 값을 변경하면 발생한다.

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트
- `e` \<Object> 이벤트 객체

<br/>
<br/>

## Attribute

### Data

- `Value`  슬라이더의 현재 값을 설정하는 속성입니다.
* `Min`  슬라이더의 최소값을 설정하는 속성입니다.
* `Max`  슬라이더의 최대값을 설정하는 속성입니다.
* `Step` 슬라이더의 각 단위를 설정하는 속성입니다.

<br/>