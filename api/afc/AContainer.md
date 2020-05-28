# AContainer

최상위 추상 컨데이너, 비유하자면 [AView]() 는 그림이고 [AContainer]() 는 그림을 감싸고 있는 액자라고 할 수 있다. 자세한 내용은 [컴포넌트 시스템]() 설명 참조

<br>
<br>

## Class Variables

### AContainer.openContainers \<Object>
현재 응용프로그램에서 오픈되어져 있는 모든 컨테이너들을 가지고 있는 변수<br>
일반적으로 [AContainer.findOpenContainer]() 함수를 이용해 컨테이너를 얻어온다.

<br>
<br>

## Instance Variables

### element \<HTMLElement>
컨테이너를 구성하고 있는 HTMLElement 객체
```js
//순수 자바스크립트와 같이 다음 코드가 동작한다.
this.element.style.color = 'blue';
```
<br>

### $ele \<jQuery>
this.element 의 jQuery 객체
```js
//jQyery 와 같이 다음 코드가 동작한다.
this.$ele.css('color', 'blue');
```
<br>

### option \<Object>
컨테이너의 옵션 정보를 담고 있는 객체
```js
this.setOption({isModal:true, isCenter:true});
console.log(this.option.isModal);
------------------------------------------------------
true
```
<br>

### parent \<[AContainer](#AContainer)>
자신을 오픈한 부모 컨테이너 객체, AContainer 의 open 함수 호출 시 지정할 수 있다.

<br>

### view \<[AView](#AView)>
컨테이너가 감싸고 있는 뷰 객체, 뷰는 컴포넌트를 담아 화면을 표현하는 역할을 하며 컨테이너는 뷰를 감싸는 프레임 역할을 한다.

<br>
<br>

## Class Methods

### AContainer.findOpenContainer( cntrId )

컨테이너 아이디로 현재 오픈되어져 있는 컨테이너 객체를 얻어온다.

- `cntrId` \<String> 컨테이너 아이디 
- **Returns** \<[AContainer](#AContainer)>
```js
var cntr = AContainer.findOpenContainer('MenuWnd');
//cntr is instance of AContainer
//It might be AWindow, AFrameWnd, ADialog ...
cntr.show();
```

<br>
<br>

## Instance Methods

### appendSplit( splitSize, panelClass )

추가 분할 영역을 맨 뒤에 추가한다. AContainer 분할에 대한 자세한 설명은 [createSplit](#createSplit(-count,-sizeArr,-splitDir,-barSize,-panelClass-)) 함수 참조

- `splitSize` \<Number> 분할할 사이즈를 지정
  - 생략하거나 -1 지정시 자동으로 계산하여 영역 할당
  - 소수점 입력 시 비율만큼 할당 
- `panelClass` \<String> 추가할 APanel 클래스 이름, 생략시 기본값은 "APanel"
- **Returns** \<APanel> 새로 추가된 패널 객체

```js
function MainView*onSplitBtnClick(acomp, info, evt)
{
	var cntr = this.getContainer();

    //현재 MainView를 감싸고 있는 컨테이너 영역을 분할하여 
    //250 픽셀의 새로운 컨테이너(패널)를 맨 뒤에 추가한다.
    var newCntr = cntr.appendSplit(250);

	...
};
```
<br>

### close( result, data )

컨테이너를 닫는다.
- `result` \<Number> resultCallback 함수에 전달할 결과값
- `data` \<Object> resultCallback 함수에 전달할 데이터 객체

```js
//another lay file ...
var wnd = new AWindow();
wnd.open('Source/MyTestView.lay', ... );
wnd.setResultCallback(function(result, data)
{
    console.log(result);    //-1
    console.log(data);      //{ value: 'test' }
});


//Source/MyTestView.lay 파일
function MyTestView*onCloseBtnClick(acomp, info, evt)
{
    ...

    this.getContainer().close(-1, { value: 'test' });

};
```

<br>

### createSplit( count, sizeArr, splitDir, barSize, panelClass )

빈 컨테이너를 오픈한 후 컨테이너 내부 영역을 지정한 개수만큼 분할하여, 그 영역에 새로운 컨테이너([APanel]())를 생성한다. 생성된 컨테이너들 끼리의 영역은 스플릿바를 통해 리사이즈할 수 있다.<br>
※ 컨테이너 open 함수 호출 시 url 을 지정하지 않으면 빈 컨테이너가 생성된다. 차후 [setView]() 함수로 AView를 로드할 수 있다.

- `count` \<Number> 분할할 컨테이너 갯수 
- `sizeArr` \<Array> 분할할 각 컨테이너의 사이즈 배열
  - 배열의 각 요소는 숫자로만 지정 가능 `[ 100, 200, 10 ]`
  - -1 지정시 자동으로 남은 영역 할당 `[ 200, -1, 200 ]`
  - 소수점 입력 시 비율로 분할 `[ 0.2, 0.6, 0.2 ]`
  - sizeArr 을 지정하지 않으면(또는 null) 분할 영역 전체를 자동 균등 분할 
  - sizeArr 자체를 배열이 아닌 -1 로 지정하면 분할 영역을 조정할 수 없는 static 상태가 되고, 내부에 로드된 View의 사이즈 만큼 컨테이너의 사이즈가 자동으로 조정되는 auto 사이즈 상태가 된다.
- `splitDir` \<String> 컨테이너 분할 방향 (row : 가로방향, column : 세로방향)
- `barSize` \<Number> 사이즈 조정 BarSize, 생략시 기본값은 5px
- `panelClass` \<String> 새롭게 생성할 [APanel]() 클래스 이름
  - 생략시 기본값은 "APanel"
  - 생략하지 않고 명시적으로 '' 을 셋팅하면 컨테이너를 생성하지 않는다. 이 경우 차후 [setSplitPanel]() 함수를 호출하여 셋팅할 수 있다.
- **Returns** \<Array> 뷰가 로드되어 있지 않은 빈 컨테이너 배열

```js
function TestWindow*onCreate()
{
	super.onCreate();

    //세로 방향으로 3분할, 상단 20px, 하단 20px, 중단 -1 은 남은 영역을 차지함
    var hCntrs = this.createSplit(3, [20, -1, 20], 'column');
    hCntrs[0].setView('Source/TopView.lay');
    hCntrs[2].setView('Source/BottomView.lay');

    //분할된 컨테이너 중에서 중단(2번째) 컨테이너를 다시 가로 방향으로 3분할
    var vCntrs = hCntrs[1].createSplit(3, [200, -1, 200], 'row');

    //다음과 같이 분할됨
    -----------------
    -----------------
    |   |       |   |
    |   |       |   |
    |   |       |   |
    |   |       |   |
    -----------------
    -----------------
};
```
<br>

### destroySplit()

내부에 분할되어 생성되어 있는 모든 컨테이너를 삭제한다. 즉, createSplit 이전 상태로 돌린다.

<br>

### enable( isEnable )

컨테이너를 활성 또는 비활성화 시킨다. 비활성 상태가 되면 컨테이너 자체뿐 아니라 내부의 모든 컴포넌트도 동작하지 않는다.

- `isEnable` \<Boolean> 활성화 여부

<br>

### getClassName()

컨테이너 객체의 클래스 이름을 리턴한다.

- **Returns** \<String>

```js
var cntr1 = new ADialog();  //AContainer > AWindow > AFrameWnd > ADialog
var cntr2 = new APanel();   //AContainer > APanel

console.log(cntr1.getClassName());  //"ADialog"
console.log(cntr2.getClassName());  //"APanel"
```
<br>

### getContainerId()

컨테이너 객체 생성시 셋팅한 고유 아이디를 리턴한다. 컨테이너 아이디는 중복될 수 없으며 열려 있는 컨테이너를 찾거나 구별하는 경우에 사용되어진다.

- **Returns** \<String>

<br>

### getData()

[setData](#setData) 를 통해 셋팅한 데이터 값을 리턴한다.

- **Returns** \<All>

<br>

### getHeight()

컨테이너의 높이 값을 리턴한다.

- **Returns** \<Number>

<br>

### getParent()

AContainer 의 [open](#open) 함수 호출 시 지정한 부모 컨테이너 객체를 리턴한다.

- **Returns** \<[AContatiner](#AContatiner)>

<br>

### getPos()

컨테이너의 포지션 정보를 가진 오브젝트 객체를 리턴한다.

- **Returns** \<Obejct> `{ left: 100, top: 100 }`
```js
// if wnd is a instance of AWindow

var pos = wnd.getPos();

console.log(pos.left + ', ' + pos.top);
```

<br>

### getSplitCount()

분할된 영역의 개수를 리턴한다.

- **Returns** \<Number>

<br>

### getSplitPanel( inx )

분할된 영역 중에서 특정 영역의 컨테이너(`APanel`)를 얻어온다. 분할에 대한 자세한 설명은 
[createSplit](#createSplit(-count,-sizeArr,-splitDir,-barSize,-panelClass-)) 함수 참조

- `inx` \<Number> 분할된 영역의 index
- **Returns** \<[APanel](#APanel)>

```js
var panel = cntr.getSplitPanel(2);  //3번째 분할된 영역의 패널 리턴
```

<br>

### getView()

컨테이너가 감싸고 있는 `this.view` 객체를 리턴한다.<br>
뷰는 컴포넌트를 담아 화면을 표현하는 역할을 하며 컨테이너는 뷰를 감싸는 프레임 역할을 한다.

- **Returns** \<[AView](#AView)>

<br>

### getWidth()

컨테이너의 넓이 값을 리턴한다.

- **Returns** \<Number>

<br>

### hide()

컨테이너를 숨긴다.

<br>

### indexOfPanel( panel )

분할된 영역에서 패널의 인덱스 위치를 얻어온다.

- `panel` \<APanel> 인덱스를 얻고자 하는 패널 객체
- **Returns** \<Number>

```js
function TestView*onInitDone()
{
	super.onInitDone();

    var cntr = this.getContainer();
    var panels = cntr.createSplit(3, [100,-1,100]); //return APanel Array

    var inx = cntr.indexOfPanel(panels[1]);

    console.log(inx);   // inx is 1
};
```
<br>

### insertSplit( inx, splitSize, isAfter, panelClass )

특정 인덱스 위치에 분할 영역을 삽입한다. AContainer 분할에 대한 자세한 설명은 [createSplit](#createSplit(-count,-sizeArr,-splitDir,-barSize,-panelClass-)) 함수 참조

- `inx` \<Number> 분할해서 추가할 컨테이너 위치
- `splitSize` \<Number> 분할할 사이즈를 지정
  - 생략하거나 -1 지정시 자동으로 계산하여 영역 할당
  - 소수점 입력 시 비율만큼 할당 
- `isAfter` \<Boolean> inx 뒤로 추가할지 여부
- `panelClass` \<String> 추가할 APanel 클래스 이름, 생략시 기본값은 "APanel"
- **Returns** \<APanel> 새로 추가된 패널 객체

```js
function MainView*onSplitBtnClick(acomp, info, evt)
{
	var cntr = this.getContainer();

    //현재 MainView를 감싸고 있는 컨테이너 영역을 분할하여 
    //200 픽셀의 새로운 컨테이너(패널)를 두번째 패널 뒤에 추가한다.
    var newCntr = cntr.insertSplit(1, 200, true);

	...
};
```
<br>

### isOpen()

컨테이너가 오픈되어져 있는지를 반환한다. 즉, open 함수가 호출되었는지 여부

- **Returns** \<Boolean>

<br>

### isShow()

컨테이너가 화면에 보여지고 있는지를 반환한다.

- **Returns** \<Boolean>

<br>

### isValid()

컨테이너의 유효 여부를 반환한다. 즉, 아직 open 이 호출되지 않았거나 open 후에 close 가 호출 되었으면 isValid 는 false(`유효하지 않은 상황`) 이다. 

- **Returns** \<Boolean>

<br>

### open( url, parent, left, top, width, height, isPopup )

설정된 옵션에 따라 컨테이너 객체를 생성하고 전역 컨테이너(`body`) 공간에 추가하여, 화면에 컨테이너가 노출되도록 한다. 여기서 url 정보가 셋팅되어져 있으면 view 객체를 생성하고 자신의 공간으로 로드 한다. **즉, 컨테이너를 화면에 띄운다.**

- `url` \<String> 뷰 객체를 로드할 lay 파일의 경로
- `parent` \<AContainer> 자신의 부모가 될 컨테이너 지정, `null` 인 경우 기본적으로 [mainContainer](#mainContainer), [rootContainer](#rootContainer) 순서로 부모가 된다.
- `left` \<String> or \<Number> 컨테이너의 X 위치
- `top` \<String> or \<Number> 컨테이너의 Y 위치
- `width` \<String> or \<Number> 컨테이너의 넓이
- `height` \<String> or \<Number> 컨테이너의 높이
- `isPopup` \<Boolean> 기본적으로 부모 컨테이너 내부에 생성되지만 이 값이 true 이면 전역 공간에 팝업처럼 오픈된다.

```js
var page = new APage('myPage');
page.open('Source/Views/TestView.lay', null);

// AContainer 는 추상 클래스이므로 일반적으로 AContainer 를 상속 받은 
// 클래스에서 open 함수를 오버라이드 하여 자신만의 파라미터를 구성하고 함수
// 내부에서 AContainer 의 open 함수를 호출하는 방식으로 사용된다.

//다음은 APage 클래스의 open 함수이다.
APage.prototype.open = function(viewUrl, parent)
{
	AContainer.prototype.open.call(this, viewUrl, parent, 0, 0, '100%', '100%');
};
```
<br>

### prependSplit( splitSize, panelClass )

추가 분할 영역을 맨 앞에 추가한다. AContainer 분할에 대한 자세한 설명은 [createSplit](#createSplit(-count,-sizeArr,-splitDir,-barSize,-panelClass-)) 함수 참조

- `splitSize` \<Number> 분할할 사이즈를 지정
  - 생략하거나 -1 지정시 자동으로 계산하여 영역 할당
  - 소수점 입력 시 비율만큼 할당 
- `panelClass` \<String> 추가할 APanel 클래스 이름, 생략시 기본값은 "APanel"
- **Returns** \<APanel> 새로 추가된 패널 객체

```js
function MainView*onSplitBtnClick(acomp, info, evt)
{
	var cntr = this.getContainer();

    //현재 MainView를 감싸고 있는 컨테이너 영역을 분할하여 
    //250 픽셀의 새로운 컨테이너(패널)를 맨 앞에 추가한다.
    var newCntr = cntr.prependSplit(250);

	...
};
```
<br>

### removeSplit( inx )

특정 인덱스에 위한 분할 컨테이너를 삭제한다.

- `inx` \<Number> 삭제하고자 하는 컨테이너의 인덱스

<br/>

### setActiveRecursive( isRecursive )

컨테이너의 `view` 를 시작으로 자신이 받은 active / deactive 이벤트를 자식 뷰들에게도 재귀적으로 호출해 줄지 여부를 지정한다. 성능상의 이유로 기본값은 `false` 이지만 성능에 큰 영향을 주지 않고 구조적으로 꼭 필요할 경우 셋팅해 준다. 이 값은  컨테이너 단위로 작동된다.

- `isRecursive` \<Boolean> 자식 뷰들에게 active / deactive 이벤트를 전달할 지 여부

```js
var wnd = new AWindow();

wnd.setActiveRecursive(true);
wnd.open(...);
...
```
<br>

----
여기부터
----

### setContainerId( containerId )

컨테이너 고유 아이디를 세팅한다.

* **Parameters**: 
	* **`containerId`** {String} 컨테이너 고유 아이디

* **Usage**: 
```js
container.setContainerId('contId');
```

<br/>

### setData( data )

데이터를 지정한다.

* **Parameters**: 
	* **`data`** {String} 데이터

* **Usage**: 
```js
var data = 'data';
container.setData(data);
```

<br/>

### setHeight( height )

컨테이너의 높이 값을 설정한다.

* **Parameters**: 
	* **`height`** {String} 높이값

* **Usage**: 
```js
container.setHeight(100);
container.setHeight('100px');
container.setHeight('100%');
```

<br/>

### setParent( newParent, styleObj )

부모를 설정한다. 부모객체는 반드시 AContainer여야 한다.

* **Parameters**: 
	* **`newParent`** {String} 새로 설정 할 부모객체
	* **`styleObj`** {String} 스타일 오브젝트

* **Usage**: 
```js
container.setParent(theApp.rootContainer, {left:0,top:0});
```

<br/>

### setPos( pos )

포지션을 지정합니다.

* **Parameters**: 
	* **`pos`** {String} ex) {left:10, top:20}

* **Usage**: 
```js
// %입력불가, px는 생략해서 입력해야한다.
container.setPos({left:10, top:20});
```

<br/>

### setSplitPanel( inx, acont )

분할 컨테이너를 설정한다. 현재 컨테이너가 분할 컨테이너일 경우 오픈 대신 호출한다.

* **Parameters**: 
	* **`inx`** {String} 인덱스
	* **`acont`** {String} 컨테이너

* **Usage**: 
```js
var panel = new APanel();
.
.
.
container.setSplitPanel(1, panel);
```

<br/>


### setView( view, isFull )

컨테이너 내부에 생성되는 뷰를 세팅한다.

* **Parameters**: 
	* **`view`** {String} view의 url
	* **`isFull`** {String} 뷰를 가득차게 할지 여부

<br/>

### setWidth( width )

컨테이너의 너비값을 설정한다.

* **Parameters**: 
	* **`width`** {String} 너비값

* **Usage**: 
```js
container.setWidth(100);
container.setWidth('100px');
container.setWidth('10%');
```

<br/>

### show()

컨테이너를 보이게 한다.

* **Usage**: 
```js
container.show();
```

<br/>

### toString()

컨테이너의 HTML 엘리먼트를 문자열로 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = container.toString();
```

<br/>

### setOption()

* **Parameters**: 

* **Usage**: 
```js

```

<br>
<br>

## Events

### onActive( reload )

onWillActive 이후에 호출되며 컨테이너 활성화가 시작되면 매번 호출된다.

- `reload` {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

<br>

### onActiveDone( reload )

onActive 이후 컨테이너 활성화 과정이 모두 종료되면 매번 호출된다. show 의 에니메이션이나 특정 이펙트가 완전히 종료된 후 호출

- `reload` {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

<br>

### onAppPause()

Application 이 Background 로 이동하는 경우 호출된다.

<br>

### onAppResume()

Application 이 Foreground 로 이동하는 경우

<br>

### onBackKey()

디바이스(android) 의 Back Key 가 눌려졌을 때 호출된다.

<br>

### onClose()

컨테이너가 종료될때 호출된다.

<br>

### onCreate()

컨테이너의 리소스 로드가 완료되면 호출된다. 최초 한번만 호출된다. 리소스는 로드됐지만 컨테이너가 보여지진 않는다.

<br>

### onDeactive()

onWillDeactive 이후에 호출되며 컨테이너 비활성화가 시작되면 매번 호출된다.

<br>

### onDeactiveDone()

onDeactive 이후 컨테이너 비활성화 과정이 모두 종료되면 매번 호출된다. hide 의 에니메이션이나 특정 이펙트가 완전히 종료된 후 호출

<br>

### onOrientationChange( info )

디바이스의 방향이 변경될 때 호출된다.

- `info` {String} portrait or landscape

<br>

### onReady()

컨테이너의 리소스 로드가 완료되면 최초 한번만 호출된다. 리소스는 로드됐지만 컨테이너가 보여지진 않는다.

<br>

### onResize()

Native WebView 의 사이즈가 변경될 때 호출된다. 디바이스의 방향이 변경될 경우 onOrientationChange 와 함께 호출된다.

<br>

### onSplitChanged( splitFrame )

분할컨테이너가 변경될때 불려지는 함수이다. 분할컨테이너에 리사이즈 이벤트를 호출한다.

- `splitFrame` {AContainer} 분할 컨테이너

<br>


### onWillActive( isFirst )

onReady 이후에 호출되며 컨테이너 활성화가 시작되기 바로 전에 매번 호출된다.

- `isFirst` {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

<br>

### onWillDeactive()

컨테이너 비활성화가 시작되기 바로 전에 매번 호출된다.

<br>

