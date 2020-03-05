# AQuery
> **Extends**: 

query 파일의 구조정보를 관리하는 클래스

<br/>

## Properties


### query

json 형식의 쿼리파일을 객체화한 변수

* **Type**: `Object`
* **Default**: `null`

<br/>

### queryComps

쿼리와 연결된 컴포넌트들의 집합 <br/>this.queryComps = <br/> { <br/> //화면 번호 <br/>'1500': [AButton, ALabel, ...], <br/> '2500': [AEdit, AEdit, ...], <br/> };

* **Type**: `Object`
* **Default**: `{}`

<br/>
<br/>

## Methods

### addQueryComp( containerId, type, acomp )

AQuery 객체에 type 과 연결된 컴포넌트를 등록한다. 컴포넌트는 containerId(화면)단위로 등록된다. 등록된 컴포넌트는 input 인 경우 데이터를 전송할 때 컴포넌트의 값을 참조하여 데이터를 버퍼에 셋팅한다. output 인 경우 데이터 수신 시 수신된 데이터를 컴포넌트에 반영한다

* **Parameters**: 
	* **`containerId`** {String} 컴포넌트가 포함된 화면의 id
	* **`type`** {String} 'input' or 'output'
	* **`acomp`** {String} 등록할 컴포넌트

<br/>

### eachQueryBlock( type, callback )

type 영역의 모든 블럭의 구조정보를 콜백함수로 넘겨준다. block 객체의 구조는 getQueryBlock 참조.

* **Parameters**: 
	* **`type`** {String} 'input' or 'output'
	* **`callback`** {String} function(name, block)

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
aquery.eachQueryBlock('output', function(name, block)
{
　// 블락명, 블락 정보로 원하는 처리를 한다.
});
```

<br/>

### getIoVer()

쿼리의 버전을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var version = aquery.getIoVer();
```

<br/>

### getMeta()

쿼리 파일의 메타 정보를 리턴한다.

* **Returns**: Object

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var meta= aquery.getMeta();
```

<br/>

### getName()

쿼리명을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var name= aquery.getName();
```

<br/>

### getQueryBlock( type, blockName )

type 영역의 특정 블럭의 구조정보 객체를 리턴한다. ex) aquery.getQueryBlock('output', 'OutBlock1');

* **Returns**: Object

* **Parameters**: 
	* **`type`** {String} 'input' or 'output'
	* **`blockName`** {String} ex) 'InBlock1', 'OutBlock2'

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var inblock1 = aquery.getQueryBlock('input', 'InBlock1');
var outblokc2 = aquery.getQueryBlock('output', 'OutBlock2');
```

<br/>

### getQueryComps( containerId, type )

AQuery 객체에 type 과 연결된 컴포넌트들을 배열로 리턴한다.

* **Returns**: Array

* **Parameters**: 
	* **`containerId`** {String} 컴포넌트가 포함된 화면의 id
	* **`type`** {String} 'input' or 'output'

<br/>

### getQueryType()

쿼리의 유형을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var qryType= aquery.getQueryType();
```

<br/>

### getSafeQuery( qryName )

쿼리명에 해당하는 쿼리 객체를 반환한다. 로드된 쿼리 객체가 없으면 쿼리정보를 Query 폴더의 쿼리명으로된 파일에서 읽어서 쿼리 객체를 생성하고 반환한다. 파일이 없는 경우는 null이 리턴된다. 확장자는 AQuery.FORMAT 에 지정된 값으로 사용한다.

* **Returns**: AQuery

* **Parameters**: 
	* **`qryName`** {String} 쿼리명

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
```

<br/>

### getTrType()

쿼리의 유형을 반환한다.

* **Returns**: String

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var trType = aquery.getTrType();
```

<br/>

### getValue( key )

키에 해당하는 쿼리 정보를 반환한다.

* **Returns**: All

* **Parameters**: 
	* **`key`** {String} .

* **Usage**: 
```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var qryName = aquery.getValue('name');
```

<br/>

### hasQueryDataKey( queryData )

쿼리데이터에 현재 쿼리 정보에 있는 FID key 가 있는지를 체크한다. 관계있는 FID 가 하나라도 있으면 true 를 리턴한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`queryData`** {String} 쿼리데이터 객체

<br/>

### loadQuery( url, callback )

url 위치의 query 파일을 로드한다. 로드가 완료되면 callback 함수를 호출해 준다.

* **Parameters**: 
	* **`url`** {String} .
	* **`callback`** {String} .

<br/>

### removeQueryComp( containerId, type, acomp )

AQuery 객체에 type 과 연결된 컴포넌트를 제거한다.

* **Parameters**: 
	* **`containerId`** {String} 컴포넌트가 포함된 화면의 id
	* **`type`** {String} 'input' or 'output'
	* **`acomp`** {String} 제거할 컴포넌트

<br/>
<br/>
