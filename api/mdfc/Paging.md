# Paging
**Extends**: [`AView`](./../afc/AView.md)

리스트의 페이징을 이 컴포넌트를 사용하면 손쉽게 사용이 가능하다.

<br/>

## Class Variables

<br/>

## Instance Variables

<br/>

## Class Methods

<br/>

## Instance Methods

### addParam( data )

페이지 이동시 전달할 데이터를 기존에 설정한것과 병합한다.

- `data` \<JSON Object> 전달할 데이터

```js
this.paging.addParam({
    key1: 'data1',
    key3: 'data3'
});
```

<br/>

### getBlock()

블럭당 페이지 수를 반환한다.

- **Returns** \<Number> 블럭당 페이지 수

<br/>

### getPage()

컴포넌트의 페이지 정보를 JSON 형식으로 반환한다.

- **Returns** \<JSON Object> 페이지 정보

```js
var info = this.paging.getPage();
info.totalCount;  //전체 레코드 수
info.totalPage;	  //전체 페이지 수
info.pageIndex;	  //현재 페이지 번호
info.perPage;	  //페이지당 레코드 수
info.block;		  //블록당 페이지 수

```

<br/>

### getPageIndex()

현재 페이지 번호를 반환한다.

- **Returns** \<Number> 현재 페이지 번호

<br/>

### getPerPage()

페이지당 레코드 수를 반환한다.

- **Returns** \<Number> 페이지당 레코드 수

<br/>

### getTotalCount()

페이징 컴포넌트의 총 레코드 수를 반환한다.

- **Returns** \<Number> 총 레코드 수

<br/>

### getTotalPage()

페이징 컴포넌트의 총 페이지 수를 반환한다.

- **Returns** \<Number> 총 페이지 수

<br/>

### setBlock( blk )

블럭당 페이지 수를 설정한다.<br/>페이지번호가 설정한것 만큼만 화면에 표시된다.

- `blk` \<Number> 블럭당 페이지 수

<br/>

### setComponent( acomp )

페이징 컴포넌트와 연결된 컴포넌트를 설정한다.

- `acomp` \<[`AGrid`](./../afc/AGrid.md)> or <[`AListView`](./../afc/AListView.md)> 그리드 or 리스트뷰 컴포넌트

<br/>

### setDelegator( delegator )

delegator 함수 처리 객체를 설정한다. pagingBindData 함수를 정의하여 이벤트를 처리한다.

- `delegator` \<Object> 위임받을 객체

```js
//페이징 컴포넌트를 사용하기 위한 예시
function SampleView*init(context, evtListener)
{
	super.init(context, evtListener);
	
	this.paging.setDelegator(this);
	...
	...
	this.page = 1; //현재 페이지번호.
	this.send_pageList();
};

function SampleView*send_pageList()
{
	//전체레코드수, 현재페이지번호, 한페이지당레코드수, 블럭당페이지수 세팅	
	this.paging.setPage(250, this.page, 10, 10);
	this.paging.setPageView();

	//현재 페이지에 맞는 데이터를 가져오는 코드
	...
	...
};

//페이지 버튼을 누를 때 발생하는 
//이벤트 함수이다. delegator를 지정해주면 전달받을수 있다.
function SampleView*pagingBindData(comp, info)
{
	var page = info.pageIdx;
	//클릭된 페이지가 현재 페이지와 같으면 리턴.
	if(page == this.page) return;
	this.page = page;
	this.send_pageList();
};

```

<br/>

### setDisabled( isDisabled )

컴포넌트의 사용여부를 설정한다.

- `isDisabled` \<Boolean> 사용여부

<br/>

### setIsCenter( bln )

컴포넌트를 중앙으로 설정한다.

- `bln` \<Boolean> 중앙 위치 여부

<br/>

### setPage( cnt, idx, per, blk )

페이징 컴포넌트의 값을 설정한다.

- `cnt` \<Number> 전체 레코드 수
- `idx` \<Number> 현재 페이지 번호
- `per` \<Number> 페이지당 레코드 수
- `blk` \<Number> 블럭당 페이지 수

<br/>

### setPageIndex( idx )

현재 페이지 번호를 설정한다.

- `idx` \<Number> 페이지 번호

<br/>

### setPageView()

페이징 컴포넌트를 세팅된 정보를 토대로 렌더링 한다.

```js
this.paging.setPageView();
```

<br/>

### setParam( data )

페이지 이동시 전달할 데이터를 설정한다.

- `idx` \<JSON Object> 전달할 데이터
```js
this.paging.setParam({
    key1: 'data1',
    key2: 'data2'
});
```

<br/>

### setPerPage( per )

페이지당 레코드 수를 설정한다.

- `per` \<Number> 레코드 수

<br/>

### setReadOnly( isReadOnly )

컴포넌트의 읽기전용 속성을 설정한다.

- `isReadOnly` \<Boolean> 읽기전용 속성 여부

<br/>

### setTotalCount( cnt )

페이징 컴포넌트의 총 레코드수를 설정한다. 자동으로 새로고침도 진행된다.

- `cnt` \<Number> 전체 레코드 수

<br/>

## Events


### pagingBindData( comp, info )

페이지 버튼을 클릭시 호출되는 함수이다. delegator를 위임해야 호출된다. 자세한 사용법은 [setDelegator](#-setDelegator(-delegator-))함수를 참조한다.
- `comp` \<Paging> 컴포넌트 객체
- `info` \<JSON Object> 미리 저장된 데이터 및 페이지 번호

<br/>

