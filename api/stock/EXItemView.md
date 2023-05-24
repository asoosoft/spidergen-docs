# EXItemView
> **Extends**: [`AView`](./../afc/AView.md)

종목 선택 뷰

<br/>

## Properties

### frwName

* `Default` "stock"

<br/>

### dropMaxCount \<Number>

dropView에 표시되는 종목 최대 갯수

<br/>

### typeArr \<Array>

종목 정보 배열

<br/>

### itemInfo \<Array>

세팅된 종목 정보

### unshift \<Boolean>

히스토리 추가 순서

<br/>
<br/>

## Methods

### getItemInfo()

종목뷰에 세팅된 종목 정보를 리턴한다.

* **Returns** \<Array>

```js
var itemInfo = this.itemView.getItemInfo();
```

<br/>

### openDrop( itemsArr )

첫번째 컴포넌트의 아래에 넓이는 같고 높이는 컴포넌트의 최대 5배인 모달윈도우를 띄운다.<br/>윈도우에는 종목정보가 그리드 형태로 표현되며 선택시 종목뷰에 종목정보가 세팅된다.

* `itemsArr` \<Array> 종목 정보 배열

```js
var itemsArr = EXItemView.getHistoryInfo().search();
this.itemView.openDrop(itemsArr);
```

<br/>

### openSearchWindow()

종목 검색을 위한 풀팝업을 띄운다. 팝업에서 종목을 선택하면 종목뷰에 종목 정보를 세팅한다.

```js
this.itemView.openSearchWindow();
```

<br/>

### setHistoryInfo( obj )

종목 뷰에서 쓰일 히스토리 객체를 지정한다.

* `obj` \<Object> 히스토리 객체

```js
EXItemView.setHistoryInfo(new HistoryInfo());
```

<br/>

### setItemInfo( itemInfo, isReport )

종목 정보로 종목을 선택한다. isReport값을 true로 세팅하면 등록해둔 change 이벤트가 발생한다.<br/><br/>- 종목 세팅 순서<br/>1. 종목 정보가 없으면 히스토리 객체에서 최근종목정보를 가져온다. (history:getRecent)<br/>2. 최근종목정보도 없으면 기본종목정보를 가져와 세팅한다. (master:getDefaultItemInfo)<br/>3. 히스토리 객체에 최종 종목정보를 세팅한다. (history:set)<br/>4. 히스토리 정보를 저장한다. (history.saveInfo)<br/>5. 첫번째 자식 컴포넌트에 setText가 있으면 종목정보의 1번째 위치의 값인 종목표현명으로 세팅한다.<br/>6. isReport값이 true이면 change 이벤트를 발생시킨다.

* `itemInfo` \<Array> 종목 정보 배열 [코드, 종목표현명, 분류값]
* `isReport` \<Boolean> change 이벤트 전달 여부

```js
this.itemView.setItemInfo(['005930', '삼성전자', '001'], true);
```

<br/>

### setMasterInfo( obj )

종목 뷰에서 쓰일 종목 마스터 객체를 지정한다.<br/>종목 마스터 객체에는 반드시 아래의 함수가 존재해야한다.<br/>getDefaultItemInfo() - 기본 종목 정보배열을 리턴하는 함수<br/>getItem(code, type) - 코드와 분류값에 맞는 종목을 리턴하는 함수<br/>get() - 전체 종목을 리턴하는 함수<br/>getInfoByItem(item) - 종목에 해당하는 정보배열([코드, 종목표현명, 분류값])을 리턴하는 함수

* `obj` \<Object> 종목 마스터 객체

```js
EXItemView.setMasterInfo(new MasterInfo());
```

<br/>

### EXItemView.getHistoryInfo()

* **Returns** \<Object> 히스토리 객체

```js
EXItemView.getHistoryInfo();
```

<br/>

### EXItemView.getMasterInfo()

전체 종목을 관리할 객체를 리턴하는 함수

* **Returns** \<Object> 종목 마스터 객체

```js
EXItemView.getMasterInfo();
```

<br/>

### setText( text )

종목검색어 셋팅

* `text` \<String> 종목 검색어

```js
EXItemView.setText(text);
```

<br/>

### getItem()

현재 셋팅된 종목 리턴하는 함수

* **Returns** \<Object> 종목 객체

```js
EXItemView.getItem();
```

<br/>

### setTypeArr( typeArr )

종목 중 원하는 타입 배열을 저장한다.

* `typeArr` \<Array> Type 배열

```js
EXItemView.setTypeArr(typeArr);
```

<br/>

### getTypeArr()

Type 배열을 리턴한다.

* **Returns** \<Array> Type 배열 

```js
EXItemView.getTypeArr();
```

<br/>

### setExceptArr( exceptArr )

종목 검색시 제외할 키 배열을 저장한다.

* `exceptArr` \<Array> 제외할 key 배열

```js
EXItemView.setExceptArr(exceptArr);
```

<br/>

### getExceptArr()

제외할 키 배열을 리턴한다.

* **Returns** \<Array> key 배열 

```js
EXItemView.getExceptArr();
```

<br/>

### setDropMaxCount( dropMaxCount )

dropView에 표시할 최대 갯수를 지정한다.

* `dropMaxCount` \<Number> dropbox 윈도우에 표시될 종목 최대값

```js
EXItemView.setDropMaxCount(dropMaxCount);
```

<br/>

### getDropMaxCount()

dropView에 표시할 최대 갯수 리턴한다.

* **Returns** \<Number> dropbox 윈도우에 표시될 종목 최대값

```js
EXItemView.getDropMaxCount();
```

<br/>

### openSearchWindow()

검색 윈도우창을 오픈한다.

```js
EXItemView.openSearchWindow();
```

<br/>

### onSearchTextFieldChange()

검색 윈도우에서 검색시 호출되는 함수 (change)

<br/>

### onSearchGridSelect()

검색 윈도우에서 그리드의 로우를 클릭시 호출되는 함수

<br/>

### onDropGridSelect()

드랍 윈도우에서 그리드의 로우를 클릭시 호출되는 함수

<br/>
<br/>
