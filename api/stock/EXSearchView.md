# EXSearchView
> **Extends**: [`AView`](../afc/AView.md)

검색뷰

<br/>

## Properties

<!-- ### frwName



<br/> -->

### searchKeyArr \<Array>

검색키 목록 저장 배열

* `Default` ["name"]

<br/>

### depth \<Number>

데이터의 깊이를 저장하는 변수

<br/>
<br/>

## Methods

### getData()

검색하기 위해 세팅한 객체 또는 배열을 리턴한다.

* **Returns** \<Object>

```js
var data = this.searchView.getData();
```

<br/>

### getSearchKeyArr()

세팅한 검색할 키값을 리턴한다.

* **Returns** \<Array>

```js
var arr = this.searchView.getSearchKeyArr();
```

<br/>

### searchData( srchTxt, typeArr, exceptArr )

세팅한 데이터에서 검색키에 해당하는 값들과 검색어를 비교하여 해당하는 결과값을 리턴한다.<br/><br/>typeArr : 데이터구조가 배열인 경우 배열위치값, 객체인경우 키값을 지정하여 특정 분류에 해당하는 정보를 얻는다.<br/>exceptArr : 최종 정보 배열(또는 객체)를 감싸고 있는 것이 객체인 경우 제외할 키값을, 배열인 경우 제외할 위치값을 넣는다.

* **Returns** \<Array>

* `srchTxt` \<String> 검색어
* `typeArr` \<Array> 분류값(또는 배열)
* `exceptArr` \<Array> 제외할 객체의 키값 또는 위치값(또는 배열)

```js
// 검색키에 해당하는 값에 삼성이 들어간 목록을 리턴한다.
this.searchView.searchData('삼성');
// 타입이 001인 데이터 중 검색키에 해당하는 값에 삼성이 들어간 목록을 리턴한다.
this.searchView.searchData('삼성', ['001']);
// 타입이 001이고 키값이 '005930' 이 아닌 데이터 중 검색키에 해당하는 값에 삼성이 들어간 목록을 리턴한다.
this.searchView.searchData('삼성', ['001'], ['005930']);
// 타입이 001이고 배열의 위치가 0번째가 아닌 데이터 중 검색키에 해당하는 값에 삼성이 들어간 목록을 리턴한다.
this.searchView.searchData('삼성', ['001'], [0]);
```

<br/>

### setData( data )

검색할 객체 또는 배열을 지정한다.

* `data` \<Object> 검색할 객체 또는 배열

```js
var data = { "001": { "005930": { code: '005930', name: '삼성전자', type: '001', ... } } };
this.searchView.setData(data);
```

<br/>

### setSearchKeyArr( keyArr )

검색할 키값을 세팅한다. code, name, ... 또는 0, 1, ...

* `keyArr` \<Array> 검색할 키 값 배열

```js
this.searchView.setSearchKeyArr(['code', 'name']);
this.searchView.setSearchKeyArr([0, 1]);
```

<br/>
<br/>
