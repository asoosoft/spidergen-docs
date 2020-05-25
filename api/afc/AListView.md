# AListView
**Extends**: [`AComponent`](AComponent.html#acomponent)

리스트뷰 컴포넌트

<br/>
<br/>

## Class Variables

<br/>
<br/>

## Instance Variables

### defaultUrl \<String>

리스트뷰에 추가되는 기본 뷰 url

<br/>

### delegator \<Object>

리스트뷰의 delegate 함수를 처리할 객체

<br/>

### dividerColor \<String>

구분선의 RGB 색

<br/>

### itemHeight \<String>

리스트뷰 아이템의 높이

<br/>

### scrollComp \<[AComponent](AComponent.html#acomponent)>

리스트뷰와 같이 스크롤 될 컴포넌트

<br/>

### selectClass \<String>

아이템 선택시 적용 스타일 클래스

<br/>

### selectItem \<HTML Object>

선택되어진 아이템 객체

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### addItem( url, dataArray, isPrepend )

리스트뷰에 아이템을 추가한다. dataArray 개수만큼 url 의 뷰리소스가 리스트뷰에 추가되며 데이터 매핑은 bindData 가 호출되어질 때 dataArray 가 넘어가며 사용자가 직접 하도록 한다.

- `url` \<String> 아이템에 추가될 뷰 리소스 url
- `dataArray` \<Array> 화면과 매핑될 데이터객체 배열
- `isPrepend` \<Boolean> 맨 앞에 추가할 지 여부

```js
listview.setDelegator(this);
listview.addItem('Source/item.lay',['a','bb','ccc']);
```

<br/>

### addItems( urlArr, dataArr, isPrepend, asyncCallback )

- `urlArr` \<Array> 추가 할 뷰의 URL(String) 배열
- `dataArr` \<Array> 추가 할 뷰의 데이터 배열
- `isPrepend` \<Boolean> 추가 할 위치 (true : 앞, false : 뒤)
- `asyncCallback` \<Boolean> or \<Function> 동기화 여부 및 동기화 시 콜백 함수. 받는 인수는 추가된 아이템의 배열이다.

```js
var urlArr = ['Source/view1.lay', 'Source/view2.lay', 'Source/view3.lay']
var dataArr = [1, 2, 3]
listview.addItems(urlArr, dataArr, true, function(items)
{
	for(var i in items)
	{
		console.log(items[i]);
	}
})
```

<br/>

### callSubActiveEvent( funcName, isFirst )

하위 뷰들의 Active관련 함수를 실행한다.<br/><br/>단, 리스트뷰 옵션에서 isUpdatePosition가 true일때만 동작한다.

- `funcName` \<String> active 관련 함수명
- `isFirst` \<Boolean> 최초 실행여부

<br/>

### createBackup( maxRow, restoreCount )

리스트뷰 내에 아이템들을 백업한다.

- `maxRow` \<Number> 스크롤될때 아이템 인덱스 수
- `restoreCount` \<Number> 백업 저장할 수

<br/>

### createItems( url, dataArray, posItem, isPrepend )

리스트뷰에 아이템을 추가한다.<br/>dataArray 개수만큼 url의 뷰리소스가 리스트뷰에 추가되며 데이터 매핑은 bindData가 호출되어질때 dataArray가 넘어가며 사용자가 직접 하도록 한다.

- `url` \<String> 아이템에 추가될 뷰 리소스 url
- `dataArray` \<Array> 화면과 매핑될 데이터객체 배열
- `posItem` \<HTML Object> 아이템을 추가할 위치가 되는 아이템(생략될 경우 리스트뷰의 맨 앞이나 맨 뒤에 추가된다)
- `isPrepend` \<Boolean> 아이템을 맨 앞에 추가하거나 맨 뒤에 추가할지(posItem이 존재하면 posItem 앞이나 뒤에 추가한다)

<br/>

### destroyBackup()

백업기능을 파기한다.

<br/>

### enableScrlManager()

ScrollManager 의 자체 스크롤이 적용되도록 한다.

<br/>

### getBottomItem()

리스트뷰 내의 아이템들 중 마지막 아이템을 jQuery 객체로 반환한다.<br/><br/>getLastItem() 함수와 동일한다.

- **Returns** \<HTML Object>

<br/>

### getDefaultUrl()

리스트뷰의 아이템뷰에서 로드할 default url을 리턴한다.

- **Returns** \<String>

<br/>

### getFirstItem()

리스트뷰 내의 아이템들 중 첫번째 아이템을 jQuery 객체로 반환한다.<br/>getTopItem() 함수와 동일하다.

- **Returns** \<Object>

<br/>

### getItem( index )

리스트뷰의 특정 인덱스의 아이템 객체를 리턴한다.

- `index` \<Number> 아이템 인덱스
- **Returns** \<HTMLObject>

<br/>

### getItemCount()

리스트뷰 내의 모든 아이템의 수를 반환한다.<br/>getTotalCount() 함수와 동일한다.

- **Returns** \<Number>

<br/>

### getItems()

리스트뷰내의 모든 아이템들을 jQuery 객체로 리턴한다.

- **Returns** \<JQuery Object>

<br/>

### getLastItem()

리스트뷰 내의 아이템들 중 마지막 아이템을 jQuery 객체로 반환한다.<br/>getBottomItem() 함수와 동일한다.

- **Returns** \<Object>

<br/>

### getRealKey()

데이터 중 setRealMap을 통해 지정한 실시간 필드명에 해당하는 값을 가져온다.

* `data`  \<Object> 데이터
* **Returns** \<String> 실시간 키값

<br/>

### getScrollPos()

현재 스크롤의 위치를 리턴한다.

- **Returns** \<Number>

<br/>

### getSelectItem()

현재 선택되어져 있는 아이템 객체를 리턴한다.

- **Returns** \<HTMLObject>

<br/>

### getTopItem()

리스트뷰 내의 아이템들 중 첫번째 아이템을 jQuery 객체로 반환한다. <br/>getFirstItem() 함수와 동일한다.

- **Returns** \<HTML Object>

<br/>

### getTotalCount()

리스트뷰 내의 모든 아이템의 수를 반환한다.<br/>getItemCount() 함수와 동일한다.

<br/>

### indexOfItem( item )

특정 아이템의 인덱스를 얻어온다.

- `item` \<HTML Object> 인덱스를 얻을 아이템 객체
- **Returns** \<Number>

```js
var item = listview.getSelectItem();
listview.indexOfItem(item);
```

<br/>

### insertItem( url, dataArray, posItem, isPrepend )

리스트뷰의 특정 위치에 아이템을 삽입한다.

- `url` \<String> 아이템에 추가될 뷰 리소스 url
- `dataArray` \<Array> 데이터 배열
- `posItem` \<HTML Object> 아이템을 추가할 위치가 되는 아이템(생략될 경우 리스트뷰의 맨 앞이나 맨 뒤에 추가된다.)
- `isPrepend` \<Boolean> true: 앞 false : 뒤 / 아이템을 맨 앞에 추가하거나 맨 뒤에 추가할지(posItem 이 존재하면 posItem 앞이나 뒤에 추가한다.)

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

- **Returns** \<Boolean>

<br/>

### isMoreScrollLeft()

좌측으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

<br/>

### isMoreScrollRight()

우측으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

<br/>

### isMoreScrollTop()

상단으로 추가적인 스크롤이 가능한지 여부를 리턴한다.

- **Returns** \<Boolean>

<br/>

### isScroll()

현재 스크롤이 가능한 상태인지 여부를 리턴한다.

- **Returns** \<Boolean>

<br/>

### itemInsertManage( item, posItem, isPrepend )

리스트뷰에 추가되는 아이템의 실제 구현부입니다.

- `item` \<HTML Object> 추가될 아이템
- `posItem` \<HTML Object> 아이템을 추가할 위치가 되는 아이템(생략될 경우 리스트뷰의 맨 앞이나 맨 뒤에 추가된다)
- `isPrepend` \<Boolean> 아이템을 맨 앞에 추가하거나 맨 뒤에 추가할지(posItem이 존재하면 posItem 앞이나 뒤에 추가한다)

<br/>

### moveBottomItems( items )

리스트뷰 내의 특정 아이템들을 맨 아래로 옮긴다.

- `items` \<HTML Object> 아이템객체 배열

```js
var items = listview.getItems();
listview.moveBottomItems(items);
```

<br/>

### moveDownItems( items )

리스트뷰 내의 특정 아이템들를 바로 아래 아이템의 아래로 옮긴다.

- `items` \<HTML Object> 아이템 객체 배열


```js
var items = listview.getItems();
listview.moveDownItems(items);
```

<br/>

### moveTopItems( items )

리스트뷰 내의 특정 아이템들을 맨 위로 옮긴다.

- `items` \<HTML Object> 아이템객체 배열

```js
var items = listview.getItems();
listview.moveTopItems(items);
```

<br/>

### moveUpItems( items )

리스트뷰 내의 특정 아이템들를 바로 위 아이템의 위로 옮긴다.

- `items` \<HTML Object> 아이템객체 배열


```js
var items = listview.getItems();
listview.moveUpItems(items);
```

<br/>

### overscrollBehavior()

리스트뷰의 enableScrlManager 를 호출한 상태에서 스크롤이 상단 또는 하단에 이르러서 더이상 스크롤이 되지 않을 때 부모 엘리먼트의 스크롤이 되어야 할때 호출하는 함수.
<br/>단, 상위 컴포넌트에서도 enableScrlManager 가 호출되어있어야 제대로 동작함.

* `disableScrlManager` 부모 엘리먼트 스크롤매니저

```js
var scrlMgr = this.view.enableScrlManagerY();
listview.enableScrlManager();
listview.overscrollBehavior(scrlMgr);
```

<br/>

### refreshListView()

리스트뷰의 자식 item 항목들을 갱신하여 보여주는 함수

<br/>

### removeAllItems()

리스트뷰 내의 모든 아이템을 삭제한다.

<br/>

### removeItem( item )

리스트뷰에서 특정 아이템을 삭제한다.

- `item` \<HTML Object> 삭제할 아이템 객체


```js
var item = listview.getSelectItem();
listview.removeItem(item);
```

<br/>

### removeItemByIndex( index )

특정 아이템을 인덱스로 삭제한다.

- `index` \<Number> 삭제할 인덱스

<br/>

### restoreScrollPos()

리스트뷰를 저장해둔 위치로 스크롤한다. 위치를 저장하려면 saveScrollPos함수를 호출한다.

<br/>

### saveScrollPos()

현재 리스트뷰의 스크롤 위치를 저장해둔다. 리턴값이 없고 내부적으로 저장한다. 다시 불러올떄는 restoreScrollPos함수를 호출한다.

<br/>

### scrollBottomManage()

스크롤이 최하단에 위치하였는지 여부를 리턴하는 함수이다.

- **Returns** \<boolean>

<br/>

### scrollImplement()

자체적으로 스크롤 구현한다. touchStart, touchMove, touchUp 이벤트가 동작한다.

<br/>

### scrollOffset( offset )

스크롤의 y좌표값에서 offset 만큼 더한다.

- `offset` \<Number> 더해지는 값

<br/>

### scrollTo( pos )

리스트뷰를 pos 좌표 위치로 스크롤한다.

- `pos` \<Number<> y좌표값

<br/>

### scrollToBottom()

리스트뷰를 최하단으로 스크롤한다.

<br/>

### scrollTopManage()

스크롤이 최상단에 위치하였는지 여부를 리턴하는 함수이다.

- **Returns** \<boolean>

<br/>

### scrollToTop()

리스트뷰를 최상단으로 스크롤한다.

<br/>

### setDefaultUrl( URL )

리스트뷰의 아이템뷰에서 로드할 default url을 설정한다. addItem 함수를 호출할때 URL값이 null이면 setDefaultUrl 함수로 저장한 URL을 사용한다. default url 마저도 없으면 아이템은 추가되지 않는다.

- `URL` \<String> 레이아웃의 URL

```js
listview.setLoadUrl('Source/item.lay');
listview.addItem(null, ['a','bb','ccc']);
```

<br/>

### setDelegator( delegator )

delegate 함수 처리 객체를 세팅한다.

- `delegator` \<Object> delegator

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

- `color` \<String> RGB 값

```js
listview.setDividerColor("#000000");
```

<br/>

### setItemHeight()

아이템의 높이를 세팅한다.

<br/>

### setRealMap()

리얼맵이 작동하도록 환경을 셋팅한다. setQueryData 에서 사용(this.realMap 변수 설명 참조)

* `realField` \<String> 실시간 키 수신 필드

<br/>

### setScrollArrow( topHeight )

주로 모바일 장치에서 사용되는 함수이다.<br/>리스트뷰 스크롤 표시가 없을 시 위, 아래 스크롤 아이콘을 표시해준다.

- `topHeight` \<Number> 상단에서 떨어질 위치값

<br/>

### setScrollComp( acomp )

스크롤시 리스트뷰와 관계되어 있는 컴포넌트를 세팅한다.

- `acomp` \<[AComponent](AComponent.html#acomponent)> 컴포넌트

<br/>

### setSelectClass( selectClass )

아이템 선택시 적용 스타일 클래스를 세팅한다.

- `selectClass` \<String> 스타일 클래스명

<br/>

### setSelectItem( item )

특정 아이템이 선택 되도록 한다.

- `item` \<HTML Object> 아이템 객체

```js
var item = listview.getItem(0);
listview.setSelectItem(item);
```

<br/>
<br/>

## Events

공통부분은 설명은 \<[AComponent Events](AComponent.html#events)> 참조

### scroll( comp, info, e )

스크롤이 될 때 호출되는 이벤트 함수.

- `info` \<HTML Object> 아이템을 자식으로 가지고 있는 스크롤 객체

### scrollbottom( comp, info, e )

스크롤을 맨 아래로 내렸을 때 호출되는 이벤트 함수.

- `info` \<HTML Object> 아이템을 자식으로 가지고 있는 스크롤 객체

### scrolltop( comp, info, e )

스크롤을 맨 위로 올렸을 때 호출되는 이벤트 함수.

- `info` \<HTML Object> 아이템을 자식으로 가지고 있는 스크롤 객체

### select( comp, info, e )

리스트뷰 아이템을 선택할 때 호출되는 함수. info.view는 아이템에 들어있는 뷰 객체이다.

- `info` \<HTML Object> 리스트뷰 아이템 객체

<br/>
<br/>

## Attribute

### Item  
* **Height:**  리스트의 아이템 높이를 지정하는 속성

### Contents
* **Default Url:** 아이템 추가 시 기본으로 세팅 될 URL
* **add:** 아이템을 추가한다.
    * **URL:** : 아이템 경로를 설정한다.
* **edit:** 아이템 경로를 수정한다.
* **del:** 아이템 경로를 삭제한다.
* **up:** 아이템의 순서를 한스탭 앞으로 이동한다.
* **down:** 아이템의 순서를 한스탭 뒤로 이동한다.

### Option
* **Direction:** 스크롤 방향을 설정한다.
    * **vertical:** 상하 방향
    * **horizontal:** 좌우 방향
* **selectable:** 선택 가능 여부 옵션
* **Wrap:** 가로로 배치하다 공간이 없으면 개행하여 다시 추가한다.

<br/>
