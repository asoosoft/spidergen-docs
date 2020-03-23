# AFlexLayout
> **Extends**: `ALayout`

AFlexLayout

<br/>

## Methods

### eachChild( callback, isReverse )

flexLayout의 모든 컴포넌트를 callback으로 반환한다.

* **Parameters**: 
	* **`callback`** {String} callback
	* **`isReverse`** {String} 역순 여부

* **Usage**: 
```js
flexLayout.eachChild(function(acomp){
                console.log(acomp);
}, true);
```

<br/>

### getAllLayoutComps()

모든 컴포넌트의 객체가 담긴 배열을 리턴한다.

* **Returns**: Array

* **Usage**: 
```js
var resultArr = flexLayout.getAllLayoutComps();
```

<br/>

### getCompIndex()

해당 컴포넌트의 위치값을 리턴한다.

* **Returns**: number

* **Usage**: 
```js
var result = flexLayout.getCompIndex(comp);
```

<br/>

### getFlexAlign( index )

레이아웃의 해당 순번에 있는 아이템의 align-self css value값을 리턴한다.

* **Returns**: String

* **Parameters**: 
	* **`index`** {Number} 순번

* **Usage**: 
```js
var result = flexLayout.getFlexAlign(1);
```

<br/>

### getFlexBasis( index )

레이아웃의 해당 순번에 있는 아이템의 flex-basis css value값을 리턴한다. flex-basis는 아이템의 기본 크기 값이고 auto가 기본값이다.

* **Returns**: String

* **Parameters**: 
	* **`index`** {Number} 순번

* **Usage**: 
```js
var result = flexLayout.getFlexBasis(1);
```

<br/>

### getFlexGrow( index )

레이아웃의 해당 순번에 있는 아이템의 flex-grow값을 받아온다.

* **Parameters**: 
	* **`index`** {Number} 순번

* **Usage**: 
```js
var result = flexLayout.getFlexGrow();
```

<br/>

### getFlexOrder( index )

파라미터로 받은 순번의 order값을 가져온다. order 속성은 flex item의 배치 순서를 제어하는 속성이다. 기본값은 ‘0‘이며 flex-direction 속성의 방향값(row, row-reverse, column, column-reverse)을 기준으로 낮은 숫자를 먼저 배치하고 높은 숫자를 나중에 배치한다.

* **Returns**: number

* **Parameters**: 
	* **`index`** {Number} 순번

* **Usage**: 
```js
var result = flexLayout.getFlexOrder(2);
```

<br/>

### getFlexShrink( index )

레이아웃의 해당 순번에 있는 아이템의 flex-shrink를 리턴한다. flex-shrink은 레이아웃의 item들이 차지할 너비들에 대한 감소형 숫자를 지정한다.

* **Returns**: number

* **Parameters**: 
	* **`index`** {Number} 순번

* **Usage**: 
```js
var result = flexLayout.getFlexShrink();
```

<br/>

### getFlexStringVal( index, valType )

파라미터를 이용하여 flex 해당 순번의 css 값을 리턴한다.

* **Returns**: String

* **Parameters**: 
	* **`index`** {String} index
	* **`valType`** {String} 키값

* **Usage**: 
```js
var result = flexLayout.getFlexStringVal(1, 'left');
```

<br/>

### getFlexVal( index, valType )

파라미터를 이용하여 flex 해당 순번의 css 값을 int형으로 리턴한다.

* **Returns**: int

* **Parameters**: 
	* **`index`** {String} index
	* **`valType`** {String} 키값

* **Usage**: 
```js
var result = flexLayout.getFlexVal(1,'left');
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {String} context 에 매핑된 이벤트 수신자

* **Usage**: 
```js
var flexLayout = new AFlexLayout();
flexLayout.init();
```

<br/>

### initLayoutComp( evtListener )

요소를 자유자재로 위치시키는 flex레이아웃 컴포넌트를 생성한다.

* **Parameters**: 
	* **`evtListener`** {String} context 에 매핑된 이벤트 수신자

* **Usage**: 
```js
flexLayout.initLayoutComp(evtListener);
```

<br/>

### layComponent( acomp, inx, flexGrow )

컴포넌트를 inx(인덱스)의 컴포넌트 앞에 추가한다.

* **Returns**: HTML Object

* **Parameters**: 
	* **`acomp`** {String} 컴포넌트
	* **`inx`** {Number} 어떤 컴포넌트 index
	* **`flexGrow`** {String} 컴포넌트들이 차지할 너비들에 대한 증가형 숫자를 지정 (flex-grow css값)

* **Usage**: 
```js
var btn = new AButton(); // 버튼컴포넌트
btn.init();
var item = flexLayout.layComponent(btn, 2, 1);
```

<br/>

### setFlexAlign( index, alignSelf )

레이아웃의 해당 순번에 있는 아이템의 align-self css value값을 지정한다.

* **Parameters**: 
	* **`index`** {Number} 순번
	* **`alignSelf`** {String} align-self css value값 (auto, center, stretch initial .....)

* **Usage**: 
```js
//레이아웃의 1번째 index에 있는 아이템의 align-self값을 center로 지정
flexLayout.setFlexAlign(1, 'center');
```

<br/>

### setFlexBasis( index, flexBasis )

레이아웃의 해당 순번에 있는 아이템의 flex-basis css value값을 지정한다. flex-basis는 아이템의 기본 크기 값이고 auto가 기본값이다.

* **Parameters**: 
	* **`index`** {Number} 순번
	* **`flexBasis`** {String} flex-basis css value값

* **Usage**: 
```js
//레아이웃의 0번째 index의 아이템의 flex-basis css value값을 10px로 지정한다.
//value의 단위는 px, em, rem, % 모두 사용 가능하고 단위를 생략하면 자동으로 px로 지정되서 사용된다.
flexLayout.setFlexBasis(0, 10);
```

<br/>

### setFlexGrow( index, flexGrow )

해당 순번의 아이템의 flex-grow를 지정한다.

* **Parameters**: 
	* **`index`** {String} 순번
	* **`flexGrow`** {String} flex-grow css(item의 크기 비율)

* **Usage**: 
```js
//레이아웃의 아이템이 3개 있다고 가정하고
//순서대로 1:1:2의 크기로 비율을 지정하고싶을떄 다음과 같이 사용한다.
flexLayout.setFlexGrow(0,1);
flexLayout.setFlexGrow(1,1);
flexLayout.setFlexGrow(2,1);
```

<br/>

### setFlexOrder( index, flexOrder )

레이아웃의 해당 순번에 있는 아이템의 order를 지정한다. order 속성은 flex item의 배치 순서를 제어하는 속성이다. 기본값은 ‘0‘이며 flex-direction 속성의 방향값(row, row-reverse, column, column-reverse)을 기준으로 낮은 숫자를 먼저 배치하고 높은 숫자를 나중에 배치한다.

* **Parameters**: 
	* **`index`** {Number} 순번
	* **`flexOrder`** {Number} order css value값

* **Usage**: 
```js
//0번 째 index의 아이템의 order 속성을 1로 지정함
flexLayout.setFlexOrder(0,1);
```

<br/>

### setFlexShrink( index, flexShrink )

레이아웃의 해당 순번에 있는 아이템의 flex-shrink를 지정한다. flex-shrink은 레이아웃의 item들이 차지할 너비들에 대한 감소형 숫자를 지정한다.

* **Parameters**: 
	* **`index`** {Number} 순번
	* **`flexShrink`** {Number} flex-shrink css value값

* **Usage**: 
```js
//레이아웃의 0번째 index에 있는 아이템의 flex-shrink값을 2로 지정한다.
flexLayout.setFlexShrink(0, 2);
```

<br/>

### setFlexVal( index, valType, val )

파라미터를 이용해서 flex 해당 순번의 css를 지정한다.

* **Parameters**: 
	* **`index`** {String} index
	* **`valType`** {String} css 키
	* **`val`** {String} css 값

* **Usage**: 
```js
flexLayout.setFlexVal(1, 'left','100px');
```

<br/>

### copyFlexProperty()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### copyItemProperty()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### indexOfItem()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getItem()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getItemComp()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### removeAllItems()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### refreshFlexLayout()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setFlexPadding()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setFlexMargin()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getFlexMargin()



* **Parameters**: 

* **Usage**: 
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
