# AAccordion
**Extends**: [`AComponent`](AComponent.html#acomponent)

특정 구조(p,div)로 된 태그 정보를 파라미터로 받아 accordion 메뉴를 구성한다.

<br/>

## Properties


### downcss \<Object>

Accordion의 아이템이 열린상태의 화살표의 css변수이다.

<br/>

### menuHeight \<Number>

Accordion의 상단메뉴 영역의 높이를 가지고 있는 변수이다.

<br/>

### paddingX \<Number>

AAccordion의 상단 메뉴영역의 좌우 padding값을 가지고 있는 변수이다.

<br/>

### paddingY \<Number>

AAccordion의 상단 메뉴영역의 상하 padding값을 가지고 있는 변수이다.

<br/>

### selectedItem \<Number>

현재 컨텐츠가 보여지고 있는 Item Element변수이다.

<br/>

### upcss \<Object>

Accordion의 아이템이 닫힌상태의 화살표의 css변수이다.

<br/>
<br/>

## Instance Methods

### getItemByIndex( index )

특정 인덱스의 아이템을 리턴한다.

- `index` \<Number> 인덱스

<br/>

### getItemByName( name )

특정 이름의 아이템을 리턴한다.

- `name` \<String> 이름

<br/>

### getItemCount()

아이템의 갯수를 리턴한다.

- **Returns** \<Number>

<br/>

### getItems()

모든 아이템을 리턴한다.

- **Returns** \<JQuery Object>

<br/>

### insertItem( menuText, url, isOpenLoad )

url뷰의 Item을 생성하여 Accordion에 삽입한다.

- `menuText` \<String> 메뉴 텍스트
- `url` \<String> 아이템뷰의 URL
- `isOpenLoad` \<String> 로드하여 오픈할것인지 여부

```js
aaccordion.insertItem('타이틀', 'view/item.lay');
```

<br/>

### removeAllItems()

모든 아이템을 삭제한다.

<br/>

### setAccordionOption( option )

아코디언 옵션을 설정한다.

 - `option` \<Object> 옵션

```js
accordion.setOption({
	showContent: false,			//아코디언 메뉴 추가시점에 바로 컨텐츠가 보여질지 여부
	speed: 'fast',				//에니메이션 속도
	isSingleShow: true,			//하나의 메뉴만 펼칠지
	isAnimation: true,
	isShowToggle: true,			//펼쳐진 항목 다시 클릭시 숨길지
	showEvent: 'click',			//bind event name
	mouseOverEventDelay: 0,
	
	beforeShow: null,
	afterShow: null,
	beforeHide: null,
	afterHide: null,
	//isMobile: false
});
```

<br/>

### setMenuDownIcon( downIcon )

DOWN아이콘을 설정한다. <br><br> ※ 주의 : 해당 함수는 insertItem함수를 호출하기 이전에 호출해야 한다.

- `downIcon` \<String> 아이콘의 URL

```js
accordion.setMenuUpIcon('asset/icon/down.png');
```

<br/>

### setMenuPadding( paddingX, paddingY )

제목부분의 패딩을 설정한다. 이 함수는 insertItem을 호출하기 전에 호출되어야 정상작동한다.

- `paddingX` \<Number> X축 패딩
- `paddingY` \<Number> Y축 패딩

```js
accordion.setMenuPadding(10, 20);
//10% 나 10px을 넣으면 안됨.
```

<br/>

### setMenuTooltip( item, msg)

특정 아이템의 툴팁을 변경한다.

- `item` \<jQuery Object> 아이템
- `msg` \<String> 변경 할 툴팁

```js
var item = aaccordion.getItemByIndex(0);
accordion.setMenuTooltip(item, '새로운 툴팁');
```

<br/>

### setMenuUpIcon( upIcon )

UP아이콘을 설정한다. <br><br> ※ 주의 : 해당 함수는 insertItem함수를 호출하기 이전에 호출해야 한다.

- `upIcon` \<String> 아이콘의 URL

```js
accordion.setMenuUpIcon('asset/icon/up.png');
```

<br/>

### showHideByIndex( index, isAnimation )

특정 인덱스의 아이템을 토글로 보여주거나 숨긴다.

- `index` \<String> 인덱스
- `isAnimation` \<String> 애니메이션 여부

```js
aaccordion.showHideByIndex(1, true);
```

<br/>

### showHideByName( name, isAnimation )

특정 이름의 아이템을 토글로 보여주거나 숨긴다.

- `name` \<String> 이름
- `isAnimation` \<String> 애니메이션 여부

```js
aacordion.showHideByName('타이틀',true);
```

<br/>

### showHideManage( selItem )

특정 아이템을 토글로 보여주거나 숨긴다.

- `selItem` \<String> 파라미터 selItem 은 클릭되어진 메뉴의 상위 item Element 이다.

```js
var item = aaccordion.insertItem('title','view/item.lay');
aaccordion.showHideManage(item);
```

<br/>
<br/>

## Events

공통부분은 설명은 \<[AComponent Events](AComponent.html#events)> 참조

### select( comp, info, e )

아코디언이 선택 될 때 호출된다.

- `info` \<jQuery Object> 아이템 객체

<br/>

