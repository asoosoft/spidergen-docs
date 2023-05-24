# AQuery
> **Extends** 

query 파일의 구조정보를 관리하는 클래스
</br>
쿼리시스템을 이용한 통신에 대한 설명은 [IO System](../../guide/06.%20IO%20System.md) 참고

<br/>

## Class Variables
AQuery.IKEY = 1;
AQuery.IFID = 2;
AQuery.IVALUE = 3;
AQuery.ITYPE = 4;
AQuery.ISIZE = 5;
AQuery.IEXP = 6;

### AQuery.IDESC \<Number>

데이터 포맷 정보 중 설명 위치 `0`

<br/>

### AQuery.IKEY \<Number>

데이터 포맷 정보 중 키 위치 `1`

<br/>

### AQuery.IFID \<Number>

데이터 포맷 정보 중 FID 위치 `2`

<br/>

### AQuery.IVALUE \<Number>

데이터 포맷 정보 중 값 위치 `3`

<br/>

### AQuery.ITYPE \<Number>

데이터 포맷 정보 중 타입 위치 `4`

<br/>

### AQuery.ISIZE \<Number>

데이터 포맷 정보 중 길이 위치 `5`

<br/>

### AQuery.IEXP \<Number>

데이터 포맷 정보 중 소수점 길이 위치 `6`

<br/>

### AQuery.BINARY \<Number>

데이터 타입이 바이너리 `-2`

<br/>

### AQuery.STRING \<Number>

데이터 타입이 문자열 `-1`

<br/>

### AQuery.UNSIGNED \<Number>

데이터 타입이 양의 정수 `1`

<br/>

### AQuery.SIGNED \<Number>

데이터 타입이 정수 `0`

<br/>
<br/>

## Instance Variables

### query \<Object>

json 형식의 쿼리파일을 객체화한 변수

```js
this.query = 
{
	"meta": {},
	//... 그외 다른 항목 ex) "trType": 1,  ex)"realType": 0
	"name": "obcpp_logn_101a",
	"input":
	{
		"InBlock1":
		{
			//"type": "input",
			"format":
			[
				//설명,필드키,FID,custom,데이터형,사이즈,지수
				["단축코드","D1단축코드",16013,,-1,16,0],
				...
			]
		},
		
		...
	},
	
	"output":
	{
		"OutBlock1":
		{
			//"type": "output",
			"format":
			[
				//설명,필드키,FID,기본값,데이터형,사이즈,지수
	    		["현재가","D1현재가",15001,,0,4,-2], 
				...
			]
		},
		
		...
	}
};
```

<br/>

### queryComps \<Object>

쿼리와 연결된 컴포넌트들의 집합

* `Default` `{}`

```js
this.queryComps =
{
	//화면 번호
	'1500': [AButton, ALabel, ...],
	'2500': [AEdit, AEdit, ...],
};
```

<br/>
<br/>


## Class Methods

### AQuery.getQuery( qryName )

[AQuery.getSafeQuery( qryName )](#-AQuery.getSafeQuery-qryName-) 함수와는 다르게 로드된 쿼리 객체가 없는 경우 null 을 리턴한다.

* `qryName` \<String> 쿼리명

```js
var aquery = AQuery.getQuery('sample01');
```

<br/>

### AQuery.getSafeQuery( qryName )

쿼리명에 해당하는 쿼리 객체를 반환한다. 로드된 쿼리 객체가 없으면 쿼리정보를 Query 폴더의 쿼리명으로된 파일에서 읽어서 파싱한 정보를 가지고 있는 쿼리 객체를 생성하고 반환한다. 파일이 없는 경우는 null이 리턴된다. 확장자는 AQuery.FORMAT 에 지정된 값으로 사용한다.

* `qryName` \<String> 쿼리명
* **Returns** \<[AQuery](#aquery)>

```js
var aquery = AQuery.getSafeQuery('sample01');
```

<br/>

### AQuery.setQuery( qryName, aquery )

쿼리 정보 객체를 저장한다.

* `qryName` \<String> 쿼리명
* `aquery` \<[AQuery](#aquery)> AQuery 객체

<br/>

## Instance Methods

### addQueryComp( containerId, type, acomp )

AQuery 객체에 type 과 연결된 컴포넌트를 등록한다. 컴포넌트는 containerId(화면)단위로 등록된다. 등록된 컴포넌트는 input 인 경우 데이터를 전송할 때 컴포넌트의 값을 참조하여 데이터를 버퍼에 셋팅한다. output 인 경우 데이터 수신 시 수신된 데이터를 컴포넌트에 반영한다

* `containerId` \<String> 컴포넌트가 포함된 화면의 id
* `type` \<String> 'input' or 'output'
* `acomp` \<Component Object> 등록할 컴포넌트

<br/>

### eachQueryBlock( type, callback )

type 영역의 모든 블럭의 구조정보를 콜백함수로 넘겨준다. block 객체의 구조는 [getQueryBlock](#-getQueryBlock-type,-blockName-) 참조.

* `type` \<String> 'input' or 'output'
* `callback` \<String> function(name, block)

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

쿼리의 버전을 반환한다.(파일의 resourceVersion 항목)

* **Returns** \<String>

```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var version = aquery.getIoVer();
```

<br/>

### getMeta()

쿼리 파일의 메타 정보를 리턴한다.(파일의 meta 항목)

* **Returns** \<Object>

```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var meta= aquery.getMeta();
```

<br/>

### getName()

쿼리명을 리턴한다.(파일의 name 항목)

* **Returns** \<String>

```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var name= aquery.getName();
```

<br/>

### getQueryBlock( type, blockName )

type 영역의 특정 블럭의 구조정보 객체를 리턴한다.

* `type` \<String> 'input' or 'output'
* `blockName` \<String> ex) 'InBlock1', 'OutBlock2'
* **Returns** \<Object>

```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var inblock1 = aquery.getQueryBlock('input', 'InBlock1');
var outblokc2 = aquery.getQueryBlock('output', 'OutBlock2');
```

<br/>

### getQueryComps( containerId, type )

AQuery 객체에 type 과 연결된 컴포넌트들을 배열로 리턴한다.

* `containerId` \<String> 컴포넌트가 포함된 화면의 id
* `type` \<String> 'input' or 'output'
* **Returns** \<Array> 컴포넌트 배열

<br/>

### getQueryType()

쿼리의 유형을 리턴한다.(파일의 queryType 항목)

* **Returns** \<String>

```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var qryType= aquery.getQueryType();
```

<br/>

### getRealType()

쿼리의 실시간유형을 리턴한다.(파일의 realType 항목)

* **Returns** \<String>

```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var realType= aquery.getRealType();
```

<br/>

### getTrType()

쿼리의 유형을 반환한다.(파일의 trType 항목)

* **Returns** \<String>

```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var trType = aquery.getTrType();
```

<br/>

### getValue( key )

키에 해당하는 쿼리 정보를 반환한다.

* `key` \<String> .
* **Returns** \<All>

```js
var aquery = AQuery.getSafeQuery('sample01');
if(!aquery) return;
var qryName = aquery.getValue('name');
```

<br/>

### hasQueryDataKey( queryData )

쿼리데이터에 현재 쿼리 정보에 있는 FID key 가 있는지를 체크한다. 관계있는 FID 가 하나라도 있으면 true 를 리턴한다.

* `queryData` \<[AQueryData](./AQueryData.md)> 쿼리데이터 객체
* **Returns** \<Boolean>

<br/>

### loadQuery( url, callback )

url 위치의 query 파일을 로드한다. 로드가 완료되면 callback 함수를 호출해 준다.

* `url` \<String> .
* `callback` \<String> .

<br/>

### removeQueryComp( containerId, type, acomp )

AQuery 객체에 type 과 연결된 컴포넌트를 제거한다.

* `containerId` \<String> 컴포넌트가 포함된 화면의 id
* `type` \<String> 'input' or 'output'
* `acomp` \<Component Object> 제거할 컴포넌트

<br/>
<br/>
