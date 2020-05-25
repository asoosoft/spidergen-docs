# AMenu( rootMenu, menuId, iconMap )
> **Extends**: [`AFloat`](./AFloat.md)

* `rootMenu` \<[AMenu](#amenu-rootmenu-menuid-iconmap)> 루트 메뉴 컴포넌트
* `menuId` \<String> 메뉴 아이디
* `iconMap` \<String> 아이콘 URL 또는 CSS

메뉴를 표현하는 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

### rootMenu \<[AMenu](#amenu-rootmenu-menuid-iconmap)>

현재 메뉴가 소메뉴인 경우에 세팅하는 최상단 메뉴 컴포넌트

<br/>
<br/>

## Class Methods

### AMenu.setOverStyle( overStyle )

모든 AMenu 컴포넌트에 동일 적용되는 마우스 오버 CSS 를 지정한다.

* `overStyle` \<String> CSS

## Instance Methods

### insertItemInfo( itemInfo, index )

메뉴에 아이템정보를 특정위치에 추가 한다.

* `itemInfo` \<Object> 아이템 정보
* `index` \<Number> 인덱스

```js
var menu = new AMenu(null, 0, 'Source/img/menu_icon.png');
//2번째에 다음과 같은 메뉴아이템 정보를 넣는다
menu.insertItemInfo({ text:'Open File...', icon:'', sub: itemInfoArr }, 2);
```

<br/>

### setIconMap( iconMap )

아이콘 이미지 URL 또는 CSS 를 세팅한다.

* `iconMap` \<String> 아이콘 URL 또는 CSS

```js
menu.setIconMap('../path/icon.png');
```

<br/>

### setItemInfo( itemInfo, index )

메뉴 아이템을 교체한다.

* `itemInfo` \<Object> 아이템정보 객체
* `index` \<Number> 인덱스

```js
var menu = new AMenu(null, 0, 'Source/img/menu_icon.png');
//2번째 메뉴아이템 정보를 다음과 같이 교체한다.
menu.setItemInfo({ text:'Open File...', icon:'', sub: itemInfoArr }, 2);
```

<br/>

### setItemInfoArr()

메뉴 아이템에 메뉴정보 배열을 설정한다.

```js
var menuInfo = [
　{text:'Cut', id:'CUT_COMP', icon:0, iconMapUrl: 'Source/img/cut.png'},
　{text:'Copy', id:'COPY_COMP', icon:0, iconMapUrl: 'Source/img/page_white_copy.png'},
　{text:'Paste', id:'PASTE_COMP', icon:0, iconMapUrl: 'Source/img/page_white_paste.png'},
　{text:'-----------------------------', id:'MENU_SPLITTER'},
　{text:'Delete', id:'DELETE_COMP', icon:0, iconMapUrl: 'Source/img/page_white_delete.png'}
];
var menu = new AMenu(null, 0, 'Source/img/menu_icon.png');
menu.setItemInfoArr(menuInfo);
```

<br/>

### setOverStyle( overStyle )

마우스 오버 CSS Selector 를 지정한다.

* `overStyle` \<String> CSS Selector

<br/>

### setResultListener( listener )

메뉴가 선택되었을 때 수신받을 리스너 객체를 지정한다. 리스너 객체에 정의된 onMenuResult( amenu, info, e ) 함수를 호출해준다.

* `listener` \<Object> 리스너 객체

```js
function MainView*onBtnClick(comp, info, e)
{
	//메뉴 아이템정보는 다음과 같은 방식으로 작성
	var menuInfo = [
	{text:'Cut', id:'CUT_COMP', icon:0, iconMapUrl: 'Source/img/cut.png'},
	{text:'Copy', id:'COPY_COMP', icon:0, iconMapUrl: 'Source/img/page_white_copy.png'},
	{text:'Paste', id:'PASTE_COMP', icon:0, iconMapUrl: 'Source/img/page_white_paste.png'},
	{text:'-----------------------------', id:'MENU_SPLITTER'},
	{text:'Delete', id:'DELETE_COMP', icon:0, iconMapUrl: 'Source/img/page_white_delete.png'}
	];
	//메뉴 객체 생성
	var menu = new AMenu(null, 0, 'Source/img/menu_icon.png');
	//메뉴 이벤트 리스너 등록
	menu.setResultListener(this);
	//메뉴 아이템정보 세팅
	menu.setItemInfoArr(menuInfo);
	//메뉴팝업 ( 메뉴는 통상적으로 우클릭할때 띄우는데 e는 클릭이벤트의 이벤트정보를 가르킨다.)
	menu.popupEx({ 'left': e.pageX+1, 'top': e.pageY+1});
};

function MainView*onMenuResult(amenu, info, e)
{
	alert(info.text + '/' + info.id);
};
```

<br/>
<br/>