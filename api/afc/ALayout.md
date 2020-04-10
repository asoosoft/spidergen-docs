# ALayout
> **Extends**: `AComponent`

ALayout

<br/>

## Methods

### getMappingCount()

매핑가능한 갯수를 반환합니다.

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채웁니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {String} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {String} [ key1, key3, key10 ]
	* **`queryData`** {String} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### removeFromView()

부모뷰로 부터 레이아웃 컴포넌트를 제거한다.

* **Usage**: 
```js
layoutComponent.removeFromView();
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {String} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {String} [ key1, key3, key10 ]
	* **`queryData`** {String} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setParent()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getAllLayoutComps()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### eachChild()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### updatePosition()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### changeCompIdPrefix()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getDroppable()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### callSubActiveEvent()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### reset()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>
