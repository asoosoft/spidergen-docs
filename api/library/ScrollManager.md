# ScrollManager

자체적인 스크롤기능을 구현해주는 클래스

<br/>

## Class Variables

<br/>

## Instance Variables

<br/>

## Class Methods

<br/>

## Instance Methods

### addDisableManager( manager )

자신이 스크롤 될때 움직이지 말아야할 스크롤 매니저를 지정한다.

- `manager` \<ScrollManager> 스크롤 매니저 객체

<br/>

### enableScroll( enable )

스크롤을 가능/불가능하게 만든다. 기본적으로 true 이다.

- `enable` \<Boolean> 스크롤 가능 여부

<br/>

### initScroll( pos )

스크롤에 사용되는 값들을 초기화한다.

- `pos` \<Number> or <String> 위치값
```js
var thisObj = this;
this.bindEvent(AEvent.ACTION_DOWN, function(e)
{
	isDown = true;
	
	//이 부분을 추가하면 다른 스크롤이 발생하지 않음.
	//e.preventDefault();
	
	e.stopPropagation();
	thisObj.scrlManager.initScroll(e.changedTouches[0].clientX);
});
```

<br/>

### removeAllDisableManager()

[addDisableManager](#-addDisableManager(-manager-))에서 지정된 모든 스크롤 매니저를 해제한다.

<br/>

### removeDisableManager( manager )

[addDisableManager](#-addDisableManager(-manager-))에서 지정된 스크롤 매니저 중 매개변수 manager에 해당되는 매니저를 제외한다.

- `manager` \<ScrollManager> 스크롤 매니저 객체

<br/>

### scrollCheck( pos, scrollFunc )

마우스 터치가 끝날때 발생된다. 최종 이동거리를 계산해주고 터치가 종료되도 움직이는 속도에 따라 스크롤이 일정시간동안 발생한다.

- `pos` \<Number> or <String> 위치값
- `updateFunc` \<Function> 콜백함수

<br/>

### setOption( option )

스크롤 이동에 대한 감도를 셋팅한다. 

- `option` \<Object> 옵션 정보
	- startDelay : 최초 자동 스크롤 시작시 속도값 (값이 커질수록 느려진다. 기본값 10)
	- endDelay: 스크롤을 종료시킬 속도값. (값이 커질수록 천천히 멈춘다. 기본값 20)
	- scrollAmount: 스크롤 이동 수치. (값이 작아질 수록 미세하기 움직이며 이동량이 작아진다. 기본값 50) 
	- velocityRatio: 스크롤 속도를 감속시킬 비율. (비율이 커질수록 최초 스크롤속도가 빨리 감속된다. 기본값 0.02)


<br/>

### stopScrollTimer()

스크롤 타이머를 중지한다.

<br/>

### setStopCallback( callback )

스크롤 애니메이션이 중지됐을 때 호출할 함수를 지정한다.

- `callback` \<Function> 콜백함수

<br/>

### updateScroll( pos, updateFunc )

스크롤 위치 값을 받아서 스크롤될 위치를 계산해준다.

- `pos` \<Number> or <String> 위치값
- `updateFunc` \<Function> 콜백함수

```js
//스크롤 매니저를 사용하는 컴포넌트에서 이벤트를 등록해
//스크롤 매니저를 통해 계산된 위치값을 전달받는 예시
var thisObj = this;
this.bindEvent(AEvent.ACTION_MOVE, function(e)
{
	e.stopPropagation();
	//스크롤 매니저에 현재 위치값을 파라미터로 보낸후에
	//이동해야될 계산된 값을 콜백함수로 리턴받아 스크롤을 이동한다.
	thisObj.scrlManager.updateScroll(e.changedTouches[0].clientX, function(move)
	{
		thisObj.element.scrollLeft += move;
	});
});
```

<br/>
