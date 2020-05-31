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

### cntr \<[AContainer]()>
화면 전환이 이루어질 컨테이너 영역, 네비게이터가 생성되는 시점에 지정된다. 

<br>
<br>


## Class Methods

### ANavigator.find( name )
생성된 네비게이터들 중에서 이름이로 네비게이터 객체를 찾는다.
- `name` \<String> 네비게이터 이름
- **Returns** \<[ANavigator](#ANavigator)>
  
<br>

### ANavigator.getRootNavigator()
루트컨테이너에 셋팅된 최상위 네비게이터를 리턴한다. 화면전체가 전환되는 방식으로 네비게이터를 사용하는 경우 생성되는 객체이다.
- **Returns** \<[ANavigator](#ANavigator)>

<br>

### ANavigator.getLastNavigator()
마지막으로 화면 전환이 이루어진 네비게이터 객체를 리턴한다. 즉, 최근 사용되어진 네비게이터 객체
- **Returns** \<[ANavigator](#ANavigator)>
  
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
pageId 로 특정 페이지를 닫는다. 컨테이터만 닫을 뿐 [registerPage](#registerPage(-url,-pageId,-pageClass,-cond-)) 로 등록한 페이지 정보는 사라지지 않는다. 즉, goPage 를 호출하면 다시 새롭게 페이지가 열린다.

- `pageId` \<String> 페이지 아이디

<br>

### enableAsync( enable )
최초로 goPage 가 호출되어 페이지 이동시 컨테이너가 open 되는데, 관련된 리소스를 비동기로 로드되도록 한다. 기본값은 true 이다.

<br>

### getActivePage()

현재 네비게이터 페이지 중에서 활성화된 페이지를 얻어온다.

- **Returns** \<[APage](#APage)>

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

### getPage( pageId )

registerPage 로 등록된 페이지 중에서 아이디로 특정 페이지를 얻어온다.

- `pageId` \<String> 얻어올 페이지 아이디
- **Returns** \<[APage]()>

```js
var navi = ANavigator.find('testNavi');
var page = navi.getPage('MainView');

var view = page.getView();
view.refreshData(); //call any function 
```
<br>

### getSlideDir()
화면 전환 타입이 slide 인 경우 슬라이드되는 방향을 얻어온다. [setFlipType](#setFlipType(-flipType-)) 함수 참조
- **Returns** \<String> `left, right, up, down`

<br>

----
여기부터
----


### goNextPage( data )

히스토리상의 다음 페이지로 화면을 이동시킨다.

- `data` \<Object> 이동할 페이지에게 넘길 데이터
- **Returns** \<Boolean>

```js
var navi = ANavigator.find('sample');
var data = { tabId : 'subtab01' };
navi.goNextPage(data);
```

<br>

### goPage( pageId, data, isNoHistory )

특정 페이지로 화면을 이동시킨다.

- `pageId` \<String> or \<Number> 이동할 페이지 아이디(registerPage 호출시 등록한 아이디) 또는 인덱스(등록한 순서)
- `data` \<Object> 이동할 페이지에게 넘길 데이터
- `isNoHistory` \<Boolean> 히스토리에 남기지 않을 경우 true

```js
var navi = ANavigator.find('sample');
var data = { tabId : 'subtab01' };
navi.goPage('SubPage', data, false);
```

<br>

### goPrevPage( data )

이전 페이지로 이동시킵니다.
- `data` \<Object> 이동할 페이지에 넘길 데이터
- **Returns** \<Boolean>

```js
var navi = ANavigator.find('sample');
var data = { tabId : 'prevtab01' };
navi.goPrevPage(data);
```

<br>

### registerPage( url, pageId, pageClass, cond )

네비게이터에 페이지 정보를 등록한다. registerPage 로 페이지 정보를 등록한 후 goPage 를 통해 이동한다. 실제로 리소스가 로드되고 컨테이너가 open 되는 시점은 최초로 goPage 를 호출하는 시점이다. 한번 로드된 페이지는 closePage 를 호출할 때까지 소멸되지 않고 재사용된다.

- `url` \<String> 이동할 페이지의 리소스 경로
- `pageId` \<String> 페이지를 구분할 고유 아이디
- `pageClass` \<String> 페이지를 클래스 이름
- `cond` \<Object> 디바이스 조건에 따라 다른 페이지가 로드되도록 하기 위한 정보.

```js
var navi = ANavigator.find('sample');
navi.registerPage('Source/MainPage.lay', 'MainPage');
```

<br>

### registerPageEx( pageInfo )

파라미터로 받은 pageInfo로 registerPage를 호출하여 네비게이터에 페이지 정보를 등록한다.

- `pageInfo` \<Object> { layUrl, pageId, pageClass, cond }

```js
var navi = ANavigator.find('sample');
var pageInfo = { layUrl: 'Source/MainPage.lay', pageId: 'MainPage' };
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
<br>

## Events

### onResize()

네비게이터의 활성화된 모든 화면의 onResize를 호출한다.<br/>화면크기가 변경될 때 컨테이너에서 자신이 네비게이터의 프레임 컨테이너인 경우 호출한다.

<br>
