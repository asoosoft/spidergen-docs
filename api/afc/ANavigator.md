# ANavigator( name, cntr )
1. 네비게이터는 컨테이너 내부에서 화면을 전환해 주며 전환된 화면들의 히스토리를 관리해 준다.
2. 히스토리상의 이전과 다음으로 이동하거나 원하는 특정 화면으로 이동할 수 있다.
3. 전체화면을 네비게이터 영역으로 사용하는 방식과 특정 컨테이너 영역을 지정하여 사용하는 방식이 있다.
4. [registerPage](#registerPage(-url,-pageId,-pageClass,-cond-)) 로 페이지 정보를 등록한 후 필요한 시점에 [goPage](#goPage(-pageId,-data,-isNoHistory-)) 로 화면을 전환한다.

- `name` \<String> 네비게이터 이름 지정, 생성된 네비게이터를 찾는데 사용된다.
- `cntr` \<AContainer> 네비게이터가 작동할 컨테이너 영역, 생략하면 rootContainer 가 자동 셋팅된다.

<br/>

## Class Variables
<br>
<br>

## Instance Variables

### cntr \<[AContainer](./AContainer.md)>
화면 전환이 이루어질 컨테이너 영역, 네비게이터가 생성되는 시점에 지정된다. 

<br>
<br>


## Class Methods

### ANavigator.find( name )
생성된 네비게이터들 중에서 이름이로 네비게이터 객체를 찾는다.
- `name` \<String> 네비게이터 이름
- **Returns** \<[ANavigator](./ANavigator.md)>
  
<br>

### ANavigator.getRootNavigator()
루트컨테이너에 셋팅된 최상위 네비게이터를 리턴한다. 화면전체가 전환되는 방식으로 네비게이터를 사용하는 경우 생성되는 객체이다.
- **Returns** \<[ANavigator](./ANavigator.md)>

<br>

### ANavigator.getLastNavigator()
마지막으로 화면 전환이 이루어진 네비게이터 객체를 리턴한다. 즉, 최근 사용되어진 네비게이터 객체
- **Returns** \<[ANavigator](./ANavigator.md)>
  
<br>
<br>

## Instance Methods

### canGoNext()

다음 페이지로 이동 가능한지를 리턴한다. 즉, 다음으로 이동할 히스토리가 존재하는지
- **Returns** \<Boolean>
```js
//Next 버튼을 클릭을 했을 경우..
function SubView1*onNextBtnClick(comp, info, e)
{
	//이름으로 네비게이터 를 찾는 방법
	var navi = ANavigator.find('testNavi');
	
	//다음페이지로 이동가능한지 체크, 비교하지 않아도 없는 경우는 이동하지 않는다.
	if(navi.canGoNext()) navi.goNextPage();
	
	else AToast.show("다음 페이지 히스토리 정보가 없습니다.");
};
```
<br>

### canGoPrev()

이전 페이지로 이동 가능한지를 리턴한다. 즉, 이전으로 이동할 히스토리가 존재하는지
- **Returns** \<Boolean>

<br>

### closeAllPage()
현재 네비게이터에 등록되어 열려 있는 모든 페이지를 닫는다. [closePage](#closePage(-pageId-)) 참조

<br>

### clearHistory()

페이지 이동 히스토리를 모두 지운다.

<br>

### closePage( pageId )
pageId 로 특정 페이지를 닫는다. 컨테이터만 닫을 뿐 [registerPage](#registerPage(-url,-pageId,-pageClass,-cond-)) 로 등록한 페이지 정보는 사라지지 않는다. 즉, goPage 를 호출하면 다시 새롭게 페이지가 열린다. [unRegisterPage](#unRegisterPage(-pageId-)) 참조

- `pageId` \<String> 페이지 아이디

<br>

### enableOneshot( enable )
실제로 리소스가 로드되고 컨테이너가 open 되는 시점은 최초로 [goPage](#goPage(-pageId,-data,-isNoHistory-)) 를 호출하는 시점이다. 한번 로드된 페이지는 closePage 를 호출할 때까지 소멸되지 않고 재사용된다.
하지만 Oneshot 옵션이 true 가 되면 페이지가 비활성화 될 경우 페이지를 자동으로 close 하며 goPage 시점마다 페이지를 다시 open 한다. 기본값은 `false`

- `enable` \<Boolean> 활성화 여부

<br>

### getActivePage()

현재 네비게이터 페이지 중에서 활성화된 페이지를 얻어온다.

- **Returns** \<[APage](./APage.md)>

```js
var navi = ANavigator.find('testNavi');
var page = navi.getActivePage();

var view = page.getView();
view.refreshData(); //call any function 
```
<br>

### getFlipType()
화면 전환 타입을 얻어온다. [setFlipType](#setFlipType(-flipType-)) 함수 참조
- **Returns** \<String> `normal, slide, fade`

<br>

### getNextPage()

히스토리상의 다음 페이지 객체를 얻어온다.
- **Returns** \<APage> 

<br>

### getPage( pageId )

registerPage 로 등록된 페이지 중에서 아이디로 특정 페이지를 얻어온다.

- `pageId` \<String> 얻어올 페이지 아이디
- **Returns** \<[APage](./APage.md)>

```js
var navi = ANavigator.find('testNavi');
var page = navi.getPage('MainView');

var view = page.getView();
view.refreshData(); //call any function 
```
<br>

### getPrevPage()

히스토리상의 이전 페이지 객체를 얻어온다.
- **Returns** \<APage> 

<br>

### getSlideDir()
화면 전환 타입이 slide 인 경우 슬라이드되는 방향을 얻어온다. [setFlipType](#setFlipType(-flipType-)) 함수 참조
- **Returns** \<String> `left, right, up, down`

<br>

### goNextPage( data )

히스토리상의 다음 페이지로 화면을 이동시킨다.

- `data` \<Object> 이동할 페이지에게 넘길 데이터
- **Returns** \<Boolean> 이동할 페이지가 없을 경우 false

<br>

### goPage( pageId, data, isNoHistory )

특정 페이지로 화면을 이동시킨다. [registerPage](#registerPage(-url,-pageId,-pageClass,-cond-)) 참조

- `pageId` \<String> 이동할 페이지 아이디 (registerPage 호출시 등록한 아이디)
- `data` \<Object> 이동할 페이지에게 넘길 데이터, AContainer 의 getData() 함수를 통해 얻어올 수 있다.
- `isNoHistory` \<Boolean> true 이면 화면 이동을 히스토리에 남기지 않는다.

```js
var navi = ANavigator.find('sample');
var data = { name : 'subtab01' };
navi.goPage('SubPage', data);
```
<br>

### goPrevPage( data )

히스토리상의 이전 페이지로 화면을 이동시킨다.
- `data` \<Object> 이동할 페이지에게 넘길 데이터
- **Returns** \<Boolean> 이동할 페이지가 없을 경우 false

<br>

### registerPage( url, pageId, pageClass, cond, isAsync )

네비게이터에 페이지 정보를 등록한다. registerPage 로 페이지 정보를 등록한 후 goPage 를 통해 해당 화면으로 이동한다. 실제로 리소스가 로드되고 컨테이너가 open 되는 시점은 최초로 goPage 를 호출하는 시점이다. 한번 로드된 페이지는 closePage 를 호출할 때까지 소멸되지 않고 보존된다. `(show, hide 방식)` [enableOneshot](#enableOneshot(-enable-)) 참조

- `url` \<String> 이동할 페이지의 리소스 경로
- `pageId` \<String> 페이지를 구분할 고유 아이디
- `pageClass` \<String> 페이지를 클래스 이름, 기본값은 `APage`
- `cond` \<Function> 조건에 따라 다른 페이지가 로드되도록 하기 위한 함수, 이 변수에 함수를 셋팅하면 페이지를 이동할 때마다 이 함수를 호출하여 참이면 해당 페이지로 이동한다. 같은 pageId 로 다른 url 을 등록할 경우 이 조건을 만족하는 페이지를 우선 리턴해 준다.
- `isAsync` \<Boolean> goPage 가 호출되어 최초 페이지 이동시 컨테이너가 open 되는데, 관련된 리소스를 비동기로 로드할지 여부를 셋팅한다. 값을 생략하면 기본적으로 AContainer.isAsyncLoad 값이 적용되며 기본값은 false 이다.

```js
var navi = new ANavigator('testNavi');
navi.registerPage('Source/LoginView.lay', 'LoginView');
navi.registerPage('Source/MainView.lay', 'MainView');
navi.registerPage('Source/PageView01.lay', 'PageView');
navi.registerPage('Source/PageView02.lay', 'PageView', null, function()
{
    return (screen.width<640);
});
navi.registerPage('Source/PageView03.lay', 'PageView', null function()
{
    return (screen.width>1280);
});

//PageView 는 같은 아이디로 3개의 lay 파일이 등록되어 있고
//아래와 같이 호출시 조건에 맞는 lay 파일을 로드한다.
navi.goPage('PageView');
```

<br>

### registerPageEx( pageInfo )

내부적으로 registerPage 함수를 호출한다. registerPage 함수의 파라미터를 Object 형태로 넘길 수 있다.
- `pageInfo` \<Object> `url, pageId, pageClass, cond`

```js
var navi = ANavigator.find('sample');
var pageInfo = 
{ 
    url: 'Source/MainPage.lay', 
    pageId: 'MainView', 
    cond: function() {
    } 
};
navi.registerPageEx(pageInfo);
```

<br>

### setFlipType( flipType )

화면 전환 타입을 지정한다. [goPage]() 시점에 화면이 전환되는 액션을 설정한다.
- `flipType` \<String> `normal, slide, fade` 기본값은 normal
  - `normal` : 단순 화면전환
  - `slide` : 슬라이드(미끄러지 듯 전환) 효과를 주면서 화면이 전환된다. 이 옵션이 셋팅되면 setSlideDir 로 방향을 지정할 수 있다.
  - `fade` : Fade In/Out 효과를 주면서 화면이 전환된다.

```js
var navi = new ANavigator('testNavi');

navi.setFlipType('slide');
navi.setSlideDir('right');
...
```
<br>

### setSlideDir( dir )

화면 전환 타입이 slide 인 경우 슬라이드되는 방향을 셋팅한다. [setFlipType](#setFlipType(-flipType-)) 함수 참조
- `dir` \<String> `left, right, up, down` 기본값은 left

<br>

### unRegisterPage( pageId )
[registerPage](#registerPage(-url,-pageId,-pageClass,-cond-)) 로 등록한 페이지 정보를 제거한다. 페이지가 open 되어 있으면 close 시킨다. [closePage](#closePage(-pageId-)) 참조
- `pageId` \<String> 등록을 해제하고자 하는 페이지 아이디


<br>
<br>

## Events

