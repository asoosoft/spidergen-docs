# ANavigator
> **Extends**: 

네비게이터, 페이지 이동 및 히스토리를 관리한다.

<br/>

## Properties


### pageHistory



* **Type**: ``
* **Default**: ``

<br/>

### curHisIndex



* **Type**: ``
* **Default**: ``

<br/>

### flipType



* **Type**: ``
* **Default**: ``

<br/>

### slideDir



* **Type**: ``
* **Default**: ``

<br/>

### pageInfoMap



* **Type**: ``
* **Default**: ``

<br/>

### activePage



* **Type**: ``
* **Default**: ``

<br/>

### cntr



* **Type**: ``
* **Default**: ``

<br/>

### cntr.childNavigator



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### canGoNext()

다음 페이지로 이동 가능한지를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var canGoNext = navi.canGoNext();
```

<br/>

### canGoPrev()

이전 페이지로 이동 가능한지를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var canGoPrev = navi.canGoPrev();
```

<br/>

### clearHistory()

페이지 이동 히스토리를 모두 지운다.

* **Usage**: 
```js
var navi = ANavigator.find('sample');
navi.clearHistory();
```

<br/>

### clearPage( pageId )

해당 페이지를 종료합니다.

* **Parameters**: 
	* **`pageId`** {String} 페이지 아이디

* **Usage**: 
```js
var navi = ANavigator.find('sample');
navi.clearPage('MainPage');
```

<br/>

### ANavigator.find( name )

name에 해당하는 네비게이터 객체를 반환한다. name을 입력하지 않으면 가장 최근에 생성된 네비게이터를 반환한다.

* **Returns**: ANavigator

* **Parameters**: 
	* **`name`** {String} 네이게이터명

* **Usage**: 
```js
var navi = ANavigator.find('sample');
```

<br/>

### flipPage( willActivePage, isFirst )

화면을 전환한다. 라이프 사이클 함수가 호출된다.

* **Parameters**: 
	* **`willActivePage`** {AContainer} 활성화될 APage 객체
	* **`isFirst`** {Boolean} 최초 오픈 여부

<br/>

### ANavigator.getActiveNavigator()

가장 최근에 생성된 네비게이터 객체를 반환한다.

* **Returns**: ANavigator

* **Usage**: 
```js
var navi = ANavigator.getActiveNavigator();
```

<br/>

### ANavigator.getActiveNaviPage()

가장 최근에 생성된 네비게이터 객체의 활성화된 APage 객체를 반환한다.

* **Returns**: APage

* **Usage**: 
```js
var actPage = ANavigator.getActiveNavigator();
```

<br/>

### getActivePage()

현재 활성화된 페이지를 얻어온다.

* **Returns**: APage

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var actPage = navi.getActivePage();
```

<br/>

### getPage( pageId )

특정 페이지를 얻어온다.

* **Returns**: APage

* **Parameters**: 
	* **`pageId`** {String or Number} 얻어올 페이지 아이디 또는 인덱스

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var page = navi.getPage('SubPage');
```

<br/>

### getPageInfo( pageId )

pageId로 페이지 정보를 리턴합니다.

* **Returns**: Object

* **Parameters**: 
	* **`pageId`** {String} 페이지 아이디

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var pageInfo = navi.getPageInfo('SubPage');
```

<br/>

### goNextPage( data )

히스토리상의 다음 페이지로 화면을 이동시킨다.

* **Returns**: Boolean

* **Parameters**: 
	* **`data`** {Object} 이동할 페이지에게 넘길 데이터

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var data = { tabId : 'subtab01' };
navi.goNextPage(data);
```

<br/>

### goPage( pageId, data, isNoHistory )

특정 페이지로 화면을 이동시킨다.

* **Parameters**: 
	* **`pageId`** {String or Number} 이동할 페이지 아이디(registerPage 호출시 등록한 아이디) 또는 인덱스(등록한 순서)
	* **`data`** {Object} 이동할 페이지에게 넘길 데이터
	* **`isNoHistory`** {Boolean} 히스토리에 남기지 않을 경우 true

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var data = { tabId : 'subtab01' };
navi.goPage('SubPage', data, false);
```

<br/>

### goPrevPage( data )

이전 페이지로 이동시킵니다.

* **Returns**: Boolean

* **Parameters**: 
	* **`data`** {Object} 이동할 페이지에 넘길 데이터

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var data = { tabId : 'prevtab01' };
navi.goPrevPage(data);
```

<br/>

### onResize()

네비게이터의 활성화된 모든 화면의 onResize를 호출한다.<br/>화면크기가 변경될 때 컨테이너에서 자신이 네비게이터의 프레임 컨테이너인 경우 호출한다.

<br/>

### pushHistory( page )

히스토리를 추가한다.

* **Parameters**: 
	* **`page`** {AContainer} APage 객체

<br/>

### registerPage( url, pageId, pageClass, cond )

네비게이터에 페이지 정보를 등록한다. registerPage 로 페이지를 등록해야 goPage 를 통해 페이지 이동이 가능하다.

* **Parameters**: 
	* **`url`** {String} 이동할 페이지의 리소스 경로
	* **`pageId`** {String} 페이지를 구분할 고유 아이디
	* **`pageClass`** {String} 페이지를 클래스 이름
	* **`cond`** {Object} 디바이스 조건에 따라 다른 페이지가 로드되도록 하기 위한 정보.

* **Usage**: 
```js
var navi = ANavigator.find('sample');
navi.registerPage('Source/MainPage.lay', 'MainPage');
```

<br/>

### registerPageEx( pageInfo )

파라미터로 받은 pageInfo로 registerPage를 호출하여 네비게이터에 페이지 정보를 등록한다.

* **Parameters**: 
	* **`pageInfo`** {Object} pageInfo.layUrl / pageInfo.pageId / pageInfo.pageClass/  pageInfo.cond

* **Usage**: 
```js
var navi = ANavigator.find('sample');
var pageInfo = { layUrl: 'Source/MainPage.lay', pageId: 'MainPage' };
navi.registerPageEx(pageInfo);
```

<br/>

### ANavigator.reportBackKeyEvent()

가장 최근에 생성된 네비게이터의 활성화된 페이지의 onBackKey 함수를 호출하여 뒤로가기를 실행한다.

* **Returns**: Boolean

* **Usage**: 
```js
var isBack = ANavigator.reportBackKeyEvent();
```

<br/>

### ANavigator.reportResizeEvent()

화면의 크기가 변경되었을 때 저장된 네비게이터중 첫번째 원소(루트 네비게이터) 의 onResize를 호출하여 크기변경을 알려준다.

* **Usage**: 
```js
ANavigator.reportResizeEvent();
```

<br/>

### setFlipType( flipType )

애니메이션을 세팅합니다.

* **Parameters**: 
	* **`flipType`** {String} 'normal', 'slide', 'fade'

* **Usage**: 
```js
var navi = ANavigator.getActiveNavigator();
if(navi) navi.setFlipType('fade');
```

<br/>

### setSlideDir( dir )

페이지 이동 애니메이션이 slide 일 경우 방향을 셋팅한다.

* **Parameters**: 
	* **`dir`** {String} 'left', 'right','up','down'

* **Usage**: 
```js
var navi = ANavigator.getActiveNavigator();
if(!navi) return;
navi.setFlipType('slide');
navi.setSlideDir('down');
```

<br/>

### clearAllPage()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
