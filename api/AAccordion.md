# AAccordion
> **Extends**: `AComponent`

특정 구조(p,div)로 된 태그 정보를 파라미터로 받아 accordion 메뉴를 구성한다.

<br/>

## Properties


### downcss

Accordion의 아이템이 열린상태의 화살표의 css변수이다.

* **Type**: `Object`
* **Default**: 

<br/>

### menuHeight

Accordion의 상단메뉴 영역의 높이를 가지고 있는 변수이다.

* **Type**: `Number`
* **Default**: 

<br/>

### paddingX

AAccordion의 상단 메뉴영역의 좌우 padding값을 가지고 있는 변수이다.

* **Type**: `Number`
* **Default**: 

<br/>

### paddingY

AAccordion의 상단 메뉴영역의 상하 padding값을 가지고 있는 변수이다.

* **Type**: `Number`
* **Default**: 

<br/>

### selectedItem

현재 컨텐츠가 보여지고 있는 Item Element변수이다.

* **Type**: `Object`
* **Default**: 

<br/>

### upcss

Accordion의 아이템이 닫힌상태의 화살표의 css변수이다.

* **Type**: `Object`
* **Default**: 

<br/>
<br/>

## Methods

### createItem( menuText, url, isOpenLoad )

아코디언에 삽입될 아이템을 생성한다. <br><br> ※주의 : createItem은 Item을 생성만 하고 실제로 삽입하지 않기 떄문에 이 함수를 사용하지 않고 insertItem함수를 사용 해야한다.

* **Parameters**: 
	* **`menuText`** {String} 메뉴 텍스트
	* **`url`** {String} URL
	* **`isOpenLoad`** {String} 로드하여 오픈할것인지 여부

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다. <br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {String} context 에 매핑된 이벤트 수신자

* **Usage**: 
```js
var accordion = new AAccordion();
accordion.init();
```

<br/>

### insertItem( menuText, url, isOpenLoad )

내부적으로 createItem함수를 호출한 뒤에 생성된 Item을 Accordion에 삽입한다.

* **Parameters**: 
	* **`menuText`** {String} 메뉴 텍스트
	* **`url`** {String} 아이템뷰의 URL
	* **`isOpenLoad`** {String} 로드하여 오픈할것인지 여부

* **Usage**: 
```js
aaccordion.insertItem('타이틀', 'view/item.lay');
```

<br/>

### setMenuPadding( paddingX, paddingY )

제목부분의 패딩을 설정한다. 이 함수는 insertItem을 호출하기 전에 호출되어야 정상작동한다.

* **Parameters**: 
	* **`paddingX`** {Number} X축 패딩
	* **`paddingY`** {Number} Y축 패딩

* **Usage**: 
```js
accordion.setMenuPadding(10, 20);
//10% 나 10px을 넣으면 안됨.
```

<br/>

### setMenuUpIcon( upIcon )

UP아이콘을 설정한다. <br><br> ※ 주의 : 해당 함수는 insertItem함수를 호출하기 이전에 호출해야 한다.

* **Parameters**: 
	* **`upIcon`** {String} 아이콘의 URL

* **Usage**: 
```js
accordion.setMenuUpIcon('asset/icon/up.png');
```

<br/>

### showHideByIndex( index, isAnimation )

특정 인덱스의 아이템을 토글로 보여주거나 숨긴다.

* **Parameters**: 
	* **`index`** {String} 인덱스
	* **`isAnimation`** {String} 애니메이션 여부

* **Usage**: 
```js
aaccordion.showHideByIndex(1, true);
```

<br/>

### showHideByName( name, isAnimation )

특정 이름의 아이템을 토글로 보여주거나 숨긴다.

* **Parameters**: 
	* **`name`** {String} 이름
	* **`isAnimation`** {String} 애니메이션 여부

* **Usage**: 
```js
aacordion.showHideByName('타이틀',true);
```

<br/>

### showHideManage( selItem )

특정 아이템을 토글로 보여주거나 숨긴다.

* **Parameters**: 
	* **`selItem`** {String} 파라미터 selItem 은 클릭되어진 메뉴의 상위 item Element 이다.

* **Usage**: 
```js
var item = this.aaccordion.insertItem('title','view/item.lay');
this.aaccordion.showHideManage(item);
```

<br/>

### getItems()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getItemByIndex()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getItemByName()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getItemCount()



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

### setMenuTooltip()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>
## Events


### select( comp, info, e )

아코디언이 선택 될 때 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {jQuery Object} 아이템 객체
	* **`e`** {Object} 이벤트 정보

<br/>

