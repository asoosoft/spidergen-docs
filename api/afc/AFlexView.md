# AFlexView
**Extends** [`AComponent`](AComponent.html#acomponent)

뷰(View1)를 유동적으로 생성하는 컴포넌트

<br/>

## Properties


### views \<[AView](AView.html#aview) Array>

화면을 구성하기 위해 구분된 뷰(AView)들을 저장한 배열

<br/>

### viewDirection  \<String>

화면의 뷰들을 위치 시키는 방향을 저장한 변수. 값은 row, colum  

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### getView( index )

index 순번에 해당하는 뷰를 반환한다.

- `index` \<Number> 순번

- **Returns** \<[AView](AView.html#aview)> 뷰 객체

```js
// FlexView ID : flexView 일경우
// 뷰가 2개 추가 됨. view01.lay, view02.lay

this.flexView.setViewDirection('row');
this.flexView.insertView('Source/view01.lay');
this.flexView.insertView('Source/view02.lay');
console.log(this.flexView.getView(0));
-------------------------------------------------------
view01 {element: ... }
```

<br/>

### insertView( view, index )

index 번째 뷰 앞에 view를 추가한다.

- `view` \<[AView](AView.html#aview) or String> 뷰 객체 또는 뷰 Url

- `index` \<Number> 추가할 뷰의 기준 순번

```js
// FlexView ID : flexView 일경우
// 뷰가 2개 추가 됨. view01.lay, view02.lay

this.flexView.setViewDirection('row');
this.flexView.insertView('Source/view01.lay');
this.flexView.insertView('Source/view02.lay');

console.log(this.flexView.getView(1));              // 순번이 1인 뷰
this.flexView.insertView('Source/view03.lay', 1);   // 순번이 1인 뷰 앞에 추가 	
console.log(this.flexView.getView(1));              // 순번이 1인 뷰
-------------------------------------------------------
view02 {element: ... } 
view03 {element: ... }
```


<br/>

### removeAllViews()

FlexView 컴포넌트 내 모든 뷰를 삭제한다.

```js
// FlexView ID : flexView 일경우
// 뷰가 2개 추가 됨. view01.lay, view02.lay, view03.lay

this.flexView.setViewDirection('row');
this.flexView.insertView('Source/view01.lay');
this.flexView.insertView('Source/view02.lay');	
this.flexView.insertView('Source/view03.lay');	
	
console.log(this.flexView.views.length);
this.flexView.removeAllViews();             // 모두 삭제	
console.log(this.flexView.views.length);
-------------------------------------------------------
3
0
```

<br/>

### setViewDirection( direction )

뷰의 정렬 방향을 설정한다.

- `direction` \<String> row : 행, column : 열

```js
// FlexView ID : flexView 일경우
// 뷰가 2개 추가 됨. view01.lay, view02.lay, view03.lay

this.flexView.setViewDirection('row');
console.log(this.flexView.viewDirection);
-------------------------------------------------------
row
```

<br/>
<br/>
