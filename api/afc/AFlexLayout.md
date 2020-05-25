# AFlexLayout
**Extends** [`ALayout`](ALayout.html#ALayout)

화면의 크기와 컴포넌트의 크기에 따라 유동적인 레이아웃을 형성 할 수 있는 레이아웃 컴포넌트

<br/>

## Instance Methods

### eachChild( callback, isReverse )

레이아웃 컴포넌트 내의 모든 컴포넌트를 callback으로 반환한다.

- `callback` \<function> callback 함수 
- `isReverse` \<Bool> 역순 여부

```js

//레이아웃 컴포넌트 ID가 flexLayout
this.flexLayout.eachChild(function(acomp){
    console.log(acomp); //컴포넌트
}, true);

```

<br/>

### getAllLayoutComps()

레이아웃 컴포넌트 내에 배치된 모든 컴포넌트 객체를 배열로 리턴한다.

**Returns** \<Array> 컴포넌트 배열

```js

//레이아웃 컴포넌트 ID가 flexLayout
var resultArr = this.flexLayout.getAllLayoutComps();

console.log(resultArr); // [AButton, AButton]

```

<br/>

### getCompIndex( acomp )

레이아웃 컴포넌트 내에 파라미터 acomp 컴포넌트의 위치 정보를 리턴한다.

- `acomp` \<AComponent> 정보를 원하는 컴포넌트

- **Returns** \<Number> 위치 순번 (존재하지 않으면 -1)

```js

//레이아웃 컴포넌트 ID : flexLayout
//레이아웃 컴포넌트 내에 3개 버튼 존재 ID는 각각 : btn1, btn2, btn3 
var result = this.flexLayout.getCompIndex(this.btn2);
console.log(result); // 1

```

<br/>

### getFlexAlign( index )

레이아웃 컴포넌트의 index 순번에 있는 아이템의 align-self css value값을 리턴한다.

- `index` \<Number> 순번

- **Returns** \<String> align-self css 값

```js

//레이아웃 컴포넌트 ID : flexLayout
var result = this.flexLayout.getFlexAlign(1);
console.log(result); // auto

```

<br/>

### getFlexBasis( index )

레이아웃 컴포넌트의 index 순번에 있는 아이템의 flex-basis css value값을 리턴한다. flex-basis는 아이템의 기본 크기를 설정한다.

- `index` \<Number> 순번

- **Returns** \<String> flex-basis css 값

```js

//레이아웃 컴포넌트 ID : flexLayout
var result = this.flexLayout.getFlexBasis(1);
console.log(result); //auto

```

<br/>

### getFlexGrow( index )

레이아웃 컴포넌트의 index 순번에 있는 아이템의 flex-grow css 값을 리턴한다. flex-grow는 flex-item 요소가, flex-container 요소 내부에서 할당 가능한 공간의 정도를 설정한다.

- `index` \<Number> 순번

- **Returns** \<String> flex-grow css 값

```js

//레이아웃 컴포넌트 ID : flexLayout
var result = this.flexLayout.getFlexGrow(0);
console.log(result); // 1

```

<br/>

### getFlexOrder( index )

레이아웃 컴포넌트의 index 순번의 order값을 리턴한다. order 속성은 flex item의 배치 순서를 제어하는 속성이다. 기본값은 ‘0‘이며 flex-direction 속성의 방향값(row, row-reverse, column, column-reverse)을 기준으로 낮은 숫자를 먼저 배치하고 높은 숫자를 나중에 배치한다.

- `index` \<Number> 순번

- **Returns** \<Number> flex order 값

```js

//레이아웃 컴포넌트 ID : flexLayout
//버튼의 flex order 값이 각각 1, 2로 설정 되었을 경우
var result = this.flexLayout.getFlexOrder(1);
console.log(result); // 2

```

<br/>

### getFlexShrink( index )

레이아웃 컴포넌트의 index 순번에 있는 아이템의 flex-shrink 값을 리턴한다. flex-shrink은 flex-item 요소의 크기가 flex-container 요소의 크기보다 클 때 flex-shrink 속성을 사용한다. 설정된 숫자값에 따라 flex-container 요소 내부에서 flex-item 요소의 크기가 축소된다.

- `index` \<Number> 순번

- **Returns** \<Number> flex-shrink 값

```js

//레이아웃 컴포넌트 ID : flexLayout
var result = this.flexLayout.getFlexShrink();
console.log(result); // 1 

```

<br/>

### getFlexStringVal( index, valType )

파라미터를 이용하여 index 순번에 아이템의 valType 명의 flex css 값을 리턴한다.

- `index` \<String> 순번
- `valType` \<String> 키값

- **Returns** \<String>

```js
//레이아웃 컴포넌트 ID : flexLayout
var result = this.flexLayout.getFlexStringVal(1, 'left');
console.log(result); // 0px
```

<br/>

### getFlexVal( index, valType )

파라미터를 이용하여 index 순번의 flex css 값을 int형으로 리턴한다.

- `index` \<String> index
- `valType` \<String> 키값

- **Returns** \<int>

```js
//레이아웃 컴포넌트 ID : flexLayout
var result = flexLayout.getFlexVal(1, 'left');
console.log(result); // 0px
```

<br/>

### getFlexPadding( index )

레이아웃 컴포넌트의 index 번째 아이템의 padding 값을 리턴한다.

- `index` \<Number> 순번

- **Returns** \<String> padding 값

```js 
//레이아웃 컴포넌트 ID : flexLayout
//레이아웃 컴포넌트 내에 bt1, bt2 버튼이 존재한다.
var result = this.flexLayout.getFlexPadding(0);
console.log(result);// 0px
```

<br/>


### getFlexMargin( index )

레이아웃 컴포넌트의 index 번째 아이템의 margin 값을 리턴한다.

- `index` \<Number> 순번

- **Returns** \<String> margin 값

```js 
//레이아웃 컴포넌트 ID : flexLayout
//레이아웃 컴포넌트 내에 bt1, bt2 버튼이 존재한다.
var result = this.flexLayout.getFlexMargin(0);
console.log(result);// 0px
```


<br/>

### _init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

 - `context` \<String> 컴포넌트 생성 및 초기화 정보
 - `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var flexLayout = new AFlexLayout();
flexLayout.init();
```

<br/>

### _initLayoutComp( evtListener )

요소를 자유자재로 위치 시키는 flex레이아웃 컴포넌트를 생성한다.

- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
flexLayout.initLayoutComp(evtListener);
```

<br/>

### layComponent( acomp, inx, flexGrow )

컴포넌트를 inx 순번의 컴포넌트 앞에 추가한다.

- `acomp` \<String> 컴포넌트
- `inx` \<Number> 어떤 컴포넌트 index
- `flexGrow` \<String> 컴포넌트들이 차지할 너비들에 대한 증가형 숫자를 지정 (flex-grow css값)

- **Returns** \<HTML Object>

```js
//컴포넌트 ID가 flexLayout 일경우
var btn = new AButton(); // 버튼컴포넌트
btn.init();
var item = this.flexLayout.layComponent(btn, 2, 1);
```

<br/>

### setFlexAlign( index, alignSelf )

레이아웃의 해당 순번에 있는 아이템의 align-self css value값을 지정한다.

- `index` \<Number> 순번
- `alignSelf` \<String> align-self css value값 (auto, center, stretch initial .....)

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃의 1번째 index에 있는 아이템의 align-self값을 center로 지정
this.flexLayout.setFlexAlign(1, 'center');
```

<br/>

### setFlexBasis( index, flexBasis )

레이아웃의 해당 순번에 있는 아이템의 flex-basis css value값을 지정한다. flex-basis는 아이템의 기본 크기 값이고 auto가 기본값이다.

- `index` \<Number> 순번
- `flexBasis` \<String> flex-basis css value값

```js
//컴포넌트 ID가 flexLayout 일경우 
//레아이웃의 0번째 아이템의 flex-basis css value값을 10px로 지정한다.
//value의 단위는 px, em, rem, % 모두 사용 가능.
this.flexLayout.setFlexBasis(0, 10);
```

<br/>

### setFlexGrow( index, flexGrow )

해당 순번의 아이템의 flex-grow를 지정한다.

- `index` \<String> 순번
- `flexGrow` \<String> flex-grow css(item의 크기 비율)

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃의 아이템이 3개 있다고 가정하고
//순서대로 1:1:2의 크기로 비율을 지정하고싶을떄 다음과 같이 사용한다.
this.flexLayout.setFlexGrow(0,1);
this.flexLayout.setFlexGrow(1,1);
this.flexLayout.setFlexGrow(2,1);
```

<br/>

### setFlexOrder( index, flexOrder )

레이아웃의 해당 순번에 있는 아이템의 order를 지정한다. order 속성은 flex item의 배치 순서를 제어하는 속성이다. 기본값은 ‘0‘이며 flex-direction 속성의 방향값(row, row-reverse, column, column-reverse)을 기준으로 낮은 숫자를 먼저 배치하고 높은 숫자를 나중에 배치한다.

- `index` \<Number> 순번
- `flexOrder` \<Number> order css value값

```js
//컴포넌트 ID가 flexLayout 일경우
//0번 째 index의 아이템의 order 속성을 1로 지정함
this.flexLayout.setFlexOrder(0,1);
```

<br/>

### setFlexShrink( index, flexShrink )

레이아웃의 해당 순번에 있는 아이템의 flex-shrink를 지정한다. flex-shrink은 레이아웃의 item들이 차지할 너비들에 대한 감소형 숫자를 지정한다.

- `index` \<Number> 순번
- `flexShrink` \<Number> flex-shrink css value값

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃의 0번째 index에 있는 아이템의 flex-shrink값을 2로 지정한다.
this.flexLayout.setFlexShrink(0, 2);
```

<br/>

### setFlexVal( index, valType, val )

index 순번째의 아이템의 valType 명의 css 속성값을 val로 설정한다.

- `index` \<String> 순번
- `valType` \<String> css 속성명
- `val` \<String> css 값

```js
//컴포넌트 ID가 flexLayout 일경우
this.flexLayout.setFlexVal(0, 'left','100px');
```

<br/>

### _copyFlexProperty( srcComp )

파라미터 srcComp 객체의 flex 프로퍼티 값을 복사한다.

- `srcComp` \<AComponent> 컴포넌트 객체

<br/>

### _copyItemProperty( srcComp, inx)

파라미터 srcComp 객체의 flex 프로퍼티 값을 inx 번째 객체에 복사한다.

- `srcComp` \<AComponent> 컴포넌트 객체
- `inx` \<Number> 순번

<br/>


### indexOfItem( item )

레이아웃 컴포넌트 내의 item 순번을 리턴한다.

- `item` \<JQuery Object> 아이템

- **Returns** \<Number> 아이템 순번

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃 컴포넌트 내에 버튼 bt1, bt2 순으로 존재 할 경우
var item = this.bt1.$ele.parent();
var result = this.flexLayout.indexOfItem(item);
console.log(result); // 0
```

<br/>


### getItem( inx )

레이아웃 컴포넌트 내에 inx 번째 아이템을 리턴한다.

- `inx` \<Number> 순번

- **Returns** \<JQuery Object> 아이템 객체

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃 컴포넌트 내에 버튼 bt1, bt2 순으로 존재 할 경우
var result = this.flexLayout.getItem(0);
console.log(result); //jQuery.fn.init [div, prevObject: jQuery.fn.init(2)]
```

<br/>


### getItemComp( inx )

레이아웃 컴포넌트 내에 inx 번째 컴포넌트를 리턴한다.

- `inx` \<Number> 순번

- **Returns** \<AComponent> 컴포넌트

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃 컴포넌트 내에 버튼 bt1, bt2 순으로 존재 할 경우
var result = this.flexLayout.getItemComp(1);
console.log(result);    // AButton{element:button ... }
console.log(result.getComponentId()); // bt2
```

<br/>


### removeAllItems()

레이아웃 컴포넌트 내의 모든 아이템을 삭제한다.

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃 컴포넌트 내에 버튼 bt1, bt2 순으로 존재 할 경우
console.log(this.flexLayout.getAllLayoutComps()); //(2) [AButton, AButton]
var result = this.flexLayout.removeAllItems();
console.log(this.flexLayout.getAllLayoutComps()); //[]
```

<br/>


### refreshFlexLayout()

레이아웃 컴포넌트 내의 아이템들을 갱신 합니다.

```js
//컴포넌트 ID가 flexLayout 일경우
this.flexLayout.refreshFlexLayout();
```

<br/>


### setFlexPadding( index, padding )

레이아웃 컴포넌트의 index 번째 아이템에 padding 값을 설정한다.

- `index` \<Number> 순번

- `padding` \<String> padding 값

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃 컴포넌트 내에 버튼 bt1, bt2 순으로 존재 할 경우
console.log(this.flexLayout.getFlexVal(1, 'padding')); // 0px
this.flexLayout.setFlexPadding(1, '10px');
console.log(this.flexLayout.getFlexVal(1, 'padding')); // 10px
```

<br/>


### setFlexMargin( index, margin )

레이아웃 컴포넌트의 index 번째 아이템에 margine 값을 설정한다.

- `index` \<Number> 순번

- `margin` \<String> margin 값

```js
//컴포넌트 ID가 flexLayout 일경우
//레이아웃 컴포넌트 내에 버튼 bt1, bt2 순으로 존재 할 경우
console.log(this.flexLayout.getFlexVal(1, 'margin')); // 0px
this.flexLayout.setFlexMargin(1, '10px');
console.log(this.flexLayout.getFlexVal(1, 'margin')); // 10px
```

<br/>




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
