# AFlowThreeLine
**Extends**: [`AComponent`](./../afc/AComponent.md)

두번 꺽인 선을 그리는 컴포넌트.

<br/>

## Class Variables

<br/>

## Instance Variables

<br/>

## Class Methods

<br/>

## Instance Methods

### resizePath()

선을 다시 그린다. 기본적으로 컴포넌트의 사이즈 정보가 변경될 떄 자동으로 호출된다.

<br/>

### setArrow( info )

선의 화살표 사용 여부를 지정한다.

- `info` \<Boolean> 화살표 사용 여부

<br/>

### setArrowPosition( info )

선의 화살표 위치를 지정한다.

- `info` \<String> 화살표 위치 문자열

```js
this.flowLine.setArrowPosition('start');  //시작점
this.flowLine.setArrowPosition('end');    //끝점
this.flowLine.setArrowPosition('both');   //양쪽모두
```

<br/>

### setLineColor( color )

선의 색상을 지정한다.

- `color` \<String> 색상 정보 문자열

<br/>

### setStrokeWidth( value )

선의 두께를 지정한다.

- `value` \<String> or <Number> 선의 두께 값

<br/>

