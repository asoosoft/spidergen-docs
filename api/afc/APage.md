# APage
**Extends** `[AContainer](AContainer.html#AContainer)`




페이지 컨테이너 하나의 전체 화면을 구성한다.

<br/>

## Instance Variables

### navigator \<ANavigator>

페이지 이동을 관리하는 ANavigator 객체


<br/>

### oneshot \<Boolean>

비활성화시 바로 삭제 여부. true 이면 매번 새로 로드된다.

<br/>
<br/>

## Instance Methods

### getNavigator()

네비게이터를 반환한다.

- **Returns** \<ANavigator>

<br/>

### onBackKey()

모바일에서 백 버튼 클릭 시 호출된다.

* **Returns** \<Boolean>

<br/>

### open( viewUrl, parent )

페이지 컨테이너를 부모에 가득차게 오픈하고 그안에 viewUrl에 해당하는 뷰를 넣는다.</br>
(left:0, top:0, width:100%, height:100%)

* `viewUrl` \<String> viewUrl
* `parent` \<String> parent

```js
var page = new APage();
page.open('view/main.lay',null);
```

<br/>
<br/>
