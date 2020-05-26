# ATabView
**Extends**: `AComponent`

탭뷰 컴포넌트

<br/>
<br/>

## Class Variables

<br/>
<br/>

## Instance Variables

### btnStyles \<Array>

버튼 스타일 클래스 명 배열. 순서는 아래와 같다.

['Select_Style', 'Deselect_Style'] (선택 시 스타일 클래스, 미선택 시 스타일 클래스)

<br/>

### delegator \<[AView](AView.html#aview)>

탭 이동 시 이벤트를 받을 화면.<br/>[setDelegator( delegator )](#setdelegator-delegator-) 에서 세팅할 수 있다.

<br/>

### lastSelectedTabId \<String>

현재 선택된 탭의 아이디

<br/>

### selectedTab \<Object>

현재 선택된 탭

<br/>
<br/>

## Instance Methods

### addTab( name, url, tabId, data, oneshot, isLoad, asyncCallback )

탭뷰에 탭을 추가한다.

- `name` \<String> 버튼 타이틀
- `url` \<String> 탭 버튼 클릭시 보여줄 컨텐츠의 url
- `tabId` \<String> 고유 아이디
- `data` \<Object> 추가적인 데이터
- `oneshot`\<Boolean> 탭 선택 해제 시 컨텐츠 삭제 여부
- `isLoad` \<Boolean> 탭 선택 시 로드할지 여부
- `asyncCallback` \<Function> 있으면 로드 시 비동기로 로드하며 로드 된 [AView](AView.html#aview)를 인자로 받는다.

```js
tabView.addTab('tab1', 'Source/view1.lay', {}, false, false, function(aview)
{
    console.log('load complete');
})
```

<br/>

### addTabEx( tabInfo )

탭뷰에 탭을 추가한다.

- `tabInfo` \<Object> 추가할 탭의 정보
- **Returns** \<HTMLObject>

```js
this.tabview.addTabEx({
    name: 'tab1', // 버튼 타이틀
    url: 'Source/view1.lay', // 탭 버튼 클릭시 보여줄 컨텐츠의 url
    tabId: 'tab1', // 고유 아이디
    data: {}, // 추가적인 데이터
    oneshot: false, // 탭 선택 해제 시 컨텐츠 삭제 여부
    isLoad: false, // 탭 선택 시 로드할지 여부
    asyncCallback: function(aview)
    {
        console.log('load complete');
    } // 있으면 로드 시 비동기로 로드하며 로드 된 AView를 인자로 받는다.
});
```

<br/>

### clearHistory()

히스토리 기록을 모두 지운다.

<br/>

### clearSelectTab()

선택된 탭을 초기화 한다.

<br/>

### enableAnimation( enable )

탭 이동 시 애니메이션 옵션을 설정한다.

- `enable` \<Boolean> 활성 여부
 
<br/>

### enableHistory( enable )

탭뷰의 히스토리 기능의 사용 여부를 설정한다.

- `enable` \<Boolean> 사용 여부

<br/>

### getAllTabs()

모든 탭 객체를 jQueryObject 로 리턴한다.

- **Returns** \<JQuery Object>

<br/>

### getLastSelectedTabId()

마지막으로 선택된 탭의 아이디를 반환한다.

- **Returns** \<String>

<br/>

### getSelectedTab()

현재 선택상태인 탭을 반환한다.

- **Returns** \<HTMLObject>

<br/>

### getSelectedView()

현재 선택 탭의 뷰를 반환한다.

- **Returns** \<AView>

<br/>

### getTabById( tabId )

매개변수 tabId 에 대응하는 탭을 반환한다.

- `tabId` \<String> 탭 아이디
- **Returns** \<HTMLObject>

<br/>

### getTabByInx( index )

매개변수 index 에 대응하는 탭을 반환한다.

- `index` \<Number> 탭 인덱스
- **Returns** \<HTMLObject>

<br/>

### goNextSelect( data )

히스토리 기능을 통해 goPrevSelect를 사용했다면, 반대로 사용하기 전 뷰로 돌아간다.

- `data` \<Object> 추가적인 데이터

```js
this.tabView.goNextSelect('Text or anything');
```

<br/>

### goPrevSelect( data )

히스토리 기능을 사용중이라면, 이전에 선택했던 뷰로 돌아간다.

- `data` \<Object> 추가적인 데이터

```js
this.tabView.goPrevSelect('Text or anything');
```

<br/>

### hideTabArea()

탭버튼 영역을 보이지 않게 설정한다.

<br/>

### removeAllTab()

탭뷰내에 모든 탭을 삭제한다.

<br/>

### removeTab( tab )

매개변수 tab에 해당하는 탭을 삭제한다.

- `tab` \<HTML Object> 탭 객체

```js
var delTab = this.tabview.getTabByInx(0);
this.tabview.removeTab(delTab);
```

<br/>

### selectTab( tab, data, isNoHistory )

매개변수 tab에 해당하는 탭을 선택상태로 설정한다.

- `tab` \<HTML Object> 활성화할 탭 객체
- `data` \<Object> 추가적인 데이터
- `isNoHistory` \<Boolean> 

```js
var tab = this.tabview.getTabByInx(0);
this.tabview.selectTab(tab);
```

<br/>

### selectTabById( tabId )

매개변수 tabId 에 대응하는 탭을 선택상태로 설정한다.

- `tabId` \<String> 활성화할 탭 아이디
- **Returns** \<HTMLObject>

<br/>

### selectTabByIndex( index )

매개변수 index 에 대응하는 탭을 선택상태로 설정한다.

- **Returns** \<HTMLObject>
- `index` \<Number> 활성화할 탭 인덱스

<br/>

### setBtnStyle( styles )

탭 버튼의 스타일을 변경한다.

- `styles` \<Array> 선택 시, 미선택 시 의 스타일 클래스명 배열

```js
this.tabview.setBtnStyle(['style1', 'style2']);
```

<br/>

### setDelegator( delegator )

컴포넌트에 delegator를 설정한다.

- `delegator` \<Object> delegator

<br/>

### setSlideDir( dir )

탭변환 애니메이션이 slide 일 경우의 방향값을 셋팅한다.

- `dir` <String> 방향 ('left' / 'right')

<br/>

### setTabName( tab, name )

매개변수 tab에 해당하는 탭의 타이틀을 설정한다.

- `tab` \<HTML Object> 특정 탭 객체
- `name` \<String> 탭 타이틀

```js
var tab = this.tabview.getTabByInx(0);
this.tabview.setTabName(tab, '타이틀');
```

<br/>

### setTabOption( option )

탭 옵션을 설정한다.

- `option` \<Object> contentReload: false, //탭이 변경될 경우 컨텐츠를 다시 로드할 지.   changeAnimation: 'slide', //애니메이션 종류(fade, slide)   sameTabCheck: true //탭변경시 같은 탭이면 아무 동작도 하지 않도록 할지
 
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

- `tab` \<HTML Object> 특정 탭 객체
- `url` \<String> 리소스 url

```js
var tab = this.tabview.getTabByInx(0);
this.tabview.setTabUrl(tab, 'lay/tab2.lay');
```

<br/>

### showTabArea()

탭버튼 영역을 보이게 설정한다.

<br/>
<br/>

## Events

### afterTabChanged()

탭이 변경된후 [delegator](#delegator-aview) 로 이벤트를 위임받은 객체가 있을경우 호출된다.<br/>
oldView : 기존 선택된 뷰<br/>
newView : 새로 선택된 뷰<br/>
isFirst : 탭이 처음 열리는지 여부

### beforeTabChanging()

탭이 변경되기전 [delegator](#delegator-aview) 로 이벤트를 위임받은 객체가 있을경우 호출된다.<br/>
oldView : 기존 선택된 뷰<br/>
newView : 새로 선택된 뷰<br/>
isFirst : 탭이 처음 열리는지 여부

### swipe( comp, info, e )

스와이프시 발생한다.

- `comp` \<AComponent> 컴포넌트
- `info` \<Object> {direction: 방향, distance: 이동거리}
- `e` \<Object> 이벤트 객체

### tabChanging()

탭이 변경될때 [delegator](#delegator-aview) 로 이벤트를 위임받은 객체가 있을경우 호출된다.<br/>
oldView : 기존 선택된 뷰<br/>
newView : 새로 선택된 뷰<br/>
isFirst : 탭이 처음 열리는지 여부

<br/>
<br/>

## Attribute

### Tab

- `Width`  탭의 가로 사이즈를 지정하는 속성
- `Height`  탭의 높이를 지정하는 속성
- `Hidden`  탭의 표시여부를 설정하는 속성
- `Select History` 히스토리 기능 사용을 설정하는 속성

### Items

- `Select` 탭뷰 중 기본적으로 선택될 탭아이디를 설정하는 속성
- `add` 탭뷰를 추가하는 속성
    - `ID` 탭을 구분하기 위한 ID
    - `Name` 탭에 표시될 텍스트
    - `URL` 탭과 매칭될 탭뷰의 URL

- `edit` 탭의 설정 내용을 수정하는 속성
- `del` 탭을 삭제한다.
- `up` 탭의 순서를 한스탭 앞으로 이동한다.
- `down` 탭의 순서를 한스탭 뒤로 이동한다.

<br/>
