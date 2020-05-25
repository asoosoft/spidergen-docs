# RefreshIndicator
> **Extends**

새로고침 표시하는 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

### element \<HTMLElement>

인디케이터가 표현될 엘리먼트

<br/>

### acomp \<[AComponent](../afc/AComponent.md)>

인디케이터가 표현될 컴포넌트

<br/>

### iconColor \<String>

아이콘 색상

<br/>

### spinnerColor \<String>

스피너 색상

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### init( comp, ele )

RefreshIndicator 를 초기화한다. 

* `comp` \<[AComponent](../afc/AComponent.md)> 컴포넌트 객체
* `ele` \<HTMLElement> 엘리먼트

```js
var ri = new RefreshIndicator();
ri.init(view, view.element);
ri.setRefreshFunc(function()
{
    console.log('refresh');
    ri.hide();
});
```

<br/>

### hide()

RefreshIndicator 를 숨긴다. 보통 refresh 콜백함수에서 사용한다.

<br/>

### setRefreshFunc( refreshFunc )

리프레쉬 완료시 호출되는 함수를 지정한다.

* `refreshFunc` \<Function> 콜백함수

<br/>

### setIconColor( color )

아이콘의 색상을 지정한다.

* `color` \<String> 색상

```js
var ri = new RefreshIndicator();
ri.setIconColor('red');
ri.init(view, view.element);
ri.setRefreshFunc(function()
{
    console.log('refresh');
    ri.hide();
});
```

<br/>

### setSpinnerColor( color )

스피너의 색상을 지정한다.

* `color` \<String> 색상

```js
var ri = new RefreshIndicator();
ri.setSpinnerColor('red');
ri.init(view, view.element);
ri.setRefreshFunc(function()
{
    console.log('refresh');
    ri.hide();
});
```

<br/>

### destroy()

refreshIndicator 를 제거한다.

<br/>