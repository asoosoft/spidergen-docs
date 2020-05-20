# MDMenuBar
**Extends**: [`AMenuBar`](../afc/AMenuBar.html#amenubar)

메뉴 버튼들을 모아놓은 메뉴바를 만드는 컴포넌트

<br/>

## Properties

### activeMenu \<[AMenu](../afc/AMenu.html#amenu)>

현재 액티브 되어있는 메뉴

<br/>

### $activeMenuBtn \<JQuery Object>

현재 액티브 되어있는 버튼 jQuery 객체

<br/>
<br/>

## Instance Methods

<br/>

### init( context, evtListener )

컴포넌트 객체를 생성한 후 초기화 할 때 호출한다. 코딩을 이용하여 동적으로 객체를 생성할 경우 사용한다. 일반적으로 파라미터를 생략하여 기본값으로 생성 되도록 해준다.

- `context` \<String> 컴포넌트 생성 정보
- `evtListener` \<String> 이벤트 발생 시 수신할 객체

```js
var mdMenuBar = new MDMenuBar();
mdMenuBar.init();
```

<br/>

### initWithMenuInfo( menuInfo )

컴포넌트 객체를 생성한 후 메뉴 정보를 추가하여 초기화 할 때 호출한다. 코딩을 이용하여 동적으로 객체를 생성할 경우 사용한다.

- `menuInfo` \<Object> 메뉴정보

```js
//iconMap은 stl에 백그라운드 이미지를 입혀놓은 클래스명이거나 이미지의 주소이다.
//이미지는 각 16*16인 아이콘이 나열된 이미지이다.
//icon은 나열된 이미지 중 해당 인덱스이다.
var mdMenuBar = new MDMenuBar();
var menuInfo =
[
    {text: 'btn1', iconMap:'common_icon_map' , sub:
        [
            {text:'sub_btn1', shortKey:'Ctrl+Shift+S', id:'SUB1', icon: 2},
            {text:'sub_btn2', shortKey:'Ctrl+Shift+D', id:'SUB2', icon: 3}
        ]
    },
    {text: 'btn2', iconMap},
    {text: 'btn3', iconMap}
];
mdMenuBar.initWithMenuInfo(menuInfo);
```

<br/>

### addMenuButton( text, menuItem, iconMap)

메뉴버튼을 추가한다.

- `text` \<String> 버튼 텍스트
- `menuItem` \<Array> 서브메뉴 배열
- `iconMap` \<String> 아이콘맵

```js
var menuItem =
[
    {text:'sub_btn1', shortKey:'Ctrl+Shift+S', id:'SUB1', icon: 2},
    {text:'sub_btn2', shortKey:'Ctrl+Shift+D', id:'SUB2', icon: 3}
];
mdMenuBar.addMenuButton('btn1', menuItem, 'common_icon_map');
```

<br/>