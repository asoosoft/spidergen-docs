# ATree
> **Extends**: `AComponent`

ATree

<br/>

## Methods

### clearSelected()

트리의 모든 선택된 아이템을 선택 해제상태로 변경한다.

* **Usage**: 
```js
this.tree.clearSelected();
```

<br/>

### deleteAllItems()

트리에서 루트아이템을 제외한 모든 아이템을 삭제한다.

* **Usage**: 
```js
this.tree.deleteAllItems();
```

<br/>

### deleteItem( item, mergeHistory )

트리 아이템을 삭제한다.

* **Parameters**: 
	* **`item`** {String} 삭제될 트리 아이템
	* **`mergeHistory`** {Boolean} 현재  offset 히스토리 정보에 추가로 등록할지 여부

* **Usage**: 
```js
this.tree.deleteItem(item, false);
```

<br/>

### deselectItem( item )

해당 아이템의  선택상태를 해제한다.

* **Returns**: boolean

* **Parameters**: 
	* **`item`** {String} 트리아이템

* **Usage**: 
```js
this.tree.deselectItem(item);
```

<br/>

### expandDisable( expItem )

아이템의 접기 / 펴기 기능을 비활성화 한다.

* **Parameters**: 
	* **`expItem`** {Object} 트리 아이템

* **Usage**: 
```js
this.tree.expandDisable(item);
```

<br/>

### expandEnable( expItem, subTree, isExpand )

아이템의 접기 / 펴기 기능을 활성화 한다.

* **Parameters**: 
	* **`expItem`** {Object} 트리 아이템
	* **`subTree`** {Object} 하위 트리
	* **`isExpand`** {Boolean} true: 펼치기 false: 접기

* **Usage**: 
```js
this.tree.expandEnable(item, );
```

<br/>

### expandItem( item, isExpand )

폴더 형식의 트리아이템을 펼침상태를 설정한다.

* **Parameters**: 
	* **`item`** {Object} 트리아이템
	* **`isExpand`** {Boolean} 펼침상태 여부

* **Usage**: 
```js
this.tree.expandItem(item, true);
```

<br/>

### findChildItemByData( data, pItem, compare )

매개변수 pItem 의 바로 하위 아이템중 매개변수 data 가 일치하는 아이템을 찾아 반환한다.

* **Returns**: Object

* **Parameters**: 
	* **`data`** {Object} data
	* **`pItem`** {Object} 검색을 할 위치
	* **`compare`** {Boolean} compare함수 사용여부

* **Usage**: 
```js
var item = this.tree.findChildItemByData(findData, pItem, true);
```

<br/>

### findChildItemByName( name, pItem )

매개변수 pItem 의 바로 하위 아이템중 매개변수 name이 일치하는 아이템을 찾아 반환한다.

* **Returns**: object

* **Parameters**: 
	* **`name`** {String} 트리 아이템의 name
	* **`pItem`** {Object} 검색을 할 위치

* **Usage**: 
```js
var item = this.tree.findChildItemByName('item1', pItem);
```

<br/>

### findItemByData( data, pItem, compare )

매개변수 pItem 의 하위 모든 아이템중 매개변수 data 가 일치하는 아이템을 찾아 반환한다.

* **Returns**: Object

* **Parameters**: 
	* **`data`** {String} 데이터
	* **`pItem`** {String} 검색을 할 위치
	* **`compare`** {String} compare

* **Usage**: 
```js
var item = this.tree.findItemByData(findData, pItem, true);
```

<br/>

### findItemByName( name, pItem )

매개변수 pItem 의 하위 모든 아이템중 매개변수 name이 일치하는 아이템을 찾아 반환한다.

* **Returns**: Object

* **Parameters**: 
	* **`name`** {String} 트리 아이템의 name
	* **`pItem`** {Object} 검색을 할 위치

* **Usage**: 
```js
var item = this.tree.findItemByName('item1', pItem);
```

<br/>

### findItemsByNameLike( name, pItem )

부모 아이템의 하위 아이템들중 매개변수 name 이 이름에 포함되는 아이템들을 반환한다.

* **Returns**: Array

* **Parameters**: 
	* **`name`** {String} name
	* **`pItem`** {Object} 검색이 될 위치

* **Usage**: 
```js
var items = this.tree.findItemsByNameList('item', pItem);
```

<br/>

### getChildItems( pItem )

pItem의 하위 아이템을 반환한다.

* **Returns**: Array

* **Parameters**: 
	* **`pItem`** {String} 부모아이템 (null일 경우 루트)

* **Usage**: 
```js
var items = this.tree.getChildItems(pItem);
```

<br/>

### getChildren( pItem, callback )

부모아이템의 하위 아이템들에서 콜백함수를 호출한다.

* **Parameters**: 
	* **`pItem`** {String} 부모 아이템
	* **`callback`** {Function} 콜백함수

* **Usage**: 
```js
var callback = function(item, idx) {
    console.log(item, idx);
};
this.tree.getChildren(pItem, callback);
```

<br/>

### getClickedItem()

가장 마지막에 클릭한 아이템을 반환한다.

* **Returns**: obJect

* **Usage**: 
```js
var item = this.tree.getClickedItem();
```

<br/>

### getFirstChildItem( pItem )

부모아이템의 첫번째 자식 아이템을 반환한다.

* **Returns**: Object

* **Parameters**: 
	* **`pItem`** {String} 부모 아이템

* **Usage**: 
```js
var item = this.tree.getFirstChildItem(pItem);
```

<br/>

### getLastChildItem( pItem )

부모아이템의 마지막 자식 아이템을 반환한다.

* **Returns**: Object

* **Parameters**: 
	* **`pItem`** {Object} 부모아이템

* **Usage**: 
```js
var item = this.tree.getLastChildItem(pItem);
```

<br/>

### getParentItem( item )

부모 아이템을 반환한다.

* **Returns**: Object

* **Parameters**: 
	* **`item`** {Object} 트리 아이템

* **Usage**: 
```js
var p = this.tree.getParentItem(item);
```

<br/>

### getRootItem()

트리의 루트아이템을 반환한다.

* **Returns**: object

* **Usage**: 
```js
var root = this.tree.getRootItem();
```

<br/>

### getSelectedIndex( item )

선택된 아이템의 포지션을 반환한다.<br/>선택된 아이템이 없다면 -1을 반환한다.

* **Returns**: Number

* **Parameters**: 
	* **`item`** {String} 트리 아이템

* **Usage**: 
```js
var idx = this.tree.getSelectedIndex();
```

<br/>

### getSelectedItems()

트리에서 선택되어 있는 아이템을 배열로 반환한다.

* **Returns**: Array

* **Usage**: 
```js
var items = this.tree.getSelectedItems();
```

<br/>

### getSelectedParent( mItem )

매개변수 mItem 의 부모가 선택되어 있는지 여부를 반환한다.

* **Returns**: boolean

* **Parameters**: 
	* **`mItem`** {Object} 트리 아이템.

* **Usage**: 
```js
var b = this.tree.getSelectedParent(item);
```

<br/>

### initTree( iconMapUrl )

트리를 초기화한다.

* **Parameters**: 
	* **`iconMapUrl`** {String} iconMap파일의 Url

* **Usage**: 
```js
this.tree.initTree();
```

<br/>

### insertItem( pItem, pos, name, data, icon, isExpand, mergeHistory )

아이템을 추가한다.

* **Returns**: object

* **Parameters**: 
	* **`pItem`** {Object} 부모 아이템
	* **`pos`** {Object} 위치값
	* **`name`** {String} 트리에 표시될 이름
	* **`data`** {Object} 유저 데이터
	* **`icon`** {String} 아이콘
	* **`isExpand`** {Boolean} 트리 펼침여부
	* **`mergeHistory`** {String} 각각 다른타겟의 액션을 한 history로 묶고 싶을때 사용한다. true일경우 현재  offset 히스토리 정보에 추가로 등록한다.

* **Usage**: 
```js
this.tree.insertItem(null, 0, 'item1', {}, '', false, false);
```

<br/>

### insertItemObj( itemInfo, isExpand, mergeHistory )

아이템을 추가한다.

* **Returns**: Object

* **Parameters**: 
	* **`itemInfo`** {Object} 아이템 정보
	* **`isExpand`** {Boolean} 펼침여부
	* **`mergeHistory`** {String} 각각 다른타겟의 액션을 한 history로 묶고 싶을때 사용한다. true일경우 현재offset 히스토리 정보에 추가로 등록한다.

* **Usage**: 
```js
this.tree.insertItemObj({
    null,       //부모아이템
    0,          //위치값
    'item1',    //이름
    {},         //데이터
    'Source/icon.png'          //아이콘
}, false, false);
```

<br/>

### isExistRoot()

선택된 아이템들중에 root Item이 포함되어있는지 여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var b = this.tree.isExistRoot();
```

<br/>

### isMovePossible( moveItem, pItem )

아이템의 이동 가능 여부를 반환한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`moveItem`** {Object} 이동할 아이템
	* **`pItem`** {Object} 부모 아이템

* **Usage**: 
```js
var b = this.tree.isMovePossible(item, pItem);
```

<br/>

### moveItem( dropItem, mItems, isInsertAfter )

매개변수 mItems의 아이템들을 dropItem으로 이동시킨다. 자식 아이템이 있을 경우 같이 이동한다.

* **Parameters**: 
	* **`dropItem`** {Object} mItems들이 이곳으로 이동됩니다.
	* **`mItems`** {Array} 이동 할 아이템들의 배열
	* **`isInsertAfter`** {Boolean} true : dropItem의 앞으로 이동된다. false: dropItem의 자식노드의 맨끝에 삽입됩니다.

* **Usage**: 
```js
var items = this.tree.getSelectedItems();
this.tree.moveItem(dropItem, items,true);
```

<br/>

### redoTree()

트리의 히스토리 redo 기능을 호출한다.

* **Usage**: 
```js
this.tree.redoTree();
```

<br/>

### rename( item, name )

아이템의 표시될 이름을 변경한다.

* **Parameters**: 
	* **`item`** {Object} 트리 아이템
	* **`name`** {String} 변경될 라벨의 text

* **Usage**: 
```js
this.tree.rename(item, '아이템1');
```

<br/>

### scrollToItem( item )

해당 아이템을 스크롤 시킨다.

* **Parameters**: 
	* **`item`** {Object} 트리 아이템

* **Usage**: 
```js
this.tree.scrollToItem(item);
```

<br/>

### selectItem( item, isMulti, e )

아이템을 선택상태로 설정한다.

* **Parameters**: 
	* **`item`** {Object} 트리 아이템
	* **`isMulti`** {Boolean} 여러개 선택 여부
	* **`e`** {Object} 이벤트 info

* **Usage**: 
```js
this.tree.selectItem(item, false);
```

<br/>

### selectNextItem()

트리에서 바로 다음 아이템을 선택한다.

* **Usage**: 
```js
this.tree.selectNextItem();
```

<br/>

### selectPrevItem()

트리에서 바로 이전 아이템을 선택한다.

* **Usage**: 
```js
this.tree.selectPrevItem();
```

<br/>

### setItem( item, itemInfo )

info 데이터로 아이템을 설정한다.

* **Parameters**: 
	* **`item`** {Object} 트리 아이템
	* **`itemInfo`** {Object} 아이템에 세팅할 정보 (name : 트리에 표시할 이름, data : 사용자 데이터,icon : 트리에 사용할 아이콘)

* **Usage**: 
```js
this.tree.setItem(item, {
    name: 'newItem1',
    data: {},
    icon: ''
});
```

<br/>

### setItemComment( item, comment )

아이템 name 오른쪽에 라벨을 추가한다.

* **Parameters**: 
	* **`item`** {Object} 트리 아이템
	* **`comment`** {String} 라벨에 들어갈 text

* **Usage**: 
```js
this.tree.setItemComment(item, '아이템1 라벨');
```

<br/>

### setOption( option )

트리의 속성옵션을 설정한다.

* **Parameters**: 
	* **`option`** {Object} 옵션정보

* **Usage**: 
```js
this.tree.setOption({
    isSingleSelect: false,       //ctrl 키를 누르고 선택해도 하나만 선택된다. 
    isFullSelect: false,            //아이템 선택시 선택표시가 라인 전체로 표시된다.
    isDraggable: true,   	    //트리 드래그 여부
    useHistory: false,   	    //히스토리 사용여부(undo, redo)
    dragIcon: './Source/img/drag.png'	//드래그 아이콘      
});
```

<br/>

### startUseHistory()

히스토리 사용을 시작한다.

* **Usage**: 
```js
this.tree.startUseHistory();
```

<br/>

### undoTree()

트리의 히스토리 undo 기능을 호출한다.

* **Usage**: 
```js
this.tree.undoTree();
```

<br/>
<br/>
## Events


### dbclick( comp, info, e )

더블클릭시 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {HTML Object} 아이템 객체
	* **`e`** {Object} 이벤트 객체

### select( comp, info, e )

선택하면 발생한다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {HTML Object} 아이템 객체
	* **`e`** {Object} 이벤트 객체

<br/>

