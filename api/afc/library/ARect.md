# ARect
> **Extends**: `Object`

Rect 정보 자료구조

<br/>

## Properties

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### setEmpty()

rect 정보(left, top, widht, height)를 0으로 초기화 한다.

<br/>

### setSizeRect(l, t, w, h)

rect 객체의 사이즈 정보를 설정한다.

- `l` \<Number> left 정보 값
- `t` \<Number> top 정보 값
- `w` \<Number> width 정보 값
- `h` \<Number> height 정보 값

```js
var rect = new ARect();
rect.setSizeRect(10, 10, 10, 10);
console.log(rect);
---------------------------------------------------------------
ARect {left: 10, top: 10, width: 10, height: 10, right: 20, …}
```

<br/>

### setPointRect(l, t, r, b)

rect 객체의 위치 정보를 설정한다.

- `l` \<Number> left 정보 값
- `t` \<Number> top 정보 값
- `r` \<Number> right 정보 값
- `b` \<Number> bottom 정보 값

<br/>

### offsetRect(offsetX, offsetY)

rect 객체의 위치정보에 보정 정보를 추가한다.

- `offsetX` \<Number> left, right 에 추가 할 보정값
- `offsetY` \<Number> top, bottom 에 추가 할 보정값



<br/>

### copyRect(src)

복사할 객체의 rect 정보를 복사합니다.

- `src` \<Object> 복사할 객체의 rect 정보. 보통 AComponent.getBoundRect() 또는 
  {left : value, top : value, right : value, bottom : value} 형태의 객체

```js
// 버튼 ID : btn

var btnRect = this.btn.getBoundRect(); //컴포넌트 rect 정보 추출
console.log(btnRect);
	
var rect = new ARect();                   //rect 정보 객체 생성
rect.copyRect(this.btn.getBoundRect());   //컴포넌트 rect 정보 복사
	
console.log(rect);
------------------------------------------------------------------
DOMRect {x: 510, y: 50, width: 80, height: 22, top: 50, …}
ARect {x: 510, y: 50, width: 80, height: 22, top: 50, …}
```

<br/>

### absRect()

rect 정보의 width 값이 0보다 작을 경우 left와 right 위치값을 서로 교환 설정한다.
rect 정보의 height 값이 0보다 작을 경우 top과 bottom 위치값을 서로 교환 설정한다.

<br/>

### reverseX()

rect 정보의 left 위치값과 right 위치값을 서로 교환 설정한다.

<br/>

### reverseY()

rect 정보의 top 위치값과 bottom 위치값을 서로 교환 설정한다.

<br/>

### refreshSize()

rect 정보의 사이즈값(width, height)을 현재 rect의 위치값을 기준으로 새로 설정한다.

<br/>

### refreshRect()

rect 정보의 위치값(right, bottom)을 현재 rect의 위치값과 사이즈값을 기준으로 새로 설정한다.

<br/>

### isSubsetPt(x, y)

파라미터의 포인트 위치(x, y)가 rect 내부에 있을 경우 true, 외부에 있을경우 false를 리턴한다.

- `x` \<Number> 포인트의 x 좌표
- `y` \<Number> 포인트의 y 좌표

- **Returns** \<Boolen> 

```js
var rect = new ARect(10,10,10,10); //left:10, top:10, width:10, height:10

var result1 = rect.isSubsetPt(5, 5);  //left:5, top:5
console.log(result1);
	
var result2 = rect.isSubsetPt(12, 12); //left:12, top:12
console.log(result2);
------------------------------------------------------------------
false
true
```

<br/>

### isSubsetRt(rt)

전달된 rt의 위치정보가 rect의 위치정보에 포함 될 경우 true, 포함되지 않을 경우 false를 리턴한다.

- `rt` \<Object> rect 정보. 보통 AComponent.getBoundRect() 또는 {left : value, top : value, right : value, bottom : value} 형태의 객체

```js
// 뷰 ID : menuBarView, 버튼 ID : btn
// 버튼이 뷰 영역 밖에 위치시킨다.

var rect = new ARect();
rect.copyRect(this.menuBarView.getBoundRect());   //menuBarView 의 rect 정보를 복사한다.
var result = rect.isSubsetRt(this.btn.getBoundRect()); //btn이 menuBarView 영역내 있는지 확인한다.
	
console.log(result);
------------------------------------------------------------------
false
```

<br/>

### isIntersectRt(rt)

전달된 rt의 위치 정보가 rect의 위치정보와 교차될 경우 true, 그렇지 않을 경우 false를 리턴한다.

- `rt` \<Object> rect 정보. 보통 AComponent.getBoundRect() 또는 {left : value, top : value, right : value, bottom : value} 형태의 객체

<br/>

### isRectEmpty()

rect 정보의 사이즈정보(width, height) 값을 0으로 초기화 한다.

<br/>
