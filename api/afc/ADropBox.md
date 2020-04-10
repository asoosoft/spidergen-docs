# ADropBox
> **Extends**: `AComponent`

드랍박스

<br/>

## Properties


### openDir

드랍박스를 펼칠 방향 (true : 하단으로 펼침, false: 상단으로 펼침)

* **Type**: `Boolean`
* **Default**: `true`

<br/>

### items



* **Type**: ``
* **Default**: ``

<br/>


### selIndex



* **Type**: ``
* **Default**: ``

<br/>


### dropBoxH



* **Type**: ``
* **Default**: ``

<br/>


### selectClass



* **Type**: ``
* **Default**: ``

<br/>


### normalClass



* **Type**: ``
* **Default**: ``

<br/>


### focusClass



* **Type**: ``
* **Default**: ``

<br/>


### textfield



* **Type**: ``
* **Default**: ``

<br/>


### dropBtn



* **Type**: ``
* **Default**: ``

<br/>


### useDropBox



* **Type**: ``
* **Default**: ``

<br/>


### listPopup



* **Type**: ``
* **Default**: ``

<br/>


### scrollArea



* **Type**: ``
* **Default**: ``

<br/>


### isEnableSM



* **Type**: ``
* **Default**: ``

<br/>

### isTabable



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### addItem( text, data )

아이템을 추가한다.

* **Returns**: Object

* **Parameters**: 
	* **`text`** {String} 아이템명
	* **`data`** {All} 아이템데이터

* **Usage**: 
```js
var data; //아이템에 저장될 데이터, 형식 자유
dropBox.addItem('컴포넌트에 보이는 이름', data);
```

<br/>

### bindData( ulObj )

읽기 모드가 아닌경우에 드랍박스 input부분에 검색어가 있는 경우에 검색처리를 해주는 함수이다.

* **Returns**: boolean

* **Parameters**: 
	* **`ulObj`** {HTML Object} ul object

<br/>

### clearSelectItem()

선택된 아이템을 초기화한다. (선택된게 없게함)

* **Usage**: 
```js
dropBox.clearSelectItem();
```

<br/>

### enableScrlManagerY()

드랍박스의 UL Object가 스크롤이 가능하게 한다.

<br/>

### getDataType()

드랍박스의 텍스트필드타입을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = dropBox.getDataType();
```

<br/>

### getEditText()

드랍박스의 텍스트를 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = dropBox.getEditText();
```

<br/>

### getItem( index )

해당 위치의 아이템을 리턴한다.

* **Returns**: Object:

* **Parameters**: 
	* **`index`** {String} 아이템 위치

* **Usage**: 
```js
var result = dropBox.getItem(2);
```

<br/>

### getItemData( index )

해당 위치의 아이템 데이터를 리턴한다.

* **Returns**: String

* **Parameters**: 
	* **`index`** {String} 아이템 위치

* **Usage**: 
```js
var result = dropBox.getItemData(2);
```

<br/>

### getItems()

모든 아이템을 리턴합니다.

* **Returns**: Array Object

* **Usage**: 
```js
var resultArr = dropBox.getItems();
```

<br/>

### getItemSize()

아이템의 크기를 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var size = dropBox.getItemSize();
```

<br/>

### getItemText( index )

해당 위치의 아이템text를 리턴한다.

* **Returns**: String

* **Parameters**: 
	* **`index`** {String} 아이템위치

* **Usage**: 
```js
var result = dropBox.getItemText(3);
```

<br/>

### getMappingCount()

매핑가능한 갯수를 리턴한다.

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조

<br/>

### getSelectedIndex()

선택된 아이템의 위치를 리턴합니다.

* **Returns**: Number

* **Usage**: 
```js
var index = dropBox.getSelectedIndex();
```

<br/>

### getSelectedItem()

선택된 아이템의 객체를 리턴한다.

* **Returns**: Object

* **Usage**: 
```js
var item = dropBox.getSelectedItem();
```

<br/>

### getSelectedItemData( key )

선택된 아이템 데이터를 리턴한다.

* **Returns**: Object

* **Parameters**: 
	* **`key`** {String} 키값

* **Usage**: 
```js
var itemData = dropBox.getSelectedItemData();
```

<br/>

### getSelectedItemText()

선택된 아이템명을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = dropBox.getSelectedItemText();
```

<br/>

### getTextAlign()

드랍박스의 텍스트 정렬 속성을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = dropBox.getTextAlign();
```

<br/>

### indexOfData( data )

입력된 data와 아이템의 데이터가 같은 아이템위치를 리턴한다.

* **Returns**: Number

* **Parameters**: 
	* **`data`** {String} 아이템데이터

* **Usage**: 
```js
var index = dropbox.indexOfData(data);
```

<br/>

### indexOfText( text )

입력된 text와 아이템text가 같은 아이템위치를 리턴한다.

* **Returns**: Number

* **Parameters**: 
	* **`text`** {String} 아이템명

* **Usage**: 
```js
//드랍박스 아이템중에 아이템명이 휴지인 아이템의 위치. 처음부터 탐색해서 찾을 경우 바로 리턴한다.
var index = dropBox.indexOfText('휴지');
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {String} context 에 매핑된 이벤트 수신자

* **Usage**: 
```js
var dropBox = new ADropBox();
dropBox.init();
```

<br/>

### isMoreScrollBottom()

Bottom방향으로 스크롤이 더 가능한지 여부를 리턴한다.

* **Returns**: Boolean

<br/>

### isMoreScrollTop()

Top방향으로 스크롤이 더 가능한지 여부를 리턴한다.

* **Returns**: Boolean

<br/>

### isScroll()

스크롤 가능여부를 리턴한다.

<br/>

### keyDownManage()

드랍박스에서의 keyDown 이벤트를 관리한다. 위아래 화살표, 엔터, esc등의 이벤트에 대해서의 동작이 정의 되어있다.

<br/>

### listPopupClose()

드랍박스를 클릭했을때 나오는 메뉴선택창을 닫아주는 함수이다.

* **Usage**: 
```js
dropBox.listPopupClose();
```

<br/>

### openBox()

드랍박스를 펼친다. 자동으로 상단으로 띄울지 하단으로 띄울지 결정한다.

* **Usage**: 
```js
dropBox.openBox();
```

<br/>

### removeAll()

모든 아이템을 삭제한다.

* **Usage**: 
```js
dropBox.removeAll();
```

<br/>

### removeItem( index )

해당하는 위치의 아이템을 삭제 한다.

* **Parameters**: 
	* **`index`** {String} 아이템위치

* **Usage**: 
```js
dropBox.removeItem(1);
```

<br/>

### scrollYImplement()

드랍박스 리스트의 스크롤 이벤트를 등록하는 함수이다. 스크롤 애니메이션을 발생시킨다.

<br/>

### selectItem( index )

해당하는 위치의 아이템을 선택한다.

* **Parameters**: 
	* **`index`** {String} 아이템위치

* **Usage**: 
```js
dropBox.selectItem(2);
```

<br/>

### selectItemByData( data )

입력한 data와 아이템 데이터가 같은 아이템을 선택한다.

* **Parameters**: 
	* **`data`** {String} 아이템데이터

* **Usage**: 
```js
dropBox.selectItemByData(data);
```

<br/>

### selectItemByText( text )

입력한 text와 아이템의 text가 같은 아이템을 선택한다.

* **Parameters**: 
	* **`text`** {String} 아이템명

* **Usage**: 
```js
dropBox.selectItemByText('휴지'); //텍스트가 휴지인 아이템을 선택한다.
```

<br/>

### setDataType( dataType )

드랍박스의 텍스트필드타입을 세팅한다.

* **Parameters**: 
	* **`dataType`** {String} 텍스트필드타입

* **Usage**: 
```js
dropBox.setDataType('text');
dropBox.setDataType('tel');
dropBox.setDataType('password');
```

<br/>

### setDropBoxHeight( height )

드랍박스의 높이를 지정한다. 이 함수는 openBox가 호출되어서 open되기전에 호출해야한다.

* **Parameters**: 
	* **`height`** {String} 높이값

* **Usage**: 
```js
dropBox.setDropBoxHeight(300);
```

<br/>

### setEditText( text )

드랍박스의 텍스트을 세팅한다.

* **Parameters**: 
	* **`text`** {String} 텍스트

* **Usage**: 
```js
dropBox.setEditText('휴지');
```

<br/>

### setItem( index, text, data )

해당 위치의 아이템을 셋팅한다.

* **Parameters**: 
	* **`index`** {String} 아이템위치
	* **`text`** {String} 아이템명
	* **`data`** {String} 아이템데이터

* **Usage**: 
```js
var data; //아이템에 저장될 데이터, 형식은 자유
dropBox.setItem(1, '아이템명', data);
```

<br/>

### setItemData( index, data )

해당 위치의 아이템 데이터를 세팅한다.

* **Parameters**: 
	* **`index`** {String} 아이템 위치
	* **`data`** {String} 아이템 데이터

* **Usage**: 
```js
var data; //아이템에 저장할 데이터, 형식은 자유
dropBox.setItemData(1, data);
```

<br/>

### setItems( items )

드랍박스에 모든 아이템을 추가한다.

* **Parameters**: 
	* **`items`** {String} 아이템 객체

* **Usage**: 
```js
var text1, data1;
var text2. data2;
.
.
dropBox.setItems([{ 'text':text1, 'data':data1 },{ 'text':text2, 'data':data2 }...]);
```

<br/>

### setItemText( index, text )

해당 위치의 text를 세팅한다.

* **Parameters**: 
	* **`index`** {String} 아이템위치
	* **`text`** {String} 아이템명

* **Usage**: 
```js
dropBox.setItemText(2,'아이템명');
```

<br/>

### setOpenDirection( isDown )

드랍박스를 펼칠 방향을 세팅한다.

* **Parameters**: 
	* **`isDown`** {String} 하단방향여부

* **Usage**: 
```js
dropBox.setOpenDirection(true); // 밑으로 염
dropBox.setOpenDirection(false); // 위로 염
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조

<br/>

### setReadOnly( isReadOnly )

읽기전용여부를 세팅한다.

* **Parameters**: 
	* **`isReadOnly`** {Boolean} 읽기전용여부

* **Usage**: 
```js
dropBox.setReadOnly(false);
```

<br/>

### setSelectClass( selectClass )

드랍박스 리스트에서 선택영역 클래스를 지정한다.

* **Parameters**: 
	* **`selectClass`** {String} 클래스명

* **Usage**: 
```js
dropBox.setSelectClass('className');
```

<br/>

### setTextAlign( align )

드랍박스의 텍스트 정렬 속성을 세팅한다.

* **Parameters**: 
	* **`align`** {String} 정렬 속성

* **Usage**: 
```js
dropBox.setTextAlign('left');
dropBox.setTextAlign('center');
dropBox.setTextAlign('right');
```

<br/>

### setUseDropBox( useDropBox )

드랍 박스 사용여부를 설정한다. (기본값 : true)

* **Parameters**: 
	* **`useDropBox`** {Boolean} true:사용 false:미사용

<br/>

### updatePosition( pWidth, pHeight )

컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. <br/>브라우저의 사이즈가 변경될 경우 자동으로 호출된다.

* **Parameters**: 
	* **`pWidth`** {Number} 부모의 너비
	* **`pHeight`** {Number} 부모의 높이

<br/>

### ADropBox.setOpenedDropBox()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### ADropBox.getOpenedDropBox()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### enableScrollManager()



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


### setData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>

## Events


### change( comp, info, e )

드랍박스에서 키업이 발생될 때 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {String} 이벤트 객체

### click( comp, info, e )

드랍박스 클릭시 호출됩니다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

### select( comp, info, e )

드랍박스의 아이템을 선택 했을떄 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} 선택된 아이템의 객체
	* **`e`** {Object} 아이템 정보

<br/>
<br/>

## Attribute

### Data

* **Placeholder:** 플레이스홀더 텍스트를 설정하는 속성입니다. 
* **Align:** 텍스트의 정렬을 설정하는 속성입니다. 
    * **left:** 텍스트를 좌측정렬 합니다. 
    * **center:** 텍스트를 중앙정렬 합니다. 
    * **right:** 텍스트를 우측 정렬합니다. 

<br/>
