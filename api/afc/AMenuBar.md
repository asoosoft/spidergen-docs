# AMenuBar
> **Extends**: [`ABar`](ABar.html#abar)

메뉴바 컴포넌트

<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### addMenuButton( text, menuItem )

메뉴버튼을 추가합니다.

- `text` \<String> 버튼 명
- `menuItem` \<Object> 메뉴아이템 정보객체

```js
// import "Framework/afc/component/AMenuBar.js" 빌드 옵션에 따라 필요 할 수 있음.

//메뉴 아이템 정보
var menuItem = [
　{ text: 'Open File', id:'OPEN_FILE', iconMapUrl: 'Assets/icon.png', icon:0 },
　{ text: 'Close File', id:'CLOSE_FILE', iconMapUrl: 'Assets/icon.png', icon:1, shortKey:'Ctrl+F4' }
];

var menuBar = new AMenuBar();
menuBar.init();
menuBar.addMenuButton('File', menuItem);
menuBar.addEventListener('select', this, 'onMenuSelect');	//메뉴선택 이벤트 처리함수 지정	
this.menuBarView.addComponent(menuBar); // 화면의 메뉴바를 띄울 뷰에 menuBar를 추가한다.
```

<br/>

### initWithMenuInfo( menuInfo )

메뉴정보로 메뉴 버튼들을 생성한다.

* `menuInfo` \<Array> 메뉴 정보 (json 형태의 요소)

```js
var menuInfo = [{
	text: 'File',
　　sub: [
		{ text: 'Open File', id:'OPEN_FILE', iconMapUrl: 'Assets/icon.png', icon:0 },
		{ text: 'Close File', id:'CLOSE_FILE', iconMapUrl: 'Assets/icon.png', icon:1, shortKey:'Ctrl+F4' }
			//...
	]	
}];
menuBar.initWithMenuInfo(menuInfo);
menuBar.addEventListener('select', this, 'onMenuSelect');	//메뉴선택 이벤트 처리함수 지정	
this.menuBarView.addComponent(menuBar); // 화면의 메뉴바를 띄울 뷰에 menuBar를 추가한다.
```

<br/>

### findMenuButton(index)

index 번째 메뉴 아이템을 리턴한다.

* `index` \<Number> 메뉴 아이템 순번

- **Returns** \<Object> JQuery 객체

<br/>
<br/>
