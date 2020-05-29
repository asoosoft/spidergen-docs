# ADataMask( ele, acomp )
> **Extends**

* `ele` \<HTMLElement> 엘리먼트 객체
* `acomp` \<[AComponent](./AComponent.md)> 컴포넌트 객체

마스킹 함수, 파라미터 관리 객체

<br/>

## Class Variables

<br/>

## Instance Variables

### acomp \<AComponent>

마스킹 데이터가 세팅되는 컴포넌트 객체

<br/>

### ele \<HTMLElement>

마스킹 데이터가 세팅되는 엘리먼트 객체

<br/>

<!-- 
### maskFuncs \<Array>

마스킹 함수 저장 배열

<br/>

### maskParams \<Array>

마스킹 함수에 전달할 파라미터 저장 배열

<br/>
 -->

### isClear \<Boolean>

데이터를 세팅 후 통신 관련 데이터 제거여부

<br/>
<br/>

## Class Methods

### get( type, name )

타입과 이름에 해당하는 마스크 정보를 가져온다.

* `type` \<String> 타입
* `name` \<String> 이름
* **Returns** \<Object>> { title:'설명', param:[], func:function(){} }

<br/>

### getFunc( type, name )

타입과 이름에 해당하는 마스크 함수를 가져온다.

* `type` \<String> 타입
* `name` \<String> 이름
* **Returns** \<Function> 마스크 함수

<br/>
<br/>

## Instance Methods

### getMaskFunc( inx )

특정 위치의 마스킹 함수, 파라미터를 얻어온다.

* `inx` \<Number> 함수 위치값
* **Returns** \<Array> [ 마스크함수, 마스크 파라미터 ]

```js
var dm = new ADataMask(this.label.element, this.label);
dm.insertMaskFunc(ADataMask.Number.money.func);
dm.getMaskFunc(0); //[ ADataMask.Number.money.func, null ]
```

<br/>

### insertMaskFunc( func, param, ?inx )

마스킹 함수를 세팅한다.

* `func` \<function> 마스킹 함수
* `param` \<Array> 마스킹 함수에 전달할 파라미터 배열
* `?inx` \<Number> 함수 위치값

```js
var dm = new ADataMask(this.label.element, this.label);
dm.insertMaskFunc(ADataMask.Number.money.func);
dm.insertMaskFunc(ADataMask.Number.toFixed.func, [2], 0);
console.log(dm.mask(12345)); //12,345.00
```

<br/>

### mask( value, ele )

값을 저장된 마스킹 함수를 호출하여 가공한다.

* `value` \<String> 가공할 값
* `ele` \<HTMLElement> 마스킹처리할 엘리먼트 객체(없으면 저장된 엘리먼트 객체 사용)

```js
var dm = new ADataMask(this.label.element, this.label);
dm.insertMaskFunc(ADataMask.Number.money.func);
console.log(dm.mask(12345)); //12,345
```

<br/>

### moveMaskFunc( fromIdx, toIdx )

fromIdx 의 마스킹 함수와 파라미터를 toIdx 와 바꾼다.

* `fromIdx` \<Number> 이동시킬 함수 위치
* `toIdx` \<Number> 이동할 함수 위치

<br/>

### removeMaskFunc( inx )

특정 위치의 마스킹 함수와 파라미터를 제거한다.

* `inx` \<Number> 제거할 위치값

<br/>

### unmask( ele )

마스킹 전 값을 얻어온다.

* `ele` \<HTMLElement> 마스킹처리한 엘리먼트 객체(없으면 저장된 엘리먼트 객체 사용)

```js
var dm = new ADataMask(this.label.element, this.label);
dm.insertMaskFunc(ADataMask.Number.money.func);
console.log(dm.mask(12345)); //12,345
console.log(dm.unmask()); //12345
```

<br/>

### updateMaskFunc( func, param, inx )

특정 위치의 마스킹 함수와 파라미터를 변경한다.

* `func` \<function> 마스킹 함수
* `param` \<Array> 마스킹 함수에 전달할 파라미터 배열
* `inx` \<Number> 함수 위치값

```js
var dm = new ADataMask(this.label.element, this.label);
dm.insertMaskFunc(ADataMask.Number.money.func);
dm.insertMaskFunc(ADataMask.Number.toFixed.func, [2], 0);
dm.updateMaskFunc(ADataMask.Number.abs.func, null, 0);
console.log(dm.mask(-12345)); //12345
```

<br/>

<!-- 

### resetElement()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setOriginal()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getOriginal()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### ADataMask.setQueryData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### ADataMask.getQueryData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### ADataMask.clearQueryData()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>



 -->


