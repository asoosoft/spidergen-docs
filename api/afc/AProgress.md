# AProgress
**Extends**: [`AComponent`](AComponent.html#acomponent)

프로그레스 컴포넌트

<br/>

## Properties


### bar \<jQuery Object>

프로그레스 객체 하위의 jQuery Object

<br/>

### value \<Number>

프로그레스의 값

<br/>
<br/>

## Instance Methods

### getData()

[getValue()](#getvalue)와 같다.

- **Returns** \<Number>

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getValue()

프로그레스의 백분율 값을 리턴한다.

- **Returns**: Number

<br/>

### init( context, evtListener )

컴포넌트 객체를 생성한 후 초기화 할 때 호출한다. 코딩을 이용하여 동적으로 객체를 생성할 경우 사용한다. 일반적으로 파라미터를 생략하여 기본값으로 생성 되도록 해준다.

- `context` \<String> 컴포넌트 생성 정보
- `evtListener` \<String> 이벤트 발생 시 수신할 객체

```js
var progress = new AProgress();
progress.init();
```

<br/>

### setData( data )

[setValue( data )](#setvalue-value-)와 같다.

- `data` \<Number> 값

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setValue( value )

프로그레스의 백분율 값을 셋팅한다.

- `value` \<Number> 값

<br/>
<br/>
