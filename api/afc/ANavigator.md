# ANavigator

네비게이터, 페이지 이동 및 히스토리를 관리한다.

<br/>

## Class Variables

<br>
<br>

## Instance Variables

*아래 변수들은 set,get 함수를 만들던지 뭔가 대책이 필요*

### slideDir
<br>

### isAsync
<br/>

### cntr
----
<br>
<br>


## Class Methods

### ANavigator.find( name )
- `name` \<String> 네비게이터 이름
- **Returns** \<[ANavigator](#ANavigator)>

<br>

### ANavigator.getRootNavigator()
- **Returns** \<[ANavigator](#ANavigator)>

<br>
<br>

## Instance Methods

### canGoNext()

다음 페이지로 이동 가능한지를 리턴한다.

* **Returns**: Boolean

<br/>

### canGoPrev()

이전 페이지로 이동 가능한지를 리턴한다.

* **Returns**: Boolean

<br>

### clearAllPage()

<br>

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

* **`pageId`** {String} 페이지 아이디

```js
var navi = ANavigator.find('sample');
navi.clearPage('MainPage');
```

<br/>

### getActivePage()

현재 활성화된 페이지를 얻어온다.

* **Returns**: APage

```js
var navi = ANavigator.find('sample');
var actPage = navi.getActivePage();
```

<br/>

### getPage( pageId )

특정 페이지를 얻어온다.

- `pageId` {String} 얻어올 페이지 아이디 또는 인덱스
- **Returns**: APage

```js
var navi = ANavigator.find('sample');
var page = navi.getPage('SubPage');
```

<br/>

### goNextPage( data )

히스토리상의 다음 페이지로 화면을 이동시킨다.

* **`data`** {Object} 이동할 페이지에게 넘길 데이터
* **Returns**: Boolean

```js
var navi = ANavigator.find('sample');
var data = { tabId : 'subtab01' };
navi.goNextPage(data);
```

<br/>

### goPage( pageId, data, isNoHistory )

특정 페이지로 화면을 이동시킨다.

- `pageId` {String or Number} 이동할 페이지 아이디(registerPage 호출시 등록한 아이디) 또는 인덱스(등록한 순서)
- `data` {Object} 이동할 페이지에게 넘길 데이터
- `isNoHistory` {Boolean} 히스토리에 남기지 않을 경우 true

```js
var navi = ANavigator.find('sample');
var data = { tabId : 'subtab01' };
navi.goPage('SubPage', data, false);
```

<br/>

### goPrevPage( data )

이전 페이지로 이동시킵니다.
- **`data`** {Object} 이동할 페이지에 넘길 데이터
- **Returns**: Boolean

```js
var navi = ANavigator.find('sample');
var data = { tabId : 'prevtab01' };
navi.goPrevPage(data);
```

<br/>

### registerPage( url, pageId, pageClass, cond )

네비게이터에 페이지 정보를 등록한다. registerPage 로 페이지를 등록해야 goPage 를 통해 페이지 이동이 가능하다.

- **`url`** {String} 이동할 페이지의 리소스 경로
- **`pageId`** {String} 페이지를 구분할 고유 아이디
- **`pageClass`** {String} 페이지를 클래스 이름
- **`cond`** {Object} 디바이스 조건에 따라 다른 페이지가 로드되도록 하기 위한 정보.

```js
var navi = ANavigator.find('sample');
navi.registerPage('Source/MainPage.lay', 'MainPage');
```

<br/>

### registerPageEx( pageInfo )

파라미터로 받은 pageInfo로 registerPage를 호출하여 네비게이터에 페이지 정보를 등록한다.

- **`pageInfo`** {Object} pageInfo.layUrl / pageInfo.pageId / pageInfo.pageClass/  pageInfo.cond

```js
var navi = ANavigator.find('sample');
var pageInfo = { layUrl: 'Source/MainPage.lay', pageId: 'MainPage' };
navi.registerPageEx(pageInfo);
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

### setAsync( isAsync )
<br>
<br>

## Events

### onResize()

네비게이터의 활성화된 모든 화면의 onResize를 호출한다.<br/>화면크기가 변경될 때 컨테이너에서 자신이 네비게이터의 프레임 컨테이너인 경우 호출한다.

<br>
