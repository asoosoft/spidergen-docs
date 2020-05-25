# ScrollIndicator
> **Extends**

스크롤바를 표현하는 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

### $indicator \<jQuery Object>

스크롤바를 표현하는 jQuery Object

<br/>

### isScrollVert \<Boolean>

스크롤바 세로방향여부

<br/>

### isVisible \<Boolean>

보임 상태 여부

<br/>

### scrollOffset \<Number>

스크롤 위치값

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### init( type, scrlElement )

스크롤바를 초기화한다. HTML 스크롤바 숨김처리, 스크롤바 생성 등

* `type` \<String> 스크롤바 방향 vetical / horizontal
* `scrlElement` \<HTMLElement> 스크롤 영역 엘리먼트

```js
var scrlIndicator = new ScrollIndicator('vertical', this.view.element);
```

<br/>

### destroy()

스크롤바를 제거하고 기존 스크롤바 보이게 한다.

<br/>

### hide()

스크콜바 안보이게 한다.

<br/>

### setStyle( styleObj )

스크롤바의 스타일을 지정한다.

* `styleObj` \<Object> 스타일 객체 ex. { "background-color": "red" }

<br/>

### disableHide()

스크롤이 움직이다 멈추면 자동으로 숨김처리 되지 않게 설정한다.
 
```js
//scrlIndicator 는 ScrollIndicator 객체
scrlIndicator.disableHide();
```

<br/>

### resetScrollPos( callback )

스크롤바가 보여질 때 호출되는 함수를 지정한다. 함수 내에서는 보통 스크롤바는 스크롤 엘리먼트와 동일한 부모를 가지고 있고 스크롤 엘리먼트의 위치가 0 이 아닐수도 있으므로 스크롤의 위치를 변경한다. 0 인 경우에는 

* `callback` \<Function> 함수

```js
var thisObj = this;
//scrlIndicator 는 ScrollIndicator 객체
scrlIndicator.resetScrollPos(function()
{
    var value = thisObj.view.getPos().top;
    this.setStyle({top: value+'px'});
    this.setScrollOffset(value);
});
```

<br/>

### setScrollOffset( scrollOffset )

스크롤 시작 위치를 지정한다.

* `scrollOffset` \<Number> 스크롤 시작 위치

<br/>

### show()

스크롤바를 보이게 한다.

<br/>