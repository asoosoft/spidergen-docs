# ScrollManager
> **Extends**: 

자체적인 스크롤기능을 구현해주는 클래스

<br/>

## Methods

### enableScroll( enable )

스크롤을 가능/불가능하게 만든다. 기본적으로 true 이다.

* **Parameters**: 
	* **`enable`** {Boolean} .

<br/>

### setDisableManager( manager )

자신이 스크롤될 때 움직이지 말아야할 ScrollManager 를 지정한다. 두개 이상의 스크롤 매니저가 중첩됐을 경우, ex) 피봇그리드

* **Parameters**: 
	* **`manager`** {ScrollManager} .

<br/>

### setOption( option )

스크롤 이동에 대한 감도를 셋팅한다. <br/>startDelay: 10, //최초 자동 스크롤 시작시 속도값. (값이 커질수록 느려진다.) <br/>endDelay: 20, //스크롤을 종료시킬 속도값. (값이 커질수록 천천히 멈춘다.)<br/><br/>scrollAmount: 50, //스크롤 이동 수치. (값이 작아질 수록 미세하기 움직이며 이동량이 작아진다.) <br/>speedRatio: 0.02 //스크롤 속도를 감속시킬 비율. (비율이 커질수록 최초 스크롤속도가 빨리 감속된다.)

* **Parameters**: 
	* **`option`** {Object} .

<br/>
<br/>
