# ATree
**Extends**: [`AComponent`](./AComponent.md)

트리 컴포넌트.

<br/>

## Class Variables

<br/>

## Instance Variables

### iconMap \<String> or \<Array> 

트리에 사용될 아이콘 경로가 저장되어있는 변수. 초기화 시점에 [initTree](#initTree-iconMapUrl-)를 호출해서 지정한다.

<br/>

### selectStyle \<String>

아이템 선택 클래스 이름

```js
this.tree.selectStyle = 'tree-select';
```
<br/>

### overStyle \<String>

드래그 오버 클래스 이름

```js
this.tree.overStyle = 'tree-over';
```

<br/>

### afterStyle \<String>

롱 오버(드래그 오버 1.5초후 발생) 클래스 이름

```js
this.tree.afterStyle = 'tree-after';
```

<br/>

## Class Methods

<br/>

## Instance Methods

### clearSelected() 

선택된 아이템들을 모두 선택해제한다.

<br/>

### deleteAllItems() 

트리에서 루트아이템을 제외한 모든 아이템을 삭제한다.

<br/>

### deleteItem( item, mergeHistory ) 

트리 아이템을 삭제한다.

- `item` \<HTMLElement> 삭제될 트리 아이템
- `mergeHistory` \<Boolean> 현재 offset 히스토리 정보에 추가로 등록할지 여부

```js
//트리에서 아이템을 삭제하는 예시
//트리 아이템명이 'test' 인 아이템을 찾아서 삭제한다.
var item = this.tree.findItemByName('test');
this.tree.deleteItem(item);
```

<br/>

### deselectItem( item ) 

해당 아이템의 선택을 해제한다.

- `item` \<HTMLElement> 트리 아이템
- **Returns** \<Boolean> 성공적으로 선택 해제 될 경우에 true를 반환

<br/>

### expandItem( item, isExpand ) 

폴더 형식의 트리아이템을 펼침상태를 설정한다.

- `item` \<HTMLElement> 트리 아이템
- `isExpand` \<Boolean> 펼침상태 여부

<br/>

### findChildItemByData( data, pItem, compare ) 

매개변수 pItem의 한 단계의 하위 아이템 중에 아이템에 저장된 데이터가 매개변수 data와 일치하는 아이템을 찾아 반환한다.
<br>
매개변수 pItem의 모든 하위 아이템에서 찾으려면 [findItemByData](#findItemByData-data-pItem-compare-)함수를 사용한다.

- `data` \<All> 데이터
- `pItem` \<HTMLElement> 부모 아이템
- `compare` \<function> 내부적으로 데이터를 비교 할때 사용될 필터 함수
- **Returns** \<HTMLElement> 트리 아이템

```js
//매개변수 compare에 대한 예시
//데이터 비교를 할때 text만 비교되도록 한다.
//생략시에는 전체비교를 한다.
var sampleFilter = function(a, b)
{
	if(a.text == b.text) return true;
	else return false;
};

var item = this.tree.findChildItemByData(findData, pItem, sampleFilter);
```

<br/>

### findChildItemByName( name, pItem ) 

매개변수 pItem의 한 단계의 하위 아이템 중에 아이템의 이름이 매개변수 name과 일치하는 아이템을 찾아 반환한다.
<br>
매개변수 pItem의 모든 하위 아이템 중에서 찾으려면 [findItemByName](#findItemByName-name-pItem-)함수를 사용한다.

- `name` \<String> 트리 아이템의 name
- `pItem` \<HTMLElement> 부모 아이템
- **Returns** \<HTMLElement> 트리 아이템

<br/>

### findItemByData( data, pItem, compare ) 

매개변수 pItem의 모든 하위 아이템 중에 아이템에 저장된 데이터가 매개변수 data와 일치하는 아이템을 찾아 반환한다.
<br>
매개변수 pItem의 한 단계의 하위 아이템 중에서 찾으려면 [findChildItemByData](#findChildItemByData-data-pItem-compare-)함수를 사용한다.

- `data` \<Object> 데이터
- `pItem` \<Object> 부모 아이템
- `compare` \<function> 내부적으로 데이터를 비교 할때 사용될 필터 함수
- **Returns** \<Object> 트리 아이템

```js
//매개변수 compare에 대한 예시
//데이터 비교를 할때 text만 비교되도록 한다.
//생략시에는 전체비교를 한다.
var sampleFilter = function(a, b)
{
	if(a.text == b.text) return true;
	else return false;
};

var item = this.tree.findItemByData(findData, pItem, sampleFilter);
```

<br/>

### findItemByName( name, pItem ) 

매개변수 pItem의 모든 하위 아이템 중에 아이템의 이름이 매개변수 name과 일치하는 아이템을 찾아 반환한다.
<br>
매개변수 pItem의 한 단계의 하위 아이템 중에서 찾으려면 [findChildItemByName](#findChildItemByName-name-pItem-)함수를 사용한다.

- `name` \<String> 트리 아이템의 name
- `pItem` \<HTMLElement> 부모 아이템
- **Returns** \<HTMLElement> 트리 아이템

<br/>

### findItemsByNameLike( name, pItem ) 

매개변수 pItem의 모든 하위 아이템들중에 이름에 매개변수 name이 포함되는 아이템들을 배열로 반환한다.

- `name` \<String> 키워드
- `pItem` \<HTMLElement> 부모 아이템
- **Returns** \<HTMLElement Array> 트리 아이템 배열
```js
//아이템 이름에 'cat'이 포함된 모든 아이템을 반환한다.
var items = this.tree.findItemsByNameList('cat', pItem);
```

<br/>

### getChildItems(pItem) 

매개변수 pItem의 하위 아이템을 JQuery Array 형식으로 리턴한다.

- `pItem` \<HTMLElement> 부모 아이템(생략시 루트 아이템 기준)
- **Returns** \<JQuery Array> 

<br/>

### getChildren( pItem, callback ) 

부모아이템의 하위 아이템들에서 콜백함수를 호출한다.

- `pItem` \<HTMLElement> 부모 아이템
- `callback` \<Function> 콜백함수
```js
this.tree.getChildren(pItem, function(item, idx){
    console.log(item, idx);
});
```

<br/>

### getClickedItem() 

가장 마지막에 클릭한 아이템을 반환한다.

- **Returns** \<HTMLElement> 가장 마지막에 클릭한 트리 아이템

<br/>

### getFirstChildItem( pItem ) 

부모아이템의 첫번째 자식 아이템을 반환한다.

- `pItem` \<HTMLElement> 부모 아이템
- **Returns** \<HTMLElement> 트리 아이템

<br/>

### getLastChildItem( pItem ) 

부모아이템의 마지막 자식 아이템을 반환한다.

- `pItem` \<HTMLElement> 부모 아이템
- **Returns** \<HTMLElement> 트리 아이템

<br/>

### getParentItem( item ) 

부모 아이템을 반환한다.

- `item` \<HTMLElement> 트리 아이템
- **Returns** \<HTMLElement> 부모 아이템

<br/>

### getRootItem() 

트리의 루트아이템을 반환한다.

- **Returns** \<HTMLElement>  

<br/>

### getSelectedIndex( item ) 

선택된 아이템의 포지션을 반환한다.

- `item` \<HTMLElement> 트리 아이템
- **Returns** \<Number> 아이템의 위치 인덱스(선택된게 없다면 -1을 리턴)

<br/>

### getSelectedItems() 

트리에서 선택되어 있는 아이템을 배열로 반환한다.

- **Returns** \<Array>

<br/>

### getSelectedParent( mItem ) 

매개변수 mItem 의 부모가 선택되어 있는지 여부를 반환한다.

- `mItem` \<HTMLElement> 트리 아이템.
- **Returns** \<Boolean>

<br/>

### initTree( iconMapUrl ) 

트리를 초기화한다.

- `iconMapUrl` \<String> iconMap파일의 Url

```js
this.tree.initTree('Source/img/tree_item.png');
```

<br/>

### insertItem( pItem, pos, name, data, icon, isExpand, mergeHistory ) 

트리에 아이템을 추가한다.

- `pItem` \<Object>  부모 아이템, null 이면 루트에 추가
- `pos` \<Object> 위치값
- `name` \<String> 트리에 표시될 이름
- `data` \<Object> 유저 데이터
- `icon` \<String> 아이콘
- `isExpand` \<Boolean> 트리 펼침여부
- `mergeHistory` \<String> 각각 다른타겟의 액션을 한 history로 묶고 싶을때 사용한다. true일경우 현재  offset 히스토리 정보에 추가로 등록한다.

- **Returns** \<Object> 새로 생성된 트리 아이템
<br/>

### insertItemObj( itemInfo, isExpand, mergeHistory ) 

트리에 아이템을 추가한다.

- `itemInfo` \<Object> 아이템 정보 JSON
  - pItem : 부모 아이템, null 이면 루트에 추가
  - pos : 위치값
  - name : 트리에 표시될 이름
  - data : 유저 데이터
  - icon : 아이콘
  - comment : 코멘트값
- `isExpand` \<Boolean> 펼침여부
- `mergeHistory` \<String> 각각 다른타겟의 액션을 한 history로 묶고 싶을때 사용한다. true일경우 현재offset 히스토리 정보에 추가로 등록한다.

- **Returns** \<Object> 새로 생성된 트리 아이템

```js
this.tree.insertItemObj({
    pItem: null,      				//부모아이템
    pos : 0,          				//위치값
    name: 'item1',    				//이름
    data: {},         				//데이터
	icon: 'Source/icon.png',        //아이콘
	comment: '코멘트'				//코멘트
}, false, false);
```

<br/>

### isExistRoot() 

선택된 아이템들중에 root Item이 포함되어있는지 여부를 반환한다.

- **Returns** \<Boolean> 포함 여부

<br/>

### isMovePossible( moveItem, pItem ) 

트리아이템이 부모 아이템으로 이동 가능 여부를 반환한다.

- `moveItem` \<HTMLElement> 트리 아이템
- `pItem` \<HTMLElement> 부모 아이템
- **Returns** \<Boolean> 이동 가능 여부

<br/>

### moveItem( dropItem, mItems, isInsertAfter ) 

매개변수 mItems의 아이템들을 dropItem으로 이동시킨다. 자식 아이템이 있을 경우 같이 이동한다.

- `dropItem` \<HTMLElement> 이동 될 기준 아이템
- `mItems` \<HTMLElement> 이동 할 아이템들의 배열
- `isInsertAfter` \<Boolean> 위치값
  - true : dropItem의 앞으로 이동된다. 
  - false: dropItem의 자식노드의 맨끝에 삽입됩니다. 

```js
var items = this.tree.getSelectedItems();
this.tree.moveItem(dropItem, items, true);
```

<br/>

### redoTree()

트리의 히스토리 redo 기능을 호출한다.

<br/>

### rename( item, name ) 

아이템의 표시될 이름을 변경한다.

- `item` \<HTMLElement> 트리 아이템.
- `name` \<String> 변경될 라벨의 text

<br/>

### scrollToItem( item ) 

해당 아이템의 보이도록 스크롤 시킨다.

- `pItem` \<HTMLElement> 트리 아이템

<br/>

### selectItem( item, isMulti, e ) 

아이템을 선택상태로 설정한다.

- `item` \<HTMLElement> 트리 아이템
- `isMulti` \<Boolean> 다중 아이템 선택 가능 여부
- `e` \<JQuery Event> 이벤트 객체

<br/>

### selectNextItem() 

트리에서 바로 다음 아이템을 선택한다.

<br/>

### selectPrevItem() 

트리에서 바로 이전 아이템을 선택한다.

<br/>

### setItem( item, itemInfo ) 

info 데이터로 아이템을 설정한다.

- `item` \<HTMLElement> 트리 아이템
- `itemInfo` \<Object> 아이템에 세팅할 정보
  - name : 트리에 표시할 이름
  - data : 사용자 데이터
  - icon : 트리에 사용할 아이콘

```js
this.tree.setItem(item, {
    name: 'newItem1',
    data: {},
    icon: ''
});
```

<br/>

### setItemComment( item, comment ) 

아이템 name 오른쪽에 코멘트 라벨을 추가한다.

- `pItem` \<HTMLElement> 트리 아이템
- `comment` \<String> 코멘트 text
```js
this.tree.setItemComment(item, '아이템 설명');
```

<br/>

### startUseHistory() 

히스토리 사용을 시작한다.

<br/>

### setDelegator( delegator ) 

delegator를 지정한다. 트리 컴포넌트에서 delegator는 아이템이 펼치거나 접히는 이벤트를 itemExpandManage함수를 통해 전달받을수있다.

- `delegator` \<Object> delegator 객체

```js
//setDelegator를 이용해서 
//itemExpandManage를 전달 받는 예시
class SampleView()
{
	super();
}
extends AView;

function SampleView*onInitDone()
{
	super.onInitDone();

	//delegator를 사용할 트리 컴포넌트에 delegator 세팅
	this.sampleTree.setDelegator(this);
	...
};

//setDelegator를 이용해서 객체를 지정한후엔
//itemExpandManage함수를 통해 전달받을수있다.
function SampleView*itemExpandManage(isExpand, item)
{
	//isExpand : 접힘, 펼침 여부
	//item : 트리 아이템
	...
};
```

<br/>

### undoTree() 

트리의 히스토리 undo 기능을 호출한다.

<br/>

## Events

### dbclick( comp, info, e )

더블클릭시 발생한다.

- `comp` \<ATree> 트리 컴포넌트
- `info` \<HTMLElement> 트리 아이템
- `e` \<JQuery Event> Event 객체

<br/>

### select( comp, info, e )

선택하면 발생한다.

- `comp` \<ATree> 트리 컴포넌트
- `info` \<HTMLElement> 트리 아이템
- `e` \<JQuery Event> Event 객체

<br/>

