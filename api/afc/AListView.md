# AListView
> **Extends**: `AComponent`

리스트뷰 컴포넌트

<br/>

## Properties

### delegator

리스트뷰의 delegate 함수를 처리할 객체

* **Type**: `Object`
* **Default**: `null`

<br/>

### itemHeight

리스트뷰 아이템의 높이

* **Type**: `String`
* **Default**: `null`

<br/>

### selectClass

아이템 선택시 적용 스타일 클래스

* **Type**: `String`
* **Default**: `null`

<br/>

### selectItem

선택되어진 아이템 객체

* **Type**: `HTML Object`
* **Default**: `null`

<br/>

### dividerColor



* **Type**: ``
* **Default**: ``

<br/>


### scrollArea



* **Type**: ``
* **Default**: ``

<br/>


### itemWrapper



* **Type**: ``
* **Default**: ``

<br/>


### scrollComp



* **Type**: ``
* **Default**: ``

<br/>


### scrlManager



* **Type**: ``
* **Default**: ``

<br/>


### savedScrollPos



* **Type**: ``
* **Default**: ``

<br/>


### defaultUrl



* **Type**: ``
* **Default**: ``

<br/>


### realMap



* **Type**: ``
* **Default**: ``

<br/>


### realField



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### addItem( url, dataArray, isPrepend )

리스트뷰에 아이템을 추가한다. dataArray 개수만큼 url 의 뷰리소스가 리스트뷰에 추가되며 데이터 매핑은 bindData 가 호출되어질 때 dataArray 가 넘어가며 사용자가 직접 하도록 한다.

* **Parameters**: 
	* **`url`** {String} 아이템에 추가될 뷰 리소스 url
	* **`dataArray`** {Array} 화면과 매핑될 데이터객체 배열
	* **`isPrepend`** {Boolean} 맨 앞에 추가할 지 여부

* **Usage**: 
```js
listview.setDelegator(this);
listview.addItem('Source/item.lay',['a','bb','ccc']);
```

<br/>

### callSubActiveEvent( funcName, isFirst )

하위 뷰들의 Active관련 함수를 실행한다.<br/><br/>단, 리스트뷰 옵션에서 isUpdatePosition가 true일때만 동작한다.

* **Parameters**: 
	* **`funcName`** {String} active 관련 함수명
	* **`isFirst`** {Boolean} 최초 실행여부

<br/>

### createBackup( maxRow, restoreCount )

리스트뷰 내에 아이템들을 백업한다.

* **Parameters**: 
	* **`maxRow`** {Number} 스크롤될때 아이템 인덱스 수
	* **`restoreCount`** {Number} 백업 저장할 수

<br/>

### createItems( url, dataArray, posItem, isPrepend )

리스트뷰에 아이템을 추가한다.<br/>dataArray 개수만큼 url의 뷰리소스가 리스트뷰에 추가되며 데이터 매핑은 bindData가 호출되어질때 dataArray가 넘어가며 사용자가 직접 하도록 한다.

* **Parameters**: 
	* **`url`** {String} 아이템에 추가될 뷰 리소스 url
	* **`dataArray`** {Array} 화면과 매핑될 데이터객체 배열
	* **`posItem`** {HTML Object} 아이템을 추가할 위치가 되는 아이템(생략될 경우 리스트뷰의 맨 앞이나 맨 뒤에 추가된다)
	* **`isPrepend`** {Boolean} 아이템을 맨 앞에 추가하거나 맨 뒤에 추가할지(posItem이 존재하면 posItem 앞이나 뒤에 추가한다)

<br/>

### destroyBackup()

백업기능을 파기한다.

<br/>

### enableScrlManager()

ScrollManager 의 자체 스크롤이 적용되도록 한다.

<br/>

### getBottomItem()

리스트뷰 내의 아이템들 중 마지막 아이템을 jQuery 객체로 반환합니다.<br/><br/>getLastItem() 함수와 동일합니다.

* **Returns**: HTML Object

* **Usage**: 
```js
var item = listview.getBottomItem();
```

<br/>

### getDefaultUrl()

리스트뷰의 아이템뷰에서 로드할 default url을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = listview.getDefaultUrl();
```

<br/>

### getFirstItem()

리스트뷰 내의 아이템들 중 첫번째 아이템을 jQuery 객체로 반환한다.<br/>getTopItem() 함수와 동일하다.

* **Returns**: Object

* **Usage**: 
```js
listview.getFirstItem();
```

<br/>

### getItem( index )

리스트뷰의 특정 인덱스의 아이템 객체를 리턴한다.

* **Returns**: HTMLObject

* **Parameters**: 
	* **`index`** {Number} 아이템 인덱스

* **Usage**: 
```js
//1번 inde에 있는 아이템을 리턴한다.
var item = listview.getItem(1);
```

<br/>

### getItemCount()

리스트뷰 내의 모든 아이템의 수를 반환합니다.<br/>getTotalCount() 함수와 동일합니다.

* **Returns**: number

* **Usage**: 
```js
var count = listview.getTotalCount();
```

<br/>

### getItems()

리스트뷰내의 모든 아이템들을 jQuery 객체로 리턴한다.

* **Returns**: JQueryObject

* **Usage**: 
```js
var items = listview.getItems();
```

<br/>

### getLastItem()

리스트뷰 내의 아이템들 중 마지막 아이템을 jQuery 객체로 반환합니다.<br/>getBottomItem() 함수와 동일합니다.

* **Returns**: Object

* **Usage**: 
```js
var result = listview.getLastItem();
```

<br/>

### getSelectItem()

현재 선택되어져 있는 아이템 객체를 리턴한다.

* **Returns**: HTMLObject

* **Usage**: 
```js
var item = listview.getSelectItem();
//아이템 객체의 뷰의 함수를 호출할때
item.view.function();
```

<br/>

### getTopItem()

리스트뷰 내의 아이템들 중 첫번째 아이템을 jQuery 객체로 반환합니다. <br/>getFirstItem() 함수와 동일합니다.

* **Returns**: HTML Object

* **Usage**: 
```js
var item = listview.getTopItem();
```

<br/>

### getTotalCount()

리스트뷰 내의 모든 아이템의 수를 반환합니다.<br/>getItemCount() 함수와 동일합니다.

<br/>

### indexOfItem( item )

특정 아이템의 인덱스를 얻어온다.

* **Returns**: Number

* **Parameters**: 
	* **`item`** {HTML Object} 인덱스를 얻을 아이템 객체

* **Usage**: 
```js
//item은 리스트뷰의 아이템 객체중에 하나이다.
listview.indexOfItem(item);
```

<br/>

### insertItem( url, dataArray, posItem, isPrepend )

리스트뷰의 특정 위치에 아이템을 삽입한다.

* **Parameters**: 
	* **`url`** {String} 아이템에 추가될 뷰 리소스 url
	* **`dataArray`** {Array} 데이터 배열
	* **`posItem`** {HTML Object} 아이템을 추가할 위치가 되는 아이템(생략될 경우 리스트뷰의 맨 앞이나 맨 뒤에 추가된다.)
	* **`isPrepend`** {Boolean} true: 앞 false : 뒤 / 아이템을 맨 앞에 추가하거나 맨 뒤에 추가할지(posItem 이 존재하면 posItem 앞이나 뒤에 추가한다.)

* **Usage**: 
```js
listview.setDelegator(this);
//리스트뷰 1234를 생성한다.
var item = listview.insertItem("../path/item.lay", [1,2,3,4], null);

//리스트뷰 5678을 생성하는데 앞서 생성한 아이템의 중간에 넣는다
listview.insertItem("../path/item.lay", [5,6,7,8], item[1], true);

//최종 리스트뷰의 순서는 1,5,6,7,8,2,3,4 가 된다.
```

<br/>

### isMoreScrollBottom()

하단으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = listview.isMoreScrollBottom();
```

<br/>

### isMoreScrollTop()

상단으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = listview.isMoreScrollTop();
```

<br/>

### isScroll()

현재 스크롤이 가능한 상태인지 여부를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = listview.isScroll();
```

<br/>

### itemInsertManage( item, posItem, isPrepend )

리스트뷰에 추가되는 아이템의 실제 구현부입니다.

* **Parameters**: 
	* **`item`** {HTML Object} 추가될 아이템
	* **`posItem`** {HTML Object} 아이템을 추가할 위치가 되는 아이템(생략될 경우 리스트뷰의 맨 앞이나 맨 뒤에 추가된다)
	* **`isPrepend`** {Boolean} 아이템을 맨 앞에 추가하거나 맨 뒤에 추가할지(posItem이 존재하면 posItem 앞이나 뒤에 추가한다)

<br/>

### moveBottomItems( items )

리스트뷰 내에 선택된 아이템들의 맨 아래로 옮기는 이다.

* **Parameters**: 
	* **`items`** {HTML Object} 아이템객체 배열

* **Usage**: 
```js
//items는 리스트뷰의 아이템객체 배열이다.
listview.moveBottomItems(items);
```

<br/>

### moveDownItems( items )

리스트뷰 내에 선택된 아이템들를 바로 아래 아이템 아래로 옮기는 함수이다.

* **Parameters**: 
	* **`items`** {HTML Object} 아이템 객체 배열

* **Usage**: 
```js
//items는 리스트뷰의 아이템객체 배열이다.
listview.moveDownItems(items);
```

<br/>

### moveTopItems( items )

리스트뷰 내에 선택된 아이템들의 맨 위로 옮기는 함수입니다.

* **Parameters**: 
	* **`items`** {HTML Object} 아이템객체 배열

* **Usage**: 
```js
//items는 리스트뷰의 아이템객체 배열입니다.
listview.moveTopItems(items);
```

<br/>

### moveUpItems( items )

리스트뷰 내에 선택된 아이템들를 바로 위 아이템 위로 옮기는 함수입니다.

* **Parameters**: 
	* **`items`** {HTML Object} 아이템객체 배열

* **Usage**: 
```js
//items는 리스트뷰의 아이템객체 배열이다.
listview.moveUpItems(items);
```

<br/>

### refreshListView()

리스트뷰의 자식 item 항목들을 갱신하여 보여주는 함수

* **Usage**: 
```js
listview.refreshListView();
```

<br/>

### removeAllItems()

리스트뷰 내의 모든 아이템을 삭제한다.

* **Usage**: 
```js
listview.removeAllItems();
```

<br/>

### removeItem( item )

리스트뷰에서 특정 아이템을 삭제한다.

* **Parameters**: 
	* **`item`** {HTML Object} 삭제할 아이템 객체

* **Usage**: 
```js
//item은 리스트뷰의 아이템중 하나이다.
listview.removeItem(item);
```

<br/>

### removeItemByIndex( index )

특정 아이템을 인덱스로 삭제한다.

* **Parameters**: 
	* **`index`** {Number} 삭제할 인덱스

* **Usage**: 
```js
//1번 index의 아이템을 리스트뷰에서 삭제한다.
listview.removeItemByIndex(1);
```

<br/>

### restoreScrollPos()

리스트뷰를 저장해둔 위치로 스크롤한다. 위치를 저장하려면 saveScrollPos함수를 호출한다.

* **Usage**: 
```js
listview.restoreScrollPos();
```

<br/>

### saveScrollPos()

현재 리스트뷰의 스크롤 위치를 저장해둔다. 리턴값이 없고 내부적으로 저장한다. 다시 불러올떄는 restoreScrollPos함수를 호출한다.

* **Usage**: 
```js
listview.saveScrollPos();
```

<br/>

### scrollBottomManage()

스크롤이 최하단에 위치하였는지 여부를 리턴하는 함수이다.

* **Returns**: boolean

* **Usage**: 
```js
var result = listview.scrollBottomManage();
```

<br/>

### scrollImplement()

자체적으로 스크롤 구현합니다. touchStart, touchMove, touchUp 이벤트가 동작합니다.

<br/>

### scrollOffset( offset )

스크롤의 y좌표값에서 offset 만큼 더한다.

* **Parameters**: 
	* **`offset`** {Number} 더해지는 값

* **Usage**: 
```js
listview.scrollOffset(100);
listview.scrollOffset(-100);
```

<br/>

### scrollTo( pos )

리스트뷰를 pos 좌표 위치로 스크롤합니다.

* **Parameters**: 
	* **`pos`** {Number} y좌표값

* **Usage**: 
```js
listview.scrollTo(0);
listview.scrollTo(50);
```

<br/>

### scrollToBottom()

리스트뷰를 최하단으로 스크롤한다.

* **Usage**: 
```js
listview.scrollToBottom();
```

<br/>

### scrollTopManage()

스크롤이 최상단에 위치하였는지 여부를 리턴하는 함수이다.

* **Returns**: boolean

* **Usage**: 
```js
var result = listview.scrollTopManage();
```

<br/>

### scrollToTop()

리스트뷰를 최상단으로 스크롤한다.

* **Usage**: 
```js
listview.scrollToTop();
```

<br/>

### setDefaultUrl( URL )

리스트뷰의 아이템뷰에서 로드할 default url을 설정한다. addItem 함수를 호출할때 URL값이 null이면 setDefaultUrl 함수로 저장한 URL을 사용한다. default url 마저도 없으면 아이템은 추가되지 않는다.

* **Parameters**: 
	* **`URL`** {String} 레이아웃의 URL

* **Usage**: 
```js
listview.setLoadUrl('Source/item.lay');
listview.addItem(null,['a','bb','ccc']);
```

<br/>

### setDelegator( delegator )

delegate 함수 처리 객체를 세팅한다.

* **Parameters**: 
	* **`delegator`** {Object} delegator

* **Usage**: 
```js
//해당 화면에서 listview의 delegator설정을 하면 아이템뷰를 생성 할 때 해당 화면의 bindData를 호출해준다.
listview.setDelegator(this);
.
//호출될 bindData를 화면에서 다음과 같은 형식으로 작성하면 된다.
function 화면명:bindData(item, data, alistview)
{
　//item : 생성된 아이템, data: addItem할때 전달받은 데이터 alistview: 리스트뷰 객체
　//아이템에 로드된 뷰의 함수를 호출하는 방식은 다음과 같다.
　item.view.setData();
};
```

<br/>

### setDividerColor( color )

리스트뷰의 구분선 색을 설정한다.

* **Parameters**: 
	* **`color`** {String} RGB 값

* **Usage**: 
```js
listview.setDividerColor("#000000");
```

<br/>

### setItemHeight()

아이템의 높이를 세팅한다.

<br/>

### setScrollArrow( topHeight )

주로 모바일 장치에서 사용되는 함수입니다.<br/>리스트뷰 스크롤 표시가 없을 시 위, 아래 스크롤 아이콘을 표시해줍니다.

* **Parameters**: 
	* **`topHeight`** {Number} 상단에서 위치 값을 넣어줍니다.

* **Usage**: 
```js
listView.setScrollArrow(5);
```

<br/>

### setScrollComp( acomp )

스크롤시 리스트뷰와 관계되어 있는 컴포넌트를 세팅한다.

* **Parameters**: 
	* **`acomp`** {AComponent} 컴포넌트

<br/>

### setSelectClass( selectClass )

아이템 선택시 적용 스타일 클래스를 세팅한다.

* **Parameters**: 
	* **`selectClass`** {String} 스타일 클래스명

* **Usage**: 
```js
listview.setSelectClass("className");
```

<br/>

### beforeInit()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### enableScrollIndicator()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### addItems()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setSelectItem()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getScrollPos()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### updatePosition()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### isMoreScrollLeft()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### isMoreScrollRight()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### removeFromView()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setRealMap()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getRealKey()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### doRealPattern()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### doAddPattern()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### overscrollBehavior()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>

## Events

### scroll( comp, info, e )

스크롤이 될 때 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트 객체
	* **`info`** {HTML Object} 아이템을 자식으로 가지고 있는 스크롤 객체
	* **`e`** {Object} null

### scrollbottom( comp, info, e )

스크롤을 맨 아래로 내렸을 때 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트 객체
	* **`info`** {HTML Object} 아이템을 자식으로 가지고 있는 스크롤 객체
	* **`e`** {Object} null

### scrolltop( comp, info, e )

스크롤을 맨 위로 올렸을 때 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트 객체
	* **`info`** {HTML Object} 아이템을 자식으로 가지고 있는 스크롤 객체
	* **`e`** {Object} null

### select( comp, info, e )

리스트뷰 아이템을 선택할 때 호출되는 함수. info.view는 아이템에 들어있는 뷰 객체이다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {HTML Object} 리스트뷰 아이템 객체
	* **`e`** {Object} 이벤트 객체

<br/>
<br/>

## Attribute

### Item  
* **Height:**  리스트의 아이템 높이를 지정하는 속성입니다. 

### Contents
* **Default Url:** 설명이 필요합니다.
* **add:** 아이템을 추가합니다.
    * **URL:** : 아이템 경로를 설정합니다.
* **edit:** 아이템 경로를 수정합니다.
* **del:** 아이템 경로를 삭제합니다.
* **up:** 아이템의 순서를 한스탭 앞으로 이동합니다. 
* **down:** 아이템의 순서를 한스탭 뒤로 이동합니다. 

### Option
* **Direction:** 설명이 필요합니다.
    * **vertical:** 설명이 필요합니다.
    * **horizontal:** 설명이 필요합니다.
* **selectable:** 설명이 필요합니다.
* **Wrap:** 설명이 필요합니다.

<br/>
