# AToolBar
**Extends**: [`AView`](AView.html#aview)

툴바

<br/>

## Instance Methods

### init( context, evtListener )

컴포넌트 객체를 생성한 후 초기화 할 때 호출한다. 코딩을 이용하여 동적으로 객체를 생성할 경우 사용한다. 일반적으로 파라미터를 생략하여 기본값으로 생성 되도록 해준다.

- `context` \<String> 컴포넌트 생성 정보
- `evtListener` \<String> 이벤트 발생 시 수신할 객체

```js
var toolbar = new AToolBar();
toolbar.init();
```

<br/>

### isHscroll()

현재 가로 스크롤이 가능한 상태인지 여부를 리턴한다

- **Returns** \<Boolean>

<br/>

### scrollOffset( offset )

툴바의 현 위치에서 offset만큼 Left 스크롤 시킨다

- `offset` \<Number> 이동 시킬 값

<br/>

### scrollTo( leftPos )

툴바의 pos에서 left 위치로 스크롤 시킨다

- `leftPos` \<Number> 이동 시킬 위치 값

<br/>
<br/>

## Events

공통부분은 설명은 \<[AView Events](AView.html#events)> 참조

### drop

드롭 할 때 발생되는 이벤트

<br/>

