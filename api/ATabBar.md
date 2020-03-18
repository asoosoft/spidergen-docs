# ATabBar
> **Extends**: `AComponent`

ATabBar

<br/>

## Properties

### selectedTab



* **Type**: ``
* **Default**: ``

<br/>

### moreBtn



* **Type**: ``
* **Default**: ``

<br/>

### ttTimer



* **Type**: ``
* **Default**: ``

<br/>

### curTooltip



* **Type**: ``
* **Default**: ``

<br/>

### iconMap



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### findTabById( tabId )

Id로 탭 아이템을 리턴받습니다.

* **Returns**: AView

* **Parameters**: 
	* **`tabId`** {String} 탭 아이디

<br/>

### getActiveTabIdx()

현재 활성화된 탭의 index를 리턴합니다.

* **Returns**: number

<br/>

### getAllTabs()

탭바의 모든 탭 아이템을 배열로 리턴받습니다.

* **Returns**: Arrays

<br/>

### getFirstTab()

탭바의 첫번째 탭을 리턴합니다.

* **Returns**: AView

<br/>

### getHiddenTabs()

탭바에서 보이지 않는 영역의 탭들을 배열로 리턴합니다.

* **Returns**: Arrays

<br/>

### getLastTab()

탭바의 가장 마지막 탭 아이템을 리턴합니다.

* **Returns**: AView

<br/>

### getNextTab( tab )

파라미터로 넘어온 탭아이템의 바로 다음 순서의 아이템을 리턴합니다.

* **Returns**: AView

* **Parameters**: 
	* **`tab`** {AView} 탭 아이템

<br/>

### getPrevTab( tab )

파라미터로 넘어온 탭아이템의 바로 이전 순서의 아이템을 리턴합니다.

* **Returns**: AView

* **Parameters**: 
	* **`tab`** {AView} 탭 아이템

<br/>

### getSelectedCntr()

현재 선택된 탭의 컨테이너를 리턴합니다.

* **Returns**: AContainer

<br/>

### getSelectedTab()

현재 선택된 탭을 리턴합니다.

* **Returns**: AView

<br/>

### getTabCount()

getTabCount

<br/>

### indexOfTab( tab )

탭의 index를 리턴합니다

* **Returns**: number

* **Parameters**: 
	* **`tab`** {AView} 탭 아이템

<br/>

### moveTab( mvTab, posTab, isAfter )

파라미터로 받은 mvTab의 위치를 이동시킵니다.

* **Parameters**: 
	* **`mvTab`** {AView} 위치를 이동시킬 탭아이템
	* **`posTab`** {String} 기준이 되는 탭아이템
	* **`isAfter`** {Boolean} true: posTab 다음으로 이동합니다.  /  false : posTab 앞으로 이동합니다.

<br/>

### removeTab( rTab, doNotSelect )

탭을 삭제합니다.

* **Parameters**: 
	* **`rTab`** {AQueryData} 삭제할 탭 아이템
	* **`doNotSelect`** {String} true일 경우 이전탭으로 활성화 해줍니다.

<br/>

### selectFirstTab()

탭바의 첫 번째 탭 아이템을 활성화 합니다.

<br/>

### selectLastTab()

탭바의 마지막 탭 아이템을 활성화 합니다.

<br/>

### selectTab( tab, moveFirst )

파라미터로 넘어온 Tab을 활성화합니다.

* **Returns**: AView

* **Parameters**: 
	* **`tab`** {AView} 탭 아이템
	* **`moveFirst`** {Boolean} 탭을 활성화하면서 가장앞으로 가져올지 여부

<br/>

### selectTabById( tabId, moveFirst )

탭을 Id를 이용해서 활성화합니다.

* **Returns**: AView

* **Parameters**: 
	* **`tabId`** {String} 탭 Id
	* **`moveFirst`** {Boolean} 탭을 활성화하면서 맨 앞으로 이동할지 여부

<br/>

### setDelegator( delegator )

Delegator를 세팅합니다.

* **Parameters**: 
	* **`delegator`** {AView} Delegator

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### beforeInit()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### onDropBtnClicked()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### onMenuSelect()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### onCloseBtnClick()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### selectTabByIndex()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setTabTitle()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getTabTitle()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setIconMapUrl()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setIconMap()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### changeIcon()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### _changeIconByCss()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### _changeIconByUrl()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### addTab()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### _makeTab()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### findTabByIndex()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getBgPos()



* **Parameters**: 

* **Usage**: 
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
