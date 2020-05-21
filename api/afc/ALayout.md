# ALayout
**Extends**: [`AComponent`](AComponent.html#AComponent)

레이아웃 컴포넌트

실제로 사용되지 않고 [GridLayout](AGridLayout.html), [FlexLayout](AFlexLayout.html)에서 상속받는다.

<br/>

## Instance Methods

### getData()

컴포넌트의 데이터를 리턴한다.

- **Returns** \<Any>

<br/>

### getDroppable()

컴포넌트 내부에 드랍 가능여부를 리턴한다.

- **Returns** \<Boolean>

<br/>

### getMappingCount()

매핑가능한 갯수를 반환한다.

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### removeFromView()

부모뷰로 부터 레이아웃 컴포넌트를 제거한다.

<br/>

### reset()

하위의 컴포넌트들을 리셋한다.

<br/>

### setData( data )

하위의 컴포넌트들에 데이터를 세팅한다.

- `data` \<Array>

```js
layout.setData({'1', '2', '3'});
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### updatePosition( pWidth, pHeight )

컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. 브라우저의 사이즈가 변경될 경우 자동으로 호출된다.

- `pWidth` \<Number> 부모의 너비
- `pHeight` \<Number> 부모의 높이

<br/>
<br/>
