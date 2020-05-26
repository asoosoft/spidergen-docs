# AMenuBar
> **Extends**: [`ABar`](ABar.html#abar)

메뉴바 컴포넌트

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### addMenuButton( text, menuItem )

메뉴정보로 메뉴 버튼을 추가한다.

- `text` \<String> 버튼 명
- `menuItem` \<Object> 메뉴아이템 정보객체

```js
//MainView에 메뉴가 노출될 menuBarView 뷰를 추가한다.

function MainView*onInitDone()
{
	super.onInitDone();

	var menuItem = [
		 { text: 'Open File', id:'OPEN_FILE', iconMapUrl: 'Assets/icon.png', icon:0 },
		 { text: 'Close File', id:'CLOSE_FILE', iconMapUrl: 'Assets/icon.png', icon:1, shortKey:'Ctrl+F4' }
		];

	var menuBar = new AMenuBar();
	menuBar.init();
	menuBar.addMenuButton('File', menuItem);
	menuBar.addEventListener('select', this, 'onMenuSelect');	//메뉴선택 이벤트 처리함수 지정	
	this.menuBarView.addComponent(menuBar); // 화면의 메뉴바를 띄울 뷰에 menuBar를 추가한다.
};

//메뉴선택 이벤트 처리함수 지정	
function MainView*onMenuSelect(comp, info, e)
{
	//comp : 이벤트를 발생 시킨 컴포넌트 AMenuBar
	//info : select 이벤트가 발생한 메뉴 정보
	//e : select 이벤트 객체

	console.log(info); 

};
-----------------------------------------------------------------------------------------------------------
{ text: 'Close File', id:'CLOSE_FILE', iconMapUrl: 'Assets/icon.png', icon:1, shortKey:'Ctrl+F4' }
```

<br/>

### initWithMenuInfo( menuInfo )

메뉴바 초기화와 동시에 메뉴정보로 메뉴 버튼들을 생성한다.

* `menuInfo` \<Array> 메뉴 정보 (json 형태의 요소) 


```js
var menuInfo = [{
	text: 'File', 	//메뉴명
　　sub: [ 			//메뉴정보		
		{ text: 'Open File', id:'OPEN_FILE', iconMapUrl: 'Assets/icon.png', icon:0 },
		{ text: 'Close File', id:'CLOSE_FILE', iconMapUrl: 'Assets/icon.png', icon:1, shortKey:'Ctrl+F4' }		
	]	
}];
menuBar.initWithMenuInfo(menuInfo);
menuBar.addEventListener('select', this, 'onMenuSelect');	//메뉴선택 이벤트 처리함수 지정	
this.menuBarView.addComponent(menuBar); // 화면의 메뉴바를 띄울 뷰에 menuBar를 추가한다.


//메뉴선택 이벤트 처리함수 지정	
function MainView*onMenuSelect(comp, info, e)
{
	//comp : 이벤트를 발생 시킨 컴포넌트 AMenuBar
	//info : select 이벤트가 발생한 메뉴 정보
	//e : select 이벤트 객체

	console.log(info); 

};
-----------------------------------------------------------------------------------------------------------
{ text: 'Close File', id:'CLOSE_FILE', iconMapUrl: 'Assets/icon.png', icon:1, shortKey:'Ctrl+F4' }
```
<br/>

### findMenuButton(index)

index 번째 메뉴 아이템을 리턴한다.

* `index` \<Number> 메뉴 아이템 순번

- **Returns** \<Object> HTML 객체

<br/>
<br/>
