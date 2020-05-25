# AFlexLayout
<<<<<<< HEAD
**Extends**: [`ALayout`](ALayout.html#ALayout)
=======
**Extends** `ALayout`
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

유연한 레이아웃을 만들 수 있는 컴포넌트 입니다.

<br/>

## Class Methods

### AFlexLayout.CONTEXT

## Instance Methods

### eachChild( callback, isReverse )

flexLayout 내의 모든 컴포넌트를 순회하면서 callback 함수를 적용한다.

<<<<<<< HEAD
- `callback` \<function> 콜백함수
- `isReverse` \<boolean> 역순여부
=======
- `callback` \<String> callback
- `isReverse` \<String> 역순 여부
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

```js
flexLayout.eachChild(function( acomp ){
	
	acomp.removeFromView(); //레이아웃 내에 모든 컴포넌트를 삭제한다.

}, true);
```

<br/>

### getAllLayoutComps()

flexLayout 내의 모든 컴포넌트 객체를 배열로 리턴한다.

<<<<<<< HEAD
- **Returns** \<Array>

<br/>

### getCompIndex( acomp )

해당 컴포넌트의 위치값을 리턴한다.

- `acomp` \<Component> 컴포넌트

- **Returns** \<Number>
=======
**Returns** \<Array>

```js
var resultArr = flexLayout.getAllLayoutComps();
```

<br/>

### getCompIndex( comp )

해당 컴포넌트의 위치값을 리턴한다.

- `comp` \<AComponent> 값을 원하는 컴포넌트
- **Returns** \<Number>

```js
var result = flexLayout.getCompIndex(comp);
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### getFlexAlign( index )

<<<<<<< HEAD
레이아웃의 해당 순번(index)에 있는 컴포넌트의 align-self value를 리턴한다.

- `index` \<Number> 순번

- **Returns** \<String>
=======
레이아웃의 해당 순번에 있는 아이템의 align-self css value값을 리턴한다.

- `index` \<Number> 순번
- **Returns** \<String>

```js
var result = flexLayout.getFlexAlign(1);
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### getFlexBasis( index )

레이아웃의 해당 순번(index)에 있는 컴포넌트의 flex-basis css value를 리턴한다. 

- `index` \<Number> 순번
<<<<<<< HEAD

- **Returns** \<String>
=======
- **Returns** \<String>

```js
var result = flexLayout.getFlexBasis(1);
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### getFlexGrow( index )

레이아웃의 해당 순번(index)에 있는 컴포넌트의 flex-grow css value를 리턴한다.

- `index` \<Number> 순번

<<<<<<< HEAD
- **Returns** \<String>
=======
```js
var result = flexLayout.getFlexGrow();
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### getFlexOrder( index )

레이아웃의 해당 순번(index)에 있는 컴포넌트의 order css value를 리턴한다. 
order 속성은 flex item의 배치 순서를 제어하는 속성이다. 기본값은 ‘0‘이며 flex-direction 속성의 방향값(row, row-reverse, column, column-reverse)을 기준으로 낮은 숫자를 먼저 배치하고 높은 숫자를 나중에 배치한다.

- `index` \<Number> 순번
<<<<<<< HEAD

- **Returns** \<Number>
=======
- **Returns** \<Number>

```js
var result = flexLayout.getFlexOrder(2);
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### getFlexShrink( index )

<<<<<<< HEAD
레이아웃의 해당 순번에 있는 컴포넌트의 flex-shrink css value를 리턴한다. 
flex-shrink은 레이아웃의 item들이 차지할 너비들에 대한 감소형 숫자를 지정한다.

- `index` \<Number> 순번

- **Returns** \<String>
=======
레이아웃의 해당 순번에 있는 아이템의 flex-shrink를 리턴한다. flex-shrink은 레이아웃의 item들이 차지할 너비들에 대한 감소형 숫자를 지정한다.

- `index` \<Number> 순번
- **Returns** \<Number>

```js
var result = flexLayout.getFlexShrink();
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### getFlexStringVal( index, valType )

레이아웃의 해당 순번의 valType와 속성명이 동일한 flex css value를 리턴한다.

<<<<<<< HEAD
- `index` \<Number> 순번
- `valType` \<String> 속성명

- **Returns** \<String>

=======
- `index` \<String> index
- `valType` \<String> 키값
- **Returns** \<String>

>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4
```js

<<<<<<< HEAD
var result = flexLayout.getFlexStringVal(1, 'align-self');

=======
- `index` \<String> index
- `valType` \<String> 키값
- **Returns** \<int>

```js
var result = flexLayout.getFlexVal(1, 'left');
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4
```

<br/>

### getFlexVal( index, valType )

레이아웃의 해당 순번의 valType와 속성명이 동일한 flex css value를 Number형으로 리턴한다.

<<<<<<< HEAD
- `index` \<Number> 순번
- `valType` \<String> 속성명

- **Returns** \<Number>
=======
 - `context` \<String> 컴포넌트 생성 및 초기화 정보
 - `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var flexLayout = new AFlexLayout();
flexLayout.init();
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### _initLayoutComp( evtListener )

<<<<<<< HEAD
flexLayout 컴포넌트를 생성한다.

- `evtListener` \<String> context에 매핑된 이벤트 수신자 객체
=======
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
flexLayout.initLayoutComp(evtListener);
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### layComponent( acomp, inx, flexGrow )

컴포넌트를 inx(인덱스)의 컴포넌트 앞에 추가한다. inx 값이 없을 경우 뒤에 추가한다.

<<<<<<< HEAD
- `acomp` \<AComponent> 컴포넌트
- `inx` \<Number> 순번
- `flexGrow` \<Number> 컴포넌트들이 차지할 너비들에 대한 증가형 숫자를 지정 (flex-grow css값)

- **Returns** \<JQuery Object>

=======
- `acomp` \<String> 컴포넌트
- `inx` \<Number> 어떤 컴포넌트 index
- `flexGrow` \<String> 컴포넌트들이 차지할 너비들에 대한 증가형 숫자를 지정 (flex-grow css값)
- **Returns** \<HTML Object>

>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4
```js
var btn = new AButton(); // 버튼컴포넌트
btn.init();
var item = flexLayout.layComponent(btn, 2, 1);
```

<br/>

### setFlexAlign( index, alignSelf )

레이아웃의 해당 순번에 있는 컴포넌트의 align-self css value값을 지정한다.

- `index` \<Number> 순번
- `alignSelf` \<String> align-self css value값 (auto, center, stretch initial .....)

```js
//레이아웃의 1번째 index에 있는 아이템의 align-self값을 center로 지정
flexLayout.setFlexAlign(1, 'center');
```

<br/>

### setFlexBasis( index, flexBasis )

레이아웃의 해당 순번에 있는 컴포넌트의 flex-basis css value를 지정한다. 

- `index` \<Number> 순번
<<<<<<< HEAD
- `flexBasis` \<String> flex-basis css value 단위는 px, em, rem, % 사용
=======
- `flexBasis` \<String> flex-basis css value값
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

```js
//레아이웃의 0번째 index의 아이템의 flex-basis css value값을 10px로 지정한다.
//value의 단위는 px, em, rem, % 모두 사용 가능하고 단위를 생략하면 자동으로 px로 지정되서 사용된다.
flexLayout.setFlexBasis(0, '10px');
```

<br/>

### setFlexGrow( index, flexGrow )

레이아웃의 해당 순번의 컴포넌트의 flex-grow를 지정한다.

<<<<<<< HEAD
- `index` \<Number> 순번
- `flexGrow` \<Number> flex-grow css value (순번 컴포넌트의 크기 비율)
=======
- `index` \<String> 순번
- `flexGrow` \<String> flex-grow css(item의 크기 비율)
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

```js
//레이아웃의 아이템이 3개 있다고 가정하고
//순서대로 1:1:2의 크기로 비율을 지정하고싶을떄 다음과 같이 사용한다.
flexLayout.setFlexGrow(0,1);
flexLayout.setFlexGrow(1,1);
flexLayout.setFlexGrow(2,1);
```

<br/>

### setFlexOrder( index, flexOrder )

<<<<<<< HEAD
레이아웃의 해당 순번에 있는 아이템(컴포넌트)의 order를 지정한다.
order 속성은 flex item의 배치 순서를 제어하는 속성이다.
기본값은 ‘0‘이며 flex-direction 속성의 방향값(row, row-reverse, column, column-reverse)을 기준으로 낮은 숫자를 먼저 배치하고 높은 숫자를 나중에 배치한다.

- `index` \<Number> 순번
- `flexOrder` \<Number> order css value값
=======
레이아웃의 해당 순번에 있는 아이템의 order를 지정한다. order 속성은 flex item의 배치 순서를 제어하는 속성이다. 기본값은 ‘0‘이며 flex-direction 속성의 방향값(row, row-reverse, column, column-reverse)을 기준으로 낮은 숫자를 먼저 배치하고 높은 숫자를 나중에 배치한다.

- `index` \<Number> 순번
- `flexOrder` \<Number> order css value값

```js
//0번 째 index의 아이템의 order 속성을 1로 지정함
flexLayout.setFlexOrder(0,1);
```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>

### setFlexShrink( index, flexShrink )

레이아웃의 해당 순번에 있는 아이템(컴포넌트)의 flex-shrink를 지정한다. 
flex-shrink은 레이아웃의 item들이 차지할 너비들에 대한 감소형 숫자를 지정한다.

- `index` \<Number> 순번
- `flexShrink` \<Number> flex-shrink css value값

```js
//레이아웃의 0번째 index에 있는 아이템의 flex-shrink값을 2로 지정한다.
flexLayout.setFlexShrink(0, 2);
```

<br/>

### setFlexVal( index, valType, val )

valType 파라미터를 이용해서 flex 해당 순번의 css를 지정한다.

<<<<<<< HEAD
- `index` \<Number> 순번
- `valType` \<String> css 속성명
- `val` \<String> css value
=======
- `index` \<String> index
- `valType` \<String> css 키
- `val` \<String> css 값
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

```js
flexLayout.setFlexVal(1, 'left','100px');
```

<br/>

<<<<<<< HEAD
### _copyFlexProperty( srcComp )

srcComp 객체의 Flex 속성값을 복사한다.
=======
### copyFlexProperty( srcComp )

- `srcComp` \<>

```js
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

- `srcComp` \<AComponent> 컴포넌트

<br/>


<<<<<<< HEAD
### _copyItemProperty(srcComp, inx)

srcComp 객체의 Flex 속성값을 inx 번째 있는 객체에 복사한다.

- `srcComp` \<AComponent> 컴포넌트
- `inx` \<Number> 순번
=======
### copyItemProperty( srcComp, inx)

- `srcComp` \<>
- `inx` \<>

```js

```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>


### indexOfItem( item )
<<<<<<< HEAD

레이아웃 아이템들중 item 객체(컴포넌트)의 순번을 리턴한다.

- `item` \<AComponent> 컴포넌트

- **Returns** \<Number> 순번
=======

- `item` \<>
- **Returns** \<>

```js

```
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

<br/>


### getItem( inx )

<<<<<<< HEAD
레이아웃의 inx 번째 아이템(컴포넌트)를 리턴한다.

- `inx` \<Number> 순번


* **Usage**: 
=======
- `inx` \<>
- **Returns** \<>

>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4
```js

```

<br/>


<<<<<<< HEAD
### getItemComp( inx)


=======
### getItemComp( inx )
>>>>>>> 0806a57ce407b2d74e8b5d5b2f31c23b3557bec4

- `inx` \<>
- **Returns** \<>

```js

```

<br/>


### removeAllItems()


```js

```

<br/>


### refreshFlexLayout()

```js

```

<br/>


### setFlexPadding( index, padding )

- `index` \<>
- `padding` \<>

```js

```

<br/>


### setFlexMargin( index, margin )

- `index` \<>
- `margin` \<>

```js

```

<br/>


### getFlexMargin( index )

- `index` \<>

```js

```

<br/>
<br/>

## Attribute

### Data

* **Direction:** 자식 요소의 방향성을 설정하는 속성입니다. 
    * **row:** 기본값. 자식 요소의 방향을 수평방향(좌 -> 우)으로 표현합니다. 
    * **row reverse:** 자식 요소의 방향을 수평방향(우 -> 좌)으로 표현합니다. 
    * **column:** 자식 요소의 방향을 수직방향(상 -> 하)으로 표현합니다. 
    * **column reverse:** 자식 요소의 방향을 수직방향(하 -> 상)으로 표현합니다.  

* **Wrap:** 자식 요소의 줄넘김 처리를 설정하는 속성입니다. 
    * **nowrap:** 기본값. 자식 요소를 한줄에 모두 표현합니다. 
    * **wrap:** 자식 요소가 적정 길이보다 길면 다음줄에 표현합니다. 
    * **wrap-reverse:** wrap과 같으나 역방향으로 표현합니다.  

* **Justify Content:** 설명이 필요합니다.
    * **flex-start:** 설명이 필요합니다.
    * **center:** 설명이 필요합니다.
    * **flex-end:** 설명이 필요합니다.
    * **space-between:** 설명이 필요합니다.
    * **space-around:** 설명이 필요합니다.
    * **space-evenly:** 설명이 필요합니다.

* **Align Items:** 설명이 필요합니다.
    * **stretch:** 설명이 필요합니다.
    * **flex-start:** 설명이 필요합니다.
    * **center:** 설명이 필요합니다.
    * **flex-end:** 설명이 필요합니다.
    * **baseline:** 설명이 필요합니다.

* **Align Content:** 설명이 필요합니다.
    * **stretch:** 설명이 필요합니다.
    * **flex-start:** 설명이 필요합니다.
    * **center:** 설명이 필요합니다.
    * **flex-end:** 설명이 필요합니다.
    * **space-between:** 설명이 필요합니다.
    * **space-around:** 설명이 필요합니다.

<br/>
