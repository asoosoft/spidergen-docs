# Paging
> **Extends**: `AView`

리스트의 페이징 모듈화

<br/>

## Properties

### frwName



* **Type**: ``
* **Default**: ``

<br/>

### childComp



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### addParam( data )

페이지 이동시 전달할 파라미터를 기존에 설정한것과 병합한다.

* **Parameters**: 
	* **`data`** {Object} json object

* **Usage**: 
```js
this.paging.addParam({
    key1: 'data1',
    key3: 'data3'
});
```

<br/>

### createElement( context )

엘러먼트를 생성해 줍니다. 내부적으로 사용하는 함수입니다. 이 함수가 실행된 이후에 init 함수가 실행됩니다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트를 생성 및 초기화 정보

<br/>

### getBlock()

페이징 컴포넌트에 설정된 블록당 페이지 수를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var cnt = this.paging.getBlock();
```

<br/>

### getPage()

페이징 컴포넌트에 설정된 정보를 반환한다.

* **Returns**: json

* **Usage**: 
```js
var info = this.paging.getPage();
//{
    totalCount: 전체 레코드 수,
    totalPage: 전체 페이지 수,
    pageIndex: 현재 페이지 번호,
    perPage: 페이지당 레코드 수,
    block: 블록당 페이지 수
}
```

<br/>

### getPageIndex()

페이징 컴포넌트의 현재 페이지 번호를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var cur = this.paging.getPageIndex();
```

<br/>

### getPerPage()

페이징 컴포넌트에 설정된 페이지당 레코드 수를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var cnt = this.paging.getPerPage();
```

<br/>

### getTotalCount()

페이징 컴포넌트의 총 레코드 수를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var cnt = this.paging.getTotalCount();
```

<br/>

### getTotalPage()

페이징 컴포넌트의 총 페이지 수를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var cnt = this.paging.getTotalPage();
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출합니다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출합니다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {Object} context에 매핑된 이벤트 수신자

<br/>

### isNumber( s )

매개변수 s가 숫자인지 판단해서 결과를 반환한다.

* **Parameters**: 
	* **`s`** {String} 문자

* **Usage**: 
```js
console.log(this.paging.isNumber('1')); //true
console.log(this.paging.isNumber('1a')); //false
```

<br/>

### setBlock( blk )

페이징 컴포넌트의 블럭당 페이지 수를 설정한다.<br/>페이지번호가 설정한것 만큼만 화면에 표시된다.

* **Parameters**: 
	* **`blk`** {Number} 블럭당 페이지 수

* **Usage**: 
```js
this.paging.setBlock(10);
```

<br/>

### setComponent( acomp )

페이징 컴포넌트와 연결된 컴포넌트를 설정한다.

* **Parameters**: 
	* **`acomp`** {AComponent} 그리드 or 리스트뷰 컴포넌트

* **Usage**: 
```js
this.paging.setComponent(this.grid);
```

<br/>

### setDelegator( delegator )

delegator 함수 처리 객체를 설정한다.<br/>pagingBindData 함수를 정의하여 이벤트를 처리한다.

* **Parameters**: 
	* **`delegator`** {Object} 위임받을 객체

* **Usage**: 
```js
this.paging.setDelegator(this);
```

<br/>

### setDisabled( isDisabled )

컴포넌트의 사용여부를 설정한다.

* **Parameters**: 
	* **`isDisabled`** {Boolean} 사용여부

* **Usage**: 
```js
this.paging.setDisabled(true);
```

<br/>

### setIsCenter( bln )

페이징 컴포넌트를 중앙에 위치하도록 할것인지 설정한다.

* **Parameters**: 
	* **`bln`** {Boolean} 중앙 위치 여부

* **Usage**: 
```js
this.paging.setIsCenter(true);
```

<br/>

### setPage( cnt, idx, per, blk )

페이징 컴포넌트의 값을 설정한다.

* **Parameters**: 
	* **`cnt`** {Number} 전체 레코드 수
	* **`idx`** {Number} 현재 페이지 번호
	* **`per`** {Number} 페이지당 레코드 수
	* **`blk`** {Number} 블럭당 페이지 수

* **Usage**: 
```js
this.paging.setPage(100, 1, 10, 10);
```

<br/>

### setPageIndex( idx )

페이징 컴포넌트의 현재 페이지 번호를 설정한다.

* **Parameters**: 
	* **`idx`** {Number} 페이지 번호

* **Usage**: 
```js
this.paging.setPageIndex(2);
```

<br/>

### setPageView()

페이징 컴포넌트를 표시한다.

* **Usage**: 
```js
this.paging.setPageView();
```

<br/>

### setParam( data )

페이지 이동시 전달할 데이터를 설정한다.

* **Parameters**: 
	* **`data`** {Object} json object

* **Usage**: 
```js
this.paging.setParam({
    key1: 'data1',
    key2: 'data2'
});
```

<br/>

### setPerPage( per )

페이징 컴포넌트의 페이지당 레코드 수를 설정한다.

* **Parameters**: 
	* **`per`** {Number} 레코드 수

* **Usage**: 
```js
this.paging.setPerPage(10);
```

<br/>

### setReadOnly( isReadOnly )

컴포넌트의 읽기전용 속성을 설정한다.

* **Parameters**: 
	* **`isReadOnly`** {Boolean} 읽기전용 속성 여부

* **Usage**: 
```js
this.paging.setReadOnly(true);
```

<br/>

### setTotalCount( cnt )

페이징 컴포넌트의 총 레코드수를 설정한다.

* **Parameters**: 
	* **`cnt`** {String} 전체 레코드 수

* **Usage**: 
```js
this.paging.setTotalCount(100);
```

<br/>

### clone()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setTotalCount()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getDroppable()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>

## Events


### pagingBindData()

delegator 위임 후에 호출된다.<br/>페이지 버튼을 클릭시 호출되며 매개변수로 acomp, info 가 전달된다.

<br/>

