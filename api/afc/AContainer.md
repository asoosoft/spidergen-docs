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

### parent \<[AContainer]()>
자신을 오픈한 부모 컨테이너 객체, AContainer 의 open 함수 호출 시 지정할 수 있다.

<br>

### view \<[AView]()>
컨테이너가 감싸고 있는 뷰 객체, 뷰는 다른 컴포넌트를 자식으로 담아 화면을 표현하는 역할을하며 컨테이너는 뷰를 감싸는 프레임 역할을 한다.

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

추가 분할 영역을 뒤에 추가한다. AContainer 분할에 대한 자세한 설명은 [createSplit]() 함수 참조

- `splitSize` \<Number> 분할 크기를 고정값으로 지정
  - 생략하거나 -1 지정시 자동으로 계산하여 영역 할당
  - 소수점 입력 시 비율만큼 할당 
- `panelClass` \<String> 추가할 APanel 클래스 이름, 생략시 기본값은 "APanel"
- **Returns** \<APanel> 새로 추가된 패널 객체

```js
function MainView*onSplitBtnClick(acomp, info, evt)
{
	var cntr = this.getContainer();

    //현재 MainView를 감싸고 있는 컨테이너 영역을 분할하여 
    //250 픽셀의 새로운 컨테이너(패널)를 추가한다.
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

----
여기부터
----

### destroySplit()

내부에 Split되어 있는 모든 컨테이너를 삭제한다.

* **Usage**: 
```js
container.destroySplit();
```

<br>

### enable( isEnable )

컨테이너의 활성, 비활성 상태를 세팅한다.

* **Parameters**: 
	* **`isEnable`** {String} 활성화 여부

* **Usage**: 
```js
container.enable(false);
```

<br>


### getClassName()

클래스 이름을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = container.getClassName();
```
<br>

### getContainerId()

컨테이너 고유 아이디를 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = container.getContainerId();
```

<br/>

### getData()

지정된 데이터를 리턴한다.

* **Returns**: All

* **Usage**: 
```js
var result = container.getData();
```

<br/>


### getHeight()

컨테이너의 높이 값을 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
container.getHeight();
```

<br/>


### getParent()

부모 컨테이너를 반환한다.

* **Returns**: AContatiner

* **Usage**: 
```js
var result = container.getParent();
```

<br/>

### getPos()

포지션 값을 리턴한다.

* **Returns**: obejct

* **Usage**: 
```js
var result = container.getPos();
```

<br/>

### getSplit( inx )

해당하는 인덱스의 스플리트뷰를 반환한다.

* **Returns**: ASplitView

* **Parameters**: 
	* **`inx`** {String} 인덱스

* **Usage**: 
```js
var result = container.getSplit();
```

<br/>

### getSplitCount()

스플리트뷰의 갯수를 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var length = container.getSplitCount();
```

<br/>

### getSplitPanel( inx )

해당 인덱스의 분할컨테이너를 리턴한다.

* **Returns**: AContainer

* **Parameters**: 
	* **`inx`** {String} 인덱스

* **Usage**: 
```js
var result = container.getSplitPanel(2);
```

<br/>

### getView()

컨테이너에 루트뷰를 리턴한다.

* **Returns**: AView

* **Usage**: 
```js
var result = container.getView();
```

<br/>

### getWidth()

컨테이너의 넓이 값을 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
container.getWidth();
```

<br/>

### hide()

컨테이너를 숨긴다.

* **Usage**: 
```js
container.hide();
```

<br/>

### indexOfPanel( panel )

패널의 인덱스를 반환한다.

* **Returns**: Number

* **Parameters**: 
	* **`panel`** {String} 패널객체

* **Usage**: 
```js
var panel = new APanel();
.
.
var index = container.indexOfPanel(panel);
```

<br/>

### init( context )

컨테이너를 생성하고 초기화 할 때 호출한다. 내부적으론 view 가 그 기능을 대신하므로 this.view 의 init 함수를 호출한다.

* **Parameters**: 
	* **`context`** {String} 컨테이너 생성 및 초기화 정보

* **Usage**: 
```js
//init함수를 직접호출하지 않는다. open함수에서 내부적으로 호출해준다.
```

<br/>

### insertSplit( inx, splitSize, isAfter, cntrClass )

새로운 분할 컨테이너를 삽입한다.

* **Returns**: APanel

* **Parameters**: 
	* **`inx`** {String} 포지션
	* **`splitSize`** {Number} 분할 크기
	* **`isAfter`** {Number} 앞인지 뒤인지 여부 // -1:insert before, 0:assign, 1:insert after
	* **`cntrClass`** {String} 컨테이너 클래스

* **Usage**: 
```js
var resultContainer = container.insertSplit(1, 250. 1);
```

<br/>

### isOpen()

컨테이너의 오픈여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = container.isOpen();
```

<br/>

### isShow()

컨테이너의 표시여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = container.isShow();
```

<br/>

### isValid()

컨테이너가 유효한지 여부를 리턴한다. 생성이 아직 안 됐거나 소멸된 경우 false 를 리턴한다.

* **Returns**: Boolean

* **Usage**: 
```js
var result = container.isValid();
```

<br/>

### open( url, parent, left, top, width, height, isPopup )

컨테이너를 오픈한다.init이 호출되지 않은 경우는 내부적으로 init을 호출해준다.

* **Returns**: boolean

* **Parameters**: 
	* **`url`** {String} 컨테이너뷰의 url
	* **`parent`** {AContainer or AComponent} 지정되어 있지 않으면 rootContainer가 지정되지만 지정된 parent가 AContainer가 아닐경우 오픈하지 않음
	* **`left`** {String} 위치값 left
	* **`top`** {String} 위치값 top
	* **`width`** {String} 너비
	* **`height`** {String} 높이
	* **`isPopup`** {String} 팝업 여부

* **Usage**: 
```js
var container = new AContainer();
container.open('view/main.lay',null, 0,0,'100%','100%');
```

<br/>

### prependSplit( splitSize, cntrClass )

새로운 분할 컨테이너를 앞쪽에 추가한다.

* **Parameters**: 
	* **`splitSize`** {String} 분할크기
	* **`cntrClass`** {String} 컨테이너 클래스

* **Usage**: 
```js
var resultContainer = container.prependSplit(250);
```

<br/>

### removeSplit( inx )

분할 컨테이너를 삭제한다.

* **Parameters**: 
	* **`inx`** {String} 인덱스

* **Usage**: 
```js
container.removeSplit(1);
```

<br/>

### setActiveRecursive( isRecursive )

active 이벤트를 자식들에게 재귀적으로 호출해 줄지 여부를 지정한다. isRecursive가 false 이고 원하는 자식에게만 전달하고 싶을 경우에는 수동으로 뷰의 onActive 함수내에서 callSubActiveEvent 함수를 호출해 주면 된다.

* **Parameters**: 
	* **`isRecursive`** {Boolean} 호출여부

* **Usage**: 
```js
container.setActiveRecursive(false);
```

<br/>

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

* **Parameters**: 
	* **`reload`** {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

### onActiveDone( reload )

onActive 이후 컨테이너 활성화 과정이 모두 종료되면 매번 호출된다. show 의 에니메이션이나 특정 이펙트가 완전히 종료된 후 호출

* **Parameters**: 
	* **`reload`** {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

### onAppPause()

Application 이 Background 로 이동하는 경우 호출된다.

### onAppResume()

Application 이 Foreground 로 이동하는 경우

### onBackKey()

디바이스(android) 의 Back Key 가 눌려졌을 때 호출된다.


### onClose()

컨테이너가 종료될때 호출된다.

<br/>

### onCreate()

컨테이너의 리소스 로드가 완료되면 호출된다. 최초 한번만 호출된다. 리소스는 로드됐지만 컨테이너가 보여지진 않는다.

<br/>


### onDeactive()

onWillDeactive 이후에 호출되며 컨테이너 비활성화가 시작되면 매번 호출된다.

### onDeactiveDone()

onDeactive 이후 컨테이너 비활성화 과정이 모두 종료되면 매번 호출된다. hide 의 에니메이션이나 특정 이펙트가 완전히 종료된 후 호출

### onOrientationChange( info )

디바이스의 방향이 변경될 때 호출된다.

* **Parameters**: 
	* **`info`** {String} portrait or landscape

### onReady()

컨테이너의 리소스 로드가 완료되면 최초 한번만 호출된다. 리소스는 로드됐지만 컨테이너가 보여지진 않는다.

### onResize()

Native WebView 의 사이즈가 변경될 때 호출된다. 디바이스의 방향이 변경될 경우 onOrientationChange 와 함께 호출된다.

### onSplitChanged( splitFrame )

분할컨테이너가 변경될때 불려지는 함수이다. 분할컨테이너에 리사이즈 이벤트를 호출한다.

* **Parameters**: 
	* **`splitFrame`** {AContainer} 분할 컨테이너

<br/>


### onWillActive( reload )

onReady 이후에 호출되며 컨테이너 활성화가 시작되기 바로 전에 매번 호출된다.

* **Parameters**: 
	* **`reload`** {Boolean} 최초 리소스 로드가 완료된 경우만 reload 가 true 이다.

### onWillDeactive()

컨테이너 비활성화가 시작되기 바로 전에 매번 호출된다.

<br/>

