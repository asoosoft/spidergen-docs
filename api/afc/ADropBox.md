# ADropBox
**Extends**: [`AComponent`](AComponent.html#AComponent)

클릭하여 선택할 수 있는 아이템들을 띄우거나 검색하여 선택할 수 있는 컴포넌트

<br/>

## Properties


### dropBoxH \<Number>
클릭 시 펼쳐질 드랍박스의 높이

<br/>

### focusClass \<String>
드랍박스 아이템 포커스 시의 스타일 클래스 명

<br/>

### isTabable \<Boolean>
탭키 이동이 가능한 컴포넌트 여부

<br/>

### items \<Array>
드랍박스 클릭 시 표시될 아이템들

<br/>

### normalClass \<String>
드랍박스 아이템 미선택 시의 스타일 클래스 명

<br/>

### openDir \<Boolean>

드랍박스를 펼칠 방향 (true : 하단으로 펼침, false: 상단으로 펼침)

<br/>

### selectClass \<String>
드랍박스 아이템 선택 시의 스타일 클래스 명

<br/>

### selIndex \<Number>
현재 선택되어있는 아이템의 인덱스

<br/>
<br/>

## Class Methods

### ADropBox.getOpenedDropBox()

프로젝트 전체에서 현재 오픈되어있는 드랍박스의 컴포넌트를 리턴한다.

- **Returns** \<ADropBox>

<br/>
<br/>

## Instance Methods

### addItem( text, data )

아이템을 추가한다.

- `text` \<String> 아이템명
- `data` \<Any> 아이템데이터
- **Returns** \<Object> 아이템

```js
var data; //아이템에 저장될 데이터, 형식 자유
dropBox.addItem('컴포넌트에 보이는 이름', data);
```

<br/>

### bindData( ulObj )

읽기 모드가 아닌경우에 드랍박스 input부분에 검색어가 있는 경우에 검색처리를 해주는 함수이다.

- `ulObj` \<HTML Object> ul object
- **Returns** \<boolean>

<br/>

### clearSelectItem()

선택된 아이템을 초기화한다. (선택된게 없게함)

<br/>

### enableScrlManagerY()

드랍박스의 UL Object가 스크롤이 가능하게 한다.

<br/>

### enableScrollManager()

터치 이벤트를 핸들링하여 자체적으로 구현한 스크롤 기능을 활성화 한다. 내부적으로 [ScrollManager](../libray/ScrollManager.html) 가 사용된다.

<br/>

### getDataType()

드랍박스의 텍스트필드타입을 리턴한다.

- **Returns** \<String>

<br/>

### getEditText()

드랍박스의 텍스트를 리턴한다.

- **Returns** \<String>

<br/>

### getItem( index )

해당 위치의 아이템을 리턴한다.

- `index` \<String> 아이템 위치
- **Returns** \<Object:>

<br/>

### getItemData( index )

해당 위치의 아이템 데이터를 리턴한다.

- `index` \<String> 아이템 위치
- **Returns** \<String>

<br/>

### getItems()

모든 아이템을 리턴합니다.

- **Returns** \<Array Object>

<br/>

### getItemSize()

아이템의 크기를 리턴한다.

- **Returns** \<Number>

<br/>

### getItemText( index )

해당 위치의 아이템text를 리턴한다.

- `index` \<String> 아이템위치
- **Returns** \<String>

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getSelectedIndex()

선택된 아이템의 위치를 리턴합니다.

- **Returns** \<Number>

<br/>

### getSelectedItem()

선택된 아이템의 객체를 리턴한다.

- **Returns** \<Object>

<br/>

### getSelectedItemData( key )

선택된 아이템 데이터를 리턴한다.

- `key` \<String> 키값
- **Returns** \<Object>

<br/>

### getSelectedItemText()

선택된 아이템명을 리턴한다.

- **Returns** \<String>

<br/>

### getTextAlign()

드랍박스의 텍스트 정렬 속성을 리턴한다.

- **Returns** \<String>

<br/>

### indexOfData( data )

입력된 data와 아이템의 데이터가 같은 아이템위치를 리턴한다.

- **`data`** \<String> 아이템데이터
- **Returns** \<Number>

<br/>

### indexOfText( text )

입력된 text와 아이템text가 같은 아이템위치를 리턴한다.

- `text` \<String> 아이템명
- **Returns** Number

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var dropBox = new ADropBox();
dropBox.init();
```

<br/>

### isMoreScrollBottom()

Bottom방향으로 스크롤이 더 가능한지 여부를 리턴한다.

- **Returns** \<Boolean>

<br/>

### isMoreScrollTop()

Top방향으로 스크롤이 더 가능한지 여부를 리턴한다.

- **Returns** \<Boolean>

<br/>

### isScroll()

스크롤 가능여부를 리턴한다.

- **Retunrs** \<Boolean>

<br/>

### listPopupClose()

드랍박스를 클릭했을때 나오는 메뉴선택창을 닫는다.


<br/>

### openBox()

드랍박스를 펼친다. 자동으로 상단으로 띄울지 하단으로 띄울지 결정한다.

<br/>

### removeAll()

모든 아이템을 삭제한다.

<br/>

### removeItem( index )

해당하는 위치의 아이템을 삭제 한다.

- `index` \<String> 아이템위치

<br/>

### scrollYImplement()

드랍박스 리스트의 스크롤 이벤트를 등록하는 함수이다. 스크롤 애니메이션을 발생시킨다.

<br/>

### selectItem( index )

해당하는 위치의 아이템을 선택한다.

- `index` \<String> 아이템위치

<br/>

### selectItemByData( data )

입력한 data와 아이템 데이터가 같은 아이템을 선택한다.

- `data` \<String> 아이템데이터

<br/>

### selectItemByText( text )

입력한 text와 아이템의 text가 같은 아이템을 선택한다.

- `text` \<String> 아이템명

<br/>

### setData( dataArr )

새로운 데이터 배열에 대한 아이템을 세팅한다.

- `dataArr` 데이터 배열

```js
dropBox.setData(['사과', '바나나']);
```

<br/>

### setDataType( dataType )

드랍박스의 텍스트필드타입을 세팅한다.

- `dataType` \<String> 텍스트필드타입

```js
dropBox.setDataType('text');
dropBox.setDataType('tel');
dropBox.setDataType('password');
```

<br/>

### setDropBoxHeight( height )

드랍박스의 높이를 지정한다. 이 함수는 openBox가 호출되어서 open되기전에 호출해야한다.

- `height` \<Number> 높이값

<br/>

### setEditText( text )

드랍박스의 텍스트을 세팅한다.

- `text` \<String> 텍스트

<br/>

### setItem( index, text, data )

해당 위치의 아이템을 셋팅한다.

- `index` \<String> 아이템위치
- `text` \<String> 아이템명
- `data` \<Any> 아이템데이터

```js
var data; //아이템에 저장될 데이터, 형식은 자유
dropBox.setItem(1, '아이템명', data);
```

<br/>

### setItemData( index, data )

해당 위치의 아이템 데이터를 세팅한다.

- `index` \<String> 아이템 위치
- `data` \<Any> 아이템 데이터

```js
var data; //아이템에 저장할 데이터, 형식은 자유
dropBox.setItemData(1, data);
```

<br/>

### setItems( items )

드랍박스에 모든 아이템을 추가한다.

- `items` \<Object> 아이템 객체

```js
var text1='텍스트1', data1 = 0;
var text2='텍스트2', data2 = 1;
.
.
dropBox.setItems([{ 'text':text1, 'data':data1 },{ 'text':text2, 'data':data2 }...]);
```

<br/>

### setItemText( index, text )

해당 위치의 text를 세팅한다.

- `index` \<String> 아이템위치
- `text` \<String> 아이템명

```js
dropBox.setItemText(2,'아이템명');
```

<br/>

### setOpenDirection( isDown )

드랍박스를 펼칠 방향을 세팅한다.

- `isDown` \<String> 하단방향여부

```js
dropBox.setOpenDirection(true); // 밑으로 염
dropBox.setOpenDirection(false); // 위로 염
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setReadOnly( isReadOnly )

읽기전용여부를 세팅한다.

- `isReadOnly` \<Boolean> 읽기전용여부

<br/>

### setSelectClass( selectClass )

드랍박스 리스트에서 선택영역 클래스를 지정한다.

- `selectClass` \<String> 클래스명

<br/>

### setTextAlign( align )

드랍박스의 텍스트 정렬 속성을 세팅한다.

- `align` \<String> 정렬 속성

```js
dropBox.setTextAlign('left');
dropBox.setTextAlign('center');
dropBox.setTextAlign('right');
```

<br/>

### setUseDropBox( useDropBox )

드랍 박스 사용여부를 설정한다. (기본값 : true)

- `useDropBox` \<Boolean> true:사용 false:미사용

<br/>

### updatePosition( pWidth, pHeight )

컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. <br/>브라우저의 사이즈가 변경될 경우 자동으로 호출된다.

* `pWidth` \<Number> 부모의 너비
* `pHeight` \<Number> 부모의 높이

<br/>
<br/>

## Events

공통부분은 설명은 \<[AComponent Events](AComponent.html#events)> 참조

### change( comp, info, e )

드랍박스에서 키업이 발생될 때 호출된다.

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br/>

### click( comp, info, e )

드랍박스 클릭시 호출됩니다.

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br/>

### select( comp, info, e )

드랍박스의 아이템을 선택 했을떄 호출된다.

- `info` \<Object> 선택된 아이템의 객체

<br/>
<br/>

## Attribute

### Data

* **Placeholder:** 플레이스홀더 텍스트를 설정하는 속성
* **Align:** 텍스트의 정렬을 설정하는 속성
    * **left:** 텍스트를 좌측정렬 한다
    * **center:** 텍스트를 중앙정렬 한다
    * **right:** 텍스트를 우측정렬 한다

<br/>
