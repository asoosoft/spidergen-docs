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
  {left : , top : , right : , bottom}


<br/>

### absRect()

가로 너비 와 세로 높이 값이 0 보다 작을 경우 좌우 또는 상하 대칭 값을 설정한다.

<br/>

### reverseX()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### reverseY()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### refreshSize()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### refreshRect()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### isSubsetPt()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### isSubsetRt()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### isIntersectRt()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### isRectEmpty()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
