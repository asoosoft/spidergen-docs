# ASlideView
> **Extends**: ``

슬라이드 뷰

<br/>

## Instance Variables

### inx

현재 아이템의 인덱스 값

<br/>
<br/>

## Instance Methods

<br/>

### addDisableManager( disableManager )

- `disableManager` \<>

<br/>

### addItem( urlArr, dataArr, isPrepend, asyncCallback )

- 'urlArr' \<String>
- 'dataArr' \<Object>
- 'isPrepend' \<Boolean> True면 앞에, False면 뒤에 추가된다.
- 'asyncCallback' \<Function>

```js
this.slideView.addItem('Source/slideViewItem01.lay', [null]);
```

<br/>

### addItems( urlArr, dataArr, isPrepend, asyncCallback )

여러개의 url 을 동시에 추가한다. 단, urlArr과 dataArr은 1:1 로 매칭된다.

- 'urlArr' \<String>
- 'dataArr' \<Object>
- 'isPrepend' \<Boolean> True면 앞에, False면 뒤에 추가된다.
- 'asyncCallback' \<Function>

<br/>

### enableScrlManager()

터치 이벤트를 핸들링하여 자체적으로 구현한 스크롤 기능을 활성화 한다.<br/>
내부적으로 [ScrollManager](../libray/ScrollManager.html)가 사용된다.

<br/>

### getItem( index )

인덱스 값을 이용하여 아이템을 얻는다.

- `index` \<Number> 원하는 아이템의 인덱스 값
- **Return** \<Object>

<br/>

### getItems()

모든 아이템을 배열로 얻는다.

- **Return** \<Array>

<br/>

### getMoveUnit()

해당 슬라이드의 이동 방향(가로, 세로)에 대한 길이를 구한다.</br>

<br/>

### indexOfItem( item )

인덱스 값을 이용하여 아이템을 얻는다.

- `item` \<Number> 인덱스 번호
- **Return** \<Object>

<br/>

### setButtonView( buttonView )

슬라이드 뷰의 버튼 기능을 하는 버튼들을 가진 뷰를 설정한다.

- `buttonView` \<AView>

<br/>

### setButtonFlexLayout( buttonFlexLayout )

슬라이드 뷰의 버튼 기능을 하는 버튼들을 가진 플렉스 레이아웃을 설정한다.

- `buttonFlexLayout` \<AFlexLayout>

<br/>

### setDelegator( delegator )

컴포넌트에 delegator를 설정한다.

- `delegator` \<Object> delegator

<br/>

### setEasing( easing )

감속 옵션을 설정합니다.

- `easing` \<String> Easing 효과 (linear / swing / easeOutQuad)

```js
this.slideView.setEasing( 'easeOutElastic' );
```

<br/>

### setSpeed( speed )

슬라이드 뷰가 움직이는 속도를 설정합니다.

- `speed` \<Number> 속력. 숫자가 클 수록 느리게 움직인다.

<br/>

### selectButton( selBtn )

버튼을 선택한다.

- `selBtn` \<AButton>

<br/>

### slideNext()

다음 슬라이드로 이동합니다. (인덱스 번호 기준)

<br/>

### slidePrev()

이전 슬라이드로 이동합니다. (인덱스 번호 기준)

<br/>

### slideTo(index, isReport)

슬라이드를 이동한다.

- `index` \<Number> 이동할 인덱스 번호
- `isReport` \<Boolean> change 이벤트를 발생할지 여부

<br/>

### scrollXImplement()

x축으로 30%이상 이동시 해당 방향의 끝까지 이동하게 한다.

<br/>

### scrollYImplement()

y축으로 30%이상 이동시 해당 방향의 끝까지 이동하게 한다.

<br/>

### onBtnClick( comp, info )

makeButton으로 만든 버튼을 클릭했을때 호출되는 함수, 객체에 저장해둔 value값을 리턴한다

* `comp` \<AButton> 버튼 객체
* `info` \<Object> listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값

<br/>

### onFlexBtnClick( comp )

플렉스 레이아웃에 존재하는 버튼을 클릭한다.</br>
버튼의 인덱스 값과 슬라이드 뷰의 아이템 인덱스 값을 이용한다.

- `comp` \<AButton>

<br/>

### removeAllItems()

슬라이드 뷰 초기화, 모든 아이템을 제거한다.

<br/>

### updatePosition( pWidth, pHeight )

컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출한다. <br/>
브라우저의 사이즈가 변경될 경우 자동으로 호출된다.

* `pWidth` \<Number> 부모의 너비
* `pHeight` \<Number> 부모의 높이

<br/>
<br/>

## Attribute

### Option

- `Direction` 방향 설정
    - `horizontal` 수평 방향
    - `vertical` 수직 방향

<br/>