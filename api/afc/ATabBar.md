# ATabBar
**Extends**: [`AComponent`](AComponent.html#acomponent)

ATabBar

<br/>

## Class Variables

<br/>
<br/>

## Instance Variables

### iconMap \<String> or \<Array> 

탭 버튼에 사용될 아이콘 경로가 저장되어있는 변수

<br/>

### moreBtn \<[AButton](AButton.html#abutton)>

더 보기 버튼

<br/>

### selectedTab \<Object>

선택된 탭

<br/>
<br/>

## Instance Methods

### addTab (tabId, title, cntr, ttMsg, icon)

- `tabId` \<String> 탭 아이디
- `title` \<String> 탭 타이틀
- `cntr` \<[AContainer](AContainer.html#acontainer)> 컨테이너
- `ttMsg` \<String> 툴팁 메시지
- `icon` \<Number> 아이콘 인덱스

```js
tabbar.addTab('tab1', '탭1', new AContainer(), '툴팁1', 0);
```

<br/>

### findTabById( tabId )

Id로 탭 아이템을 반환한다.

- `tabId` \<String> 탭 아이디
- **Returns** \<[AView](AView.html#aview)>

<br/>

### findTabByIndex( index )

인덱스로부터 탭을 리턴한다.

- `index` \<Number> 인덱스

<br/>

### getActiveTabIdx()

현재 활성화된 탭의 index를 반환한다.

- **Returns** \<number>

<br/>

### getAllTabs()

탭바의 모든 탭 아이템을 배열로 반환한다.

- **Returns** \<Arrays>

<br/>

### getFirstTab()

탭바의 첫번째 탭을 반환한다.

- **Returns** \<[AView](AView.html#aview)>

<br/>

### getHiddenTabs()

탭바에서 보이지 않는 영역의 탭들을 배열로 반환한다.

- **Returns** \<Arrays>

<br/>

### getLastTab()

탭바의 가장 마지막 탭 아이템을 반환한다.

- **Returns** \<[AView](AView.html#aview)>

<br/>

### getNextTab( tab )

파라미터로 넘어온 탭아이템의 바로 다음 순서의 아이템을 반환한다.

- `tab` \<[AView](AView.html#aview)> 탭 아이템
- **Returns** \<[AView](AView.html#aview)>

<br/>

### getPrevTab( tab )

파라미터로 넘어온 탭아이템의 바로 이전 순서의 아이템을 반환한다.

- `tab` \<[AView](AView.html#aview)> 탭 아이템
- **Returns** \<[AView](AView.html#aview)>

<br/>

### getSelectedCntr()

현재 선택된 탭의 컨테이너를 반환한다.

- **Returns** \<AContainer>

<br/>

### getSelectedTab()

현재 선택된 탭을 반환한다.

- **Returns** \<[AView](AView.html#aview)>

<br/>

### getTabCount()

탭의 갯수를 반환한다.

- **Returns** \<Number>

<br/>

### getTabTitle( tab )

특정 탭의 타이틀을 리턴한다.

- `tab` \<[AView](AView.html#aview)>

```js
var tab = tabbar.getSelectedTab();
tabbar.getTabTitle();
```

<br/>

### indexOfTab( tab )

탭의 index를 리턴한다.

- **Returns** \<number>
- `tab` \<[AView](AView.html#aview)> 탭 아이템

<br/>

### moveTab( mvTab, posTab, isAfter )

파라미터로 받은 mvTab의 위치를 이동시킨다.

- `mvTab` \<[AView](AView.html#aview)> 위치를 이동시킬 탭아이템
- `posTab` \<String> 기준이 되는 탭아이템
- `isAfter` \<Boolean> true: posTab 다음으로 이동 / false : posTab 앞으로 이동

<br/>

### removeTab( rTab, doNotSelect )

탭을 삭제한다.

- `rTab` \<AQueryData> 삭제할 탭 아이템
- `doNotSelect` \<String> true일 경우 이전탭으로 활성화 한다.

<br/>

### selectFirstTab()

탭바의 첫 번째 탭 아이템을 활성화 한다.

<br/>

### selectLastTab()

탭바의 마지막 탭 아이템을 활성화 한다.

<br/>

### selectTab( tab, moveFirst )

파라미터로 넘어온 Tab을 활성화한다.

- `tab` \<[AView](AView.html#aview)> 탭 아이템
- `moveFirst` \<Boolean> 탭을 활성화하면서 가장앞으로 가져올지 여부
- **Returns** \<[AView](AView.html#aview)>

<br/>

### selectTabById( tabId, moveFirst )

탭을 Id를 이용해서 활성화한다.


- `tabId` \<String> 탭 Id
- `moveFirst` \<Boolean> 탭을 활성화하면서 맨 앞으로 이동할지 여부
- **Returns** \<[AView](AView.html#aview)>

<br/>

### selectTabByIndex( index, moveFirst )

인덱스 값을 이용하여 탭을 선택한다.

- `index` \<Number> 선택 할 탭의 위치
- `moveFirst` \<Boolean> 맨앞으로 이동할지 여부

<br/>

### setDelegator( delegator )

Delegator를 세팅한다.

- `delegator` \<[AView](AView.html#aview)> Delegator

<br/>

### setIconMap( iconMap )

아이콘을 세팅한다.

- `iconMap` \<String>

```js
//탭바에 세팅하는 아이콘맵은 stl에 백그라운드 이미지를 입혀놓은 클래스명이거나 이미지의 주소이다.
//이미지는 각 16*16인 아이콘이 나열된 이미지이다.
tabbar.setIconMap('tree_icon_map');
```

<br/>

### setTabTitle( tab, title )

특정 탭의 타이틀을 세팅한다.

- `tab` \<[AView](AView.html#aview)>
- `title` \<String>

```js
var tab = tabbar.getSelectedTab();
tabbar.setTabTitle(tab, 'New Title');
```

<br/>
<br/>

## Events

<br/>
<br/>