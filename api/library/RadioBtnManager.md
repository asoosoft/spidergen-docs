# RadioBtnManager 

버튼들을 라디오버튼처럼 동작하게 하는 클래스

<br/>

## Class Variables

### isCheckStyle \<String>

라디오 버튼 클릭시 스타일

<br/>

### selectBtn \<AButton>

선택된 버튼

<br/>

### view \<AView>

라디오 버튼 매니저를 설정할 뷰

<br/>
<br/>

## Class Methods

### RadioBtnManager(view, isCheckStyle)

- `view` \<AButton> 라디오 버튼 매니저를 설정할 뷰
- `isCheckStyle` \<String> 라디오 버튼 클릭시 스타일

## Instance Methods

### getSelectButton()

선택된 버튼을 리턴한다.

* **Returns** \<AButton>

```js
var rbMgr = new RadioBtnManager(this);
var selBtn = rbMgr.getSelectButton();
if(selBtn) selBtn.reset(this);
selBtn.selectButton(this.myBtn);
```

<br/>

### reset( view )

선택된 버튼을 초기화한다.

- `view` \<AView> 관리할 버튼들이 있는 뷰객체

```js
var rbMgr = new RadioBtnManager(this);
var selBtn = rbMgr.getSelectButton();
if(selBtn) rbMgr.reset(this);
rbMgr.selectButton(this.myBtn);
```

<br/>

### selectButton( selBtn )

기존에 선택된 버튼이 있으면 활성화(선택 해제)해주고, 파라미터로 넘어온 버튼을 비활성화(선택)한다.

* `selBtn` \<String> 선택할 버튼 아이디 또는 버튼 객체

```js
var rbMgr = new RadioBtnManager(this);
var selBtn = rbMgr.getSelectButton();
if(selBtn) rbMgr.reset(this);
rbMgr.selectButton(this.myBtn);
```

<br/>
<br/>