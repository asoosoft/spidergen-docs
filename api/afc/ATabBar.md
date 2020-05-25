# ATabBar
**Extends**: `AComponent`

ATabBar

<br/>

## Instance Variables

### selectedTab \<Object>

선택된 탭

<br/>

### moreBtn \<>

더 보기 버튼

<br/>

### ttTimer \<>

<br/>

### curTooltip \<>

<br/>

### iconMap \<>

<br/>
<br/>

## Instance Methods

### findTabById( tabId )

Id로 탭 아이템을 반환한다.

- `tabId` \<String> 탭 아이디
- **Returns** \<AView>

<br/>

### getActiveTabIdx()

현재 활성화된 탭의 index를 반환한다.

* **Returns** \<number>

<br/>

### getAllTabs()

탭바의 모든 탭 아이템을 배열로 반환한다.

* **Returns** \<Arrays>

<br/>

### getFirstTab()

탭바의 첫번째 탭을 반환한다.

* **Returns** \<AView>

<br/>

### getHiddenTabs()

탭바에서 보이지 않는 영역의 탭들을 배열로 반환한다.

* **Returns** \<Arrays>

<br/>

### getLastTab()

탭바의 가장 마지막 탭 아이템을 반환한다.

* **Returns** \<AView>

<br/>

### getNextTab( tab )

파라미터로 넘어온 탭아이템의 바로 다음 순서의 아이템을 반환한다.

* `tab` \<AView> 탭 아이템
* **Returns** \<AView>

<br/>

### getPrevTab( tab )

파라미터로 넘어온 탭아이템의 바로 이전 순서의 아이템을 반환한다.

* `tab` \<AView> 탭 아이템
* **Returns** \<AView>

<br/>

### getSelectedCntr()

현재 선택된 탭의 컨테이너를 반환한다.

* **Returns** \<AContainer>

<br/>

### getSelectedTab()

현재 선택된 탭을 반환한다.

* **Returns** \<AView>

<br/>

### getTabCount()

탭의 갯수를 반환한다.

* **Returns** \<Number>

<br/>

### indexOfTab( tab )

탭의 index를 리턴합니다

* **Returns** \<number>
* `tab` \<AView> 탭 아이템

<br/>

### moveTab( mvTab, posTab, isAfter )

파라미터로 받은 mvTab의 위치를 이동시킵니다.

* `mvTab` \<AView> 위치를 이동시킬 탭아이템
* `posTab` \<String> 기준이 되는 탭아이템
* `isAfter` \<Boolean> true: posTab 다음으로 이동합니다.  /  false : posTab 앞으로 이동합니다.

<br/>

### removeTab( rTab, doNotSelect )

탭을 삭제합니다.

* `rTab` \<AQueryData> 삭제할 탭 아이템
* `doNotSelect` \<String> true일 경우 이전탭으로 활성화 해줍니다.

<br/>

### selectFirstTab()

탭바의 첫 번째 탭 아이템을 활성화 합니다.

<br/>

### selectLastTab()

탭바의 마지막 탭 아이템을 활성화 합니다.

<br/>

### selectTab( tab, moveFirst )

파라미터로 넘어온 Tab을 활성화합니다.

* `tab` \<AView> 탭 아이템
* `moveFirst` \<Boolean> 탭을 활성화하면서 가장앞으로 가져올지 여부
* **Returns** \<AView>

<br/>

### selectTabById( tabId, moveFirst )

탭을 Id를 이용해서 활성화합니다.


* `tabId` \<String> 탭 Id
* `moveFirst` \<Boolean> 탭을 활성화하면서 맨 앞으로 이동할지 여부
* **Returns** \<AView>

<br/>

### setDelegator( delegator )

Delegator를 세팅합니다.

* `delegator` \<AView> Delegator

<br/>

### onDropBtnClicked( acomp, info )

- `acomp` \<>
- `info` \<>

```js

```

<br/>

### onMenuSelect( menu, info )

- `menu` \<>
- `info` \<>

```js

```

<br/>

### onCloseBtnClick( acomp, info )

- `acomp` \<AComponent> AMenu 컴포넌트
- `info` \<Object> 정보


<br/>

### selectTabByIndex( index, moveFirst )

인덱스 값을 이용하여 탭을 선택한다.

- `index` \<Number> 
- `moveFirst` \<Boolean>

```js

```

<br/>

### setTabTitle( tab, title )

- `tab` \<>
- `title` \<>

```js

```

<br/>

### getTabTitle( tab )

- `tab` \<>

```js

```

<br/>

### setIconMapUrl( iconMap )

- `iconMap` \<>

```js

```

<br/>

### setIconMap( iconMap )

- `iconMap` \<>

```js

```

<br/>

### changeIcon( tab, icon )

- `tab` \<>
- `icon` \<>

```js

```

<br/>

### addTab (tabId, title, cntr, ttMsg, icon)

- `tabId` \<>
- `title` \<>
- `cntr` \<>
- `ttMsg` \<>
- `icon` \<>

```js

```

<br/>

### findTabByIndex( index )

- `index` \<>

```js

```

<br/>

### getBgPos( icon )

- `icon` \<>

```js

```

<br/>
<br/>

## Events


### change()

값을 변경하면 호출합니다.

### move()

무브 이벤트 발생시 호출합니다.

<br/>
