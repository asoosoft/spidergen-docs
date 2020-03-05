# AMenuBar
> **Extends**: `ABar`

AMenuBar

<br/>

## Methods

### addMenuButton( text, menuItem )

메뉴버튼을 추가합니다.

* **Parameters**: 
	* **`text`** {String} 버튼 명
	* **`menuItem`** {Object} 메뉴아이템

* **Usage**: 
```js
var menuBar = new AMenuBar();
var menuItem = [
　{ text: 'Open File', id:'OPEN_FILE', iconMapUrl: 'Assets/icon.png', icon:0 },
　{ text: 'Close File', id:'CLOSE_FILE', iconMapUrl: 'Assets/icon.png', icon:1, shortKey:'Ctrl+F4' }
];
menuBar.init();
menuBar.addMenuButton('File', menuItem);
menuBar.addEventListener('select', this, 'onMenuSelect');	//메뉴선택 이벤트 처리함수 지정	
this.menuBarView.addComponent(menuBar); // 화면의 메뉴바를 띄울 뷰에 menuBar를 추가한다.
```

<br/>

### initWithMenuInfo( menuInfo )

메뉴정보로 메뉴버튼들을 생성한다.

* **Parameters**: 
	* **`menuInfo`** {Array} 메뉴 정보

* **Usage**: 
```js
var menuInfo = [ 
　{
　　text: 'File',
　　sub: [
　　　{ text: 'Open File', id:'OPEN_FILE', iconMapUrl: 'Assets/icon.png', icon:0 },
　　　{ text: 'Close File', id:'CLOSE_FILE', iconMapUrl: 'Assets/icon.png', icon:1, shortKey:'Ctrl+F4' }
　　　//, ...
　　]
　}
];
menuBar.initWithMenuInfo(menuInfo);
menuBar.addEventListener('select', this, 'onMenuSelect');	//메뉴선택 이벤트 처리함수 지정	
this.menuBarView.addComponent(menuBar); // 화면의 메뉴바를 띄울 뷰에 menuBar를 추가한다.
```

<br/>
<br/>
## Events


### select( comp, info, e )

추가한 메뉴를 선택했을 때 발생하는 이벤트 함수. <br/>info 는 { id: MENU_ID, ... } 구조이며, initWithMenuInfo 함수의 파라미터로 넘긴 객체정보 중 각 메뉴에 해당하는 정보가 들어있다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} 선택한 메뉴 정보객체
	* **`e`** {Object} 이벤트 객체

<br/>

