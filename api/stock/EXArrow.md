# EXArrow
> **Extends**: `AComponent`

Arrow

<br/>

## Properties


### direction

화살표 방향

* **Type**: `String`
* **Default**: `'top'`

<br/>

### svgEl

SVG Dom element

* **Type**: `Object`
* **Default**: `null`

<br/>

### frwName



* **Type**: ``
* **Default**: ``

<br/>

### stopTagArr



* **Type**: ``
* **Default**: ``

<br/>
### polygonTag



* **Type**: ``
* **Default**: ``

<br/>
### gradientTag



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### getEndColor()

화살표의 그라디언트 태그의 끝색을 리턴합니다.

* **Returns**: String

<br/>

### getEndOpacity()

화살표의 그라디언트 태그의 끝 투명도를 리턴합니다.

* **Returns**: Float

<br/>

### getStartColor()

화살표의 그라디언트 태그의 시작색을 리턴합니다.

* **Returns**: String

<br/>

### getStartOpacity()

화살표의 그라디언트 태그의 시작 투명도를 리턴합니다.

* **Returns**: Float

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출합니다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출합니다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {Object} context 에 매핑된 이벤트 수신자

<br/>

### setColors( sColor, eColor, sOpacity, eOpacity )

화살표의 그라디언트 태그에 색상을 셋팅합니다.

* **Parameters**: 
	* **`sColor`** {String} 시작색 ex) '#999999' or 'rgba(0,0,0,1)'
	* **`eColor`** {String} 끝색 ex) '#555555' or 'rgba(0,0,0,1)'
	* **`sOpacity`** {Float} 시작 투명도 ex) 0.0 ~ 1.0
	* **`eOpacity`** {Float} 끝 투명도 ex) 0.0 ~ 1.0

<br/>

### setDefsId()

화살표의 그라디언트 태그에 디폴트 아이디를 셋팅합니다

<br/>

### setDirection( direction )

화살표의 방향을 셋팅합니다.

* **Parameters**: 
	* **`direction`** {String} ex) 'top' or 'bottom' or 'left' or 'right'

<br/>

### setEndColor( color )

화살표의 그라디언트 태그의 끝색을 셋팅합니다.

* **Parameters**: 
	* **`color`** {String} 끝색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>

### setEndOpacity( opacity )

화살표의 그라디언트 태그의 끝 투명도를 셋팅합니다.

* **Parameters**: 
	* **`opacity`** {Float} ex) 0.0 ~ 1.0

<br/>

### setRotate( angle )

화살표의 방향을 수치로 셋팅합니다.

* **Parameters**: 
	* **`angle`** {Number} ex) 0 ~ 360

<br/>

### setStartColor( color )

화살표의 그라디언트 태그의 시작색을 셋팅합니다.

* **Parameters**: 
	* **`color`** {String} 시작색 ex) '#999999' or 'rgba(0,0,0,1)'

<br/>

### setStartOpacity( opacity )

화살표의 그라디언트 태그의 시작 투명도를 셋팅합니다.

* **Parameters**: 
	* **`opacity`** {Float} ex) 0.0 ~ 1.0

<br/>

### setPoints()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
