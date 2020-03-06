# APage
> **Extends**: `AContainer`

페이지 컨테이너 하나의 전체 화면을 구성한다.

<br/>

## Properties


### navigator

페이지 이동을 관리하는 ANavigator 객체

* **Type**: `ANavigator`
* **Default**: `null`

<br/>

### oneshot

비활성화시 바로 삭제 여부. true 이면 매번 새로 로드된다.

* **Type**: `Boolean`
* **Default**: `false`

<br/>
<br/>

## Methods

### onBackKey()

(모바일 전용) 백 버튼 클릭시 호출된다.

* **Returns**: Boolean

<br/>

### open( viewUrl, parent )

페이지 컨테이너를 부모에 가득차게 오픈하고 그안에 viewUrl에 해당하는 뷰를 넣는다.(left:0, top:0, width:100%, height:100%)

* **Parameters**: 
	* **`viewUrl`** {String} viewUrl
	* **`parent`** {String} parent

* **Usage**: 
```js
var page = new APage();
page.open('view/main.lay',null);
```

<br/>
<br/>
