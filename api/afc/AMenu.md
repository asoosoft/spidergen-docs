# AMenu
> **Extends**: `AFloat`

AMenu

<br/>

## Properties


### $ele



* **Type**: ``
* **Default**: ``

<br/>

### itemInfoArr



* **Type**: ``
* **Default**: ``

<br/>

### selItem



* **Type**: ``
* **Default**: ``

<br/>

### listener



* **Type**: ``
* **Default**: ``

<br/>

### funcName



* **Type**: ``
* **Default**: ``

<br/>

### rootMenu



* **Type**: ``
* **Default**: ``

<br/>

### menuId



* **Type**: ``
* **Default**: ``

<br/>

### iconMap



* **Type**: ``
* **Default**: ``

<br/>

### overClass



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### addMenuItem( itemInfo )

메뉴 태그 정보를 세팅한다. 내부적으로만 사용한다.

* **Parameters**: 
	* **`itemInfo`** {Array} 메뉴 아이템 정보 배열

<br/>

### close()

팝업 메뉴를 닫는다.

<br/>

### init()

AMenu객체를 초기화한다. popup함수에서 호출하므로 직접 호출하지는 않아도 된다.

<br/>

### insertItemInfo( itemInfo, index )

메뉴에 아이템정보를 특정위치에 추가 한다.

* **Parameters**: 
	* **`itemInfo`** {Object} 아이템 정보
	* **`index`** {Number} 인덱스

* **Usage**: 
```js
var menu = new AMenu(null, 0, 'Source/img/menu_icon.png');
//2번째에 다음과 같은 메뉴아이템 정보를 넣는다
menu.insertItemInfo({ text:'Open File...', icon:'', sub: itemInfoArr }, 2);
```

<br/>

### popup( left, top, width, height )

메뉴를 팝업한다. 팝업하기전에 이벤트 등록과 아이템 정보를 세팅해야한다.

* **Parameters**: 
	* **`left`** {Number} left position값
	* **`top`** {Number} top  position값
	* **`width`** {Number} 너비값
	* **`height`** {Number} 높이값

* **Usage**: 
```js
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
//메뉴 이벤트 등록
menu.setSelectListener(this, 'onMenuSelect');
//메뉴 아이템정보 세팅
menu.setItemInfoArr(menuInfo);
//메뉴팝업 ( 메뉴는 통상적으로 우클릭할때 띄우는데 e는 클릭이벤트의 이벤트정보를 가르킨다.)
menu.popup(e.pageX+1, e.pageY+1);
```

<br/>

### popupEx( info )

메뉴 팝업을 띄운다.

* **Parameters**: 
	* **`info`** {Object} 포지션 객체

* **Usage**: 
```js
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
//메뉴 이벤트 등록
menu.setSelectListener(this, 'onMenuSelect');
//메뉴 아이템정보 세팅
menu.setItemInfoArr(menuInfo);
//메뉴팝업 ( 메뉴는 통상적으로 우클릭할때 띄우는데 e는 클릭이벤트의 이벤트정보를 가르킨다.)
menu.popupEx({ 'left': e.pageX+1, 'top': e.pageY+1});
```

<br/>

### reportEvent( item )

reportEvent

* **Parameters**: 
	* **`item`** {String} item

<br/>

### setIconMapUrl()

아이콘 URL을 세팅한다.

* **Usage**: 
```js
menu.setIconMapUrl('../path/icon.png');
```

<br/>

### setItemInfo( itemInfo, index )

메뉴 아이템을 교체한다.

* **Parameters**: 
	* **`itemInfo`** {Object} 아이템정보 객체
	* **`index`** {Number} 인덱스

* **Usage**: 
```js
var menu = new AMenu(null, 0, 'Source/img/menu_icon.png');
//2번째 메뉴아이템 정보를 다음과 같이 교체한다.
menu.setItemInfo({ text:'Open File...', icon:'', sub: itemInfoArr }, 2);
```

<br/>

### setItemInfoArr()

메뉴 아이템에 메뉴정보 배열을 설정한다.

* **Usage**: 
```js
var menuInfo = [
　{text:'Cut', id:'CUT_COMP', icon:0, iconMapUrl: 'Source/img/cut.png'},
　{text:'Copy', id:'COPY_COMP', icon:0, iconMapUrl: 'Source/img/page_white_copy.png'},
　{text:'Paste', id:'PASTE_COMP', icon:0, iconMapUrl: 'Source/img/page_white_paste.png'},
　{text:'-----------------------------', id:'MENU_SPLITTER'},
　{text:'Delete', id:'DELETE_COMP', icon:0, iconMapUrl: 'Source/img/page_white_delete.png'}
];
var menu = new AMenu(null, 0, 'Source/img/menu_icon.png');
menu.setItemInfoArr(menuInfo );
```

<br/>

### setSelectListener( listener, funcName )

메뉴 셀렉트 이벤트 리스너를 설정한다.

* **Parameters**: 
	* **`listener`** {Object} 리스너
	* **`funcName`** {Function} 콜백함수명

* **Usage**: 
```js
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
//메뉴 이벤트 등록
menu.setSelectListener(this, 'onMenuSelect');
//메뉴 아이템정보 세팅
menu.setItemInfoArr(menuInfo);
//메뉴팝업 ( 메뉴는 통상적으로 우클릭할때 띄우는데 e는 클릭이벤트의 이벤트정보를 가르킨다.)
menu.popupEx({ 'left': e.pageX+1, 'top': e.pageY+1});
```

<br/>

### setIconMap()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### popupSubmenu()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setResultListener()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setOverStyle()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>
