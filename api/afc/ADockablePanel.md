# ADockablePanel
> **Extends**: 

ADockablePanel

<br/>

## Properties


### dockDir \<String>

ADockingFrame 이 도킹될 때 창분할 방향

* `Default` "column"

<br/>
<br/>

## Instance Methods

### activeFrame( frame )

해당 frame을 활성화 한다.

* `frame` \<ADockingFrame> frame

```js
//frame은 ADockingFrame객체이다.
dockablePanel.activeFrame();
```

<br/>

### activeFrameByIndex( inx )

특정 위치의 프레임을 활성화 한다.

* `inx` \<Number> 활성화할 프레임의 위치

```js
//frame은 ADockingFrame객체이다.
dockablePanel.activeFrameByIndex(0);
```
<br/>

### dockFrame( frame, inx, pos, dockSize )

frame을 도킹한다.

* `frame` \<ADockingFrame> frame
* `inx` \<Number> index
* `pos` \<Number> 도킹 되는 위치 / -1:insert before, 0:assign, 1:insert after
* `dockSize` \<Number> 도킹 사이즈 / pos가 0일경우 기존자리에 추가되므로 입력할 필요가 없음

```js
//frame은 ADockingFrame객체이다.
dockablePanel.dockFrame(frame, 1, 1);
```

<br/>

### init( context )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* `context` \<String> 컴포넌트 생성 및 초기화 정보

```js
var dockablePanel = new ADockablePanel();
dockablePanel.init();
```

<br/>

### setDelegator( delegator )

도킹 이벤트 수신할 객체를 지정한다.

* `delegator` \<Object> 도킹 이벤트 수신할 객체

<br/>

### setDockDirection( dir )

도킹패널의 분할방향을 설정한다.

* `dir` \<String> 컨테이너 분할 방향 "row" or "column"

```js
dockablePanel.setDockDirection('row');   //열
dockablePanel.setDockDirection('column');  //행
```

<br/>

### undockFrame( frame, x, y, w, h )

frame의 도킹을 해제한다.

* `frame` \<ADockingFrame> frame
* `x` \<Number> 도킹을 해제하고 나서 left값
* `y` \<Number> 도킹을 해제하고 나서 top값
* `w` \<Number> 도킹을 해제하고 나서 width값
* `h` \<String> 도킹을 해제하고 나서 height값

```js
//frame은 ADockingFrame객체이다.
//포지션값은 %와 px를 생략하고 입력해야한다.
dockablePanel.undockFrame(frame, 100, 200, 500, 500);
```

<br/>

## Events

### onDockFrame( acomp, frame, tabPanel )

frame 이 도킹될 때 delegator 에 전달되는 이벤트 함수

* `acomp` \<ADockablePanel> dockablePanel
* `frame` \<ADockingFrame> frame
* `tabPanel` \<APanel> 도킹된 panel

### onUndockFrame( acomp, frame, tabPanel )

frame 이 도킹 해제될 때 delegator 에 전달되는 이벤트 함수

* `acomp` \<ADockablePanel> dockablePanel
* `frame` \<ADockingFrame> frame
* `tabPanel` \<APanel> 도킹된 panel

<br/>

