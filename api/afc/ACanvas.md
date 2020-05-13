# ACanvas
**Extends**: [`AComponent`](AComponent.html#AComponent)

캔버스 컴포넌트

<br/>

## Properties

### ctx \<Object>

캔버스의 context이다.

<br/>
<br/>

## Instance Methods

### resizeCanvas()

cavas의 사이즈를 재조정한다. updatePosition함수가 호출 될 때 호출된다.

<br/>

### getData()

데이터를 리턴한다.

- **Returns** \<String>

<br/>

### setData( data )

데이터를 세팅한다.

- `data` \<String> 데이터

```js
var data = 'abc';
canvas.setData(data);
```

<br/>

### updatePosition( pWidth, pHeight )

캔버스의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. <br/>브라우저의 사이즈가 변경될 경우 자동으로 호출된다.

- `pWidth` \<String> 부모의 너비 = Canvas의 넓이
- `pHeight` \<String> 부모의 높이 = Canvas의  높이

<br/>
<br/>
