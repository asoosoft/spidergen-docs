# ASlideView
> **Extends**: ``

슬라이드 뷰

<br/>

## Properties

### inx

### delegator

<br/>
<br/>

## Methods

### init()

컴포넌트를 생성하고 초기화 할 때 호출합니다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출해야 합니다.

- `context` \<Object> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<Object> context에 매핑된 이벤트 수신자

```js
var sildeView = new ASlideView();
sildeView.init();
```

<br/>

### setSpeed( speed )

슬라이드 뷰가 움직이는 속도를 설정합니다.

- `speed` \<Number> 속력, 숫자가 클 수록 느리게 움직입니다.

```js
this.sildeView.setSpeed(100);
```

<br/>

### setEasing( easing ) 동작 확인 필요

감속 옵션을 설정합니다.

- `easing` \<String> Easing 효과 이름 ex) linear, swing, easeOutQuad...

```js
this.slideView.setEasing( 'easeOutElastic' );
```

<br/>

### enableScrlManager()

터치 이벤트를 핸들링하여 자체적으로 구현한 스크롤 기능을 활성화 한다. 내부적으로 [ScrollManager](../libray/ScrollManager.html) 가 사용된다.

<br/>

### setDelegator( delegator ) 삭제?

<br/>

### setButtonView( buttonView )

<br/>

### setButtonFlexLayout( buttonFlexLayout )

- `buttonFlexLayout` \<>

<br/>

### onFlexBtnClick( comp, info )

- `comp` \<>
- `info` \<>

<br/>

### selectButton( selBtn )

<br/>

### addItems( urlArr, dataArr, isPrepend, asyncCallback ) 수정필요

여러개의 url 을 동시에 추가한다. 단, urlArr 과 dataArr은 1:1 로 매칭된다.

- 'urlArr' \<String>
- 'dataArr' \<Object>
- 'isPrepend' \<>
- 'asyncCallback' \<Function>

<br/>

### addItem( urlArr, dataArr, isPrepend, asyncCallback ) 수정필요

- 'urlArr' \<String>
- 'dataArr' \<Object>
- 'isPrepend' \<>
- 'asyncCallback' \<Function>

```js
this.slideView.addItem('Source/slideViewItem01.lay', [null]);
```

<br/>


### onBtnClick( comp, info )

makeButton으로 만든 버튼을 클릭했을때 호출되는 함수, 객체에 저장해둔 value값을 리턴한다

* `comp` \<AButton> 버튼 객체
* `info` \<Object> listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값

<br/>



### addDisableManager( disableManager )



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### removeAllItems()

슬라이드 뷰 초기화, 모든 아이템을 제거한다.

```js
this.slideView.removeAllItems();
```

<br/>

### getItem( index )

인덱스 값을 이용하여 아이템을 얻는다.

- `index` \<Number> 원하는 아이템의 인덱스 값
- **Return** \<Object>


```js
this.slideView.getItem(0);
```

<br/>

### getItems()

모든 아이템을 배열로 얻는다.

- **Return** \<Array>

```js
this.slideView.getItems();
```

<br/>

### indexOfItem( item )

인덱스 값을 이용하여 아이템을 얻는다.

- `item` \<Number> 인덱스 번호
- **Return** \<Object>

```js
this.slideView.indexOfItem(0);
```

<br/>

### slideTo(index, isReport)

슬라이드를 이동합니다.

- `index` \<Number> 이동할 인덱스 번호
- `isReport` \<Boolean> change 이벤트를 발생할지 여부

```js
this.slideView.slideTo(0, true);
```

<br/>

### slidePrev()

이전 슬라이드로 이동합니다. (인덱스 번호 기준)

```js
this.slideView.slidePrev();
```

<br/>

### slideNext()

다음 슬라이드로 이동합니다. (인덱스 번호 기준)


```js
this.slideView.NextPrev();
```

<br/>

### scrollXImplement()

x축으로 30%이상 이동시 끝까지 이동하게 한다.

```js
this.slideView.scrollXImplement();
```

<br/>

### scrollYImplement()

y축으로 30%이상 이동시 끝까지 이동하게 한다.

```js
this.slideView.scrollYImplement();
```

<br/>

### getMoveUnit()

해당 슬라이드의 이동 방향(가로, 세로)에 대한 길이를 구한다.</br>

```js
var a = slideView.getMoveUnit();
```

<br/>

### updatePosition( pWidth, pHeight )

컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. <br/>
브라우저의 사이즈가 변경될 경우 자동으로 호출된다.

* `pWidth` \<Number> 부모의 너비
* `pHeight` \<Number> 부모의 높이

<br/>
<br/>

## Attribute 수정 필요

### Option

- **Direction:** 설명이 필요합니다.
    * **horizontal:** 설명이 필요합니다.
    * **vertical:** 설명이 필요합니다.

<br/>
