# ASlider
> **Extends**: `AComponent`

슬라이더

<br/>

## Methods

### getMappingCount()

매핑가능한 배열을 리턴한다.<br/>['value', 'max', 'min', 'step']

<br/>

### getMax()

슬라이더의 최대값을 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var m = this.slider1.getMax();
```

<br/>

### getMin()

슬라이더의 최소값을 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var m = this.slider1.getMin();
```

<br/>

### getStep()

슬라이더의 이동 단위값을 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var s = this.slider1.getStep();
```

<br/>

### getValue()

슬라이더의 현재 값을 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var v = this.slider1.getValue();
```

<br/>

### setMax( max )

슬라이더의 최대값을 매개변수 max 값으로 설정한다.

* **Parameters**: 
	* **`max`** {Number} 최대값

* **Usage**: 
```js
this.slider1.setMax(50);
```

<br/>

### setMin( min )

슬라이더의 최소값을 매개변수 min 값으로 설정한다.

* **Parameters**: 
	* **`min`** {Number} 최소값

* **Usage**: 
```js
this.slider1.setMin(20);
```

<br/>

### setStep( step )

슬라이더의 이동 단위 값을 매개변수 step 값으로 설정한다.

* **Parameters**: 
	* **`step`** {Number} 이동 단위 값

* **Usage**: 
```js
this.slider1.setStep(10);
```

<br/>

### setValue( value )

슬라이더의 값을 매개변수 value 값으로 설정한다.

* **Parameters**: 
	* **`value`** {Number} 값

* **Usage**: 
```js
this.slider1.setValue(50);
```

<br/>
<br/>
## Events


### change( comp, e )

슬라이더의 값을 변경하면 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`e`** {Object} 이벤트 객체

<br/>

