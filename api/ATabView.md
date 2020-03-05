# ATabView
> **Extends**: `AComponent`

탭뷰 컴포넌트

<br/>

## Properties


### delegator

delegate 함수를 구현할 객체

* **Type**: `Object`
* **Default**: `null`

<br/>

### isAnimation

탭 변환시 애니메이션을 줄지 여부

* **Type**: `Boolean`
* **Default**: `false`

<br/>

### navigator

탭뷰에 네비게이션 기능을 부여하기위해 셋팅한 ANavigator 객체

* **Type**: `ANavigator`
* **Default**: `null`

<br/>

### option

탭 옵션 <br/>contentReload: false, //탭이 변경될 경우 컨텐츠를 다시 로드할 지 <br/>changeAnimation: 'slide', //애니메이션 종류(fade, slide) <br/>sameTabCheck: true //탭변경시 같은 탭이면 아무 동작도 하지 않도록 할지

* **Type**: `Object`
* **Default**: 

<br/>

### slideDir

탭 변환 애니메이션이 slide 일 경우 방향값

* **Type**: `String`
* **Default**: `'left'`

<br/>
<br/>

## Methods

### addTab( name, url, tabId, data, oneshot )

탭뷰에 탭을 추가한다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`name`** {String} 버튼 타이틀
	* **`url`** {String} 탭에 보여줄 url
	* **`tabId`** {String} 고유 아이디
	* **`data`** {Object} 추가적인 데이터
	* **`oneshot`** {Boolean} 탭 선택 해제 시 컨텐츠 삭제 여부

* **Usage**: 
```js
this.tabview.addTab('탭1', 'lay/view1.lay', 'tab1', {}, false);
```

<br/>

### addTabEx( tabInfo )

탭뷰에 탭을 추가한다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`tabInfo`** {Object} 추가할 탭의 정보

* **Usage**: 
```js
this.tabview.addTabEx({
    name: '탭1', // 버튼 타이틀
    url: 'lay/view1.lay', // 컨텐츠의 url
    tabId: 'tab1', // 고유 아이디
    data: {}, // 추가적인 데이터
    oneshot: false // 탭 선택 해제 시 컨텐츠 삭제 여부
});
```

<br/>

### callSubActiveEvent( funcName, isFirst )

선택된 탭의 매개변수 funcName 에 해당하는 함수(onActiveDone)를 호출한다.<br/>처음 호출하는것인지 여부를 isFirst 인자로 보낼수 있다.

* **Parameters**: 
	* **`funcName`** {String} 함수명
	* **`isFirst`** {Boolean} 처음 호출 여부

* **Usage**: 
```js
this.tabview.callSubActiveEvent('onActiveDone', true);
```

<br/>

### clearSelectTab()

선택된 탭을 초기화 한다.

* **Usage**: 
```js
this.tabview.clearSelectTab();
```

<br/>

### enableAnimation( enable )

탭변환 애니메이션 활성여부를 설정한다.

* **Parameters**: 
	* **`enable`** {Boolean} 활성여부

* **Usage**: 
```js
this.tabview.enableAnimation(true);
```

<br/>

### getAllTabs()

모든 탭 객체를 jQueryObject 로 리턴한다.

* **Returns**: JQueryObject

* **Usage**: 
```js
var tabs = this.tabview.getAllTabs();
```

<br/>

### getLastSelectedTabId()

마지막으로 선택된 탭의 아이디를 반환한다.

* **Returns**: String

* **Usage**: 
```js
var id = this.tabview.getLastSelectedTabId();
```

<br/>

### getSelectedTab()

현재 선택상태인 탭을 반환한다.

* **Returns**: HTMLObject

* **Usage**: 
```js
var tab = this.tabview.getSelectedTab();
```

<br/>

### getSelectedView()

현재 선택 탭의 뷰를 반환한다.

* **Returns**: AView

* **Usage**: 
```js
var v = this.tabview.getSelectedView();
```

<br/>

### getTabById( tabId )

매개변수 tabId 에 대응하는 탭을 반환한다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`tabId`** {String} 탭 아이디

* **Usage**: 
```js
var tab = this.tabview.getTabById('tab2');
```

<br/>

### getTabByInx( index )

매개변수 index 에 대응하는 탭을 반환한다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`index`** {Number} 탭 인덱스

* **Usage**: 
```js
var tab = this.tabview.getTabByInx(1);
```

<br/>

### hideTabArea()

탭버튼 영역을 보이지 않게 설정한다.

* **Usage**: 
```js
this.tabview.hideTabArea();
```

<br/>

### removeAllTab()

탭뷰내에 모든 탭을 삭제한다.

* **Usage**: 
```js
this.tabview.removeAllTab();
```

<br/>

### removeFromView( onlyRelease )

탭뷰의 모든탭을 삭제한다. 매개변수 onlyRelease 는 내부적으로 사용되므로 기본적으로는 입력하지 않는다.

* **Parameters**: 
	* **`onlyRelease`** {Boolean} true일 경우 실제로 컴포넌트를 제거하지 않고 연관된 자원만 해제함

* **Usage**: 
```js
this.tabview.removeFromView();
```

<br/>

### removeTab( tab )

매개변수 tab에 해당하는 탭을 삭제한다.

* **Parameters**: 
	* **`tab`** {HTML Object} 탭 객체

* **Usage**: 
```js
var delTab = this.tabview.getTabByInx(0);
this.tabview.removeTab(delTab);
```

<br/>

### selectTab( tab )

매개변수 tab에 해당하는 탭을 선택상태로 설정한다.

* **Parameters**: 
	* **`tab`** {HTML Object} 활성화할 탭 객체

* **Usage**: 
```js
var tab = this.tabview.getTabByInx(0);
this.tabview.selectTab(tab);
```

<br/>

### selectTabById( tabId )

매개변수 tabId 에 대응하는 탭을 선택상태로 설정한다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`tabId`** {String} 활성화할 탭 아이디

* **Usage**: 
```js
this.tabview.selectTabById('tab2');
```

<br/>

### selectTabByIndex( index )

매개변수 index 에 대응하는 탭을 선택상태로 설정한다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`index`** {Number} 활성화할 탭 인덱스

* **Usage**: 
```js
this.tabview.selectTabByIndex(1);
```

<br/>

### setBtnStyle( styles )

탭 버튼의 스타일을 변경한다.

* **Parameters**: 
	* **`styles`** {Array} 스타일 명의 배열

* **Usage**: 
```js
this.tabview.setBtnStyle(['style1', 'style2']);
```

<br/>

### setDelegator( delegator )

컴포넌트에 delegator를 설정한다.

* **Parameters**: 
	* **`delegator`** {Object} delegator

<br/>

### setSlideDir( dir )

탭변환 애니메이션이 slide 일 경우의 방향값을 셋팅한다.

* **Parameters**: 
	* **`dir`** {String} 방향 (left / right)

* **Usage**: 
```js
this.tabview.setSlideDir('left');
```

<br/>

### setTabName( tab, name )

매개변수 tab에 해당하는 탭의 타이틀을 설정한다.

* **Parameters**: 
	* **`tab`** {HTML Object} 특정 탭 객체
	* **`name`** {String} 탭 타이틀

* **Usage**: 
```js
var tab = this.tabview.getTabByInx(0);
this.tabview.setTabName(tab, '타이틀');
```

<br/>

### setTabOption( option )

탭 옵션을 설정한다.

* **Parameters**: 
	* **`option`** {Object} contentReload: false, //탭이 변경될 경우 컨텐츠를 다시 로드할 지.   changeAnimation: 'slide', //애니메이션 종류(fade, slide)   sameTabCheck: true //탭변경시 같은 탭이면 아무 동작도 하지 않도록 할지

* **Usage**: 
```js
this.tabview.setTabOption({
	contentReload: false,
	changeAnimation: 'slide',
	sameTabCheck: true
});
```

<br/>

### setTabUrl( tab, url )

매개변수 tab에 해당하는 탭의 url을 설정한다.

* **Parameters**: 
	* **`tab`** {HTML Object} 특정 탭 객체
	* **`url`** {String} 리소스 url

* **Usage**: 
```js
var tab = this.tabview.getTabByInx(0);
this.tabview.setTabUrl(tab, 'lay/tab2.lay');
```

<br/>

### showTabArea()

탭버튼 영역을 보이게 설정한다.

* **Usage**: 
```js
this.tabview.showTabArea();
```

<br/>
<br/>
## Events


### afterTabChanged()

탭이 변경된후 delegator 로 이벤트를 위임받은 객체가 있을경우 호출된다.<br/>oldView : 기존 선택된 뷰<br/>newView : 새로 선택된 뷰<br/>isFirst : 탭이 처음 열리는지 여부

### beforeTabChanging()

탭이 변경되기전 delegator 로 이벤트를 위임받은 객체가 있을경우 호출된다.<br/>oldView : 기존 선택된 뷰<br/>newView : 새로 선택된 뷰<br/>isFirst : 탭이 처음 열리는지 여부

### swipe( comp, info, e )

스와이프시 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} {direction: 방향, distance: 이동거리}
	* **`e`** {Object} 이벤트 객체

### tabChanging()

탭이 변경될때 delegator 로 이벤트를 위임받은 객체가 있을경우 호출된다.<br/>oldView : 기존 선택된 뷰<br/>newView : 새로 선택된 뷰<br/>isFirst : 탭이 처음 열리는지 여부

<br/>

