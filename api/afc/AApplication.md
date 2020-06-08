# AApplication

응용프로그램을 관리하는 클래스, AApplication 의 onReady 함수가 프로그램의 시작 지점이 된다.

<br>
<br>


## Class Variables

<br>
<br>


## Instance Variables

### rootContainer \<[AContainer](./AContainer.html#acontainer)>
응용프로그램이 시작되는 최상위 컨테이너, 화면을 표현하지는 않는다. mainContainer 의 부모 컨테이너 역할만 한다.

<br>

### mainContainer \<[AContainer](./AContainer.html#acontainer)>
rootContainer 에 추가되는 유일한 컨테이너, mainContainer 로부터 화면 표현이 시작된다.
```js
function MyTestApp*onReady()
{
	super.onReady();

	this.setMainContainer(new APage('main'));       //this.mainContainer 변수를 셋팅한다.
	this.mainContainer.open('Source/MainView.lay'); //여기서 rootContainer 에 추가된다.

	...
};
```
<br>

### mdiManager \<[MDIManager](../library/MDIManager.html#mdimanager)>

동적으로 생성되는 MDIManager 객체를 갖고 있는 변수이다.
<br>

### webHistoryMgr \<[WebHistoryManager](../library/WebHistoryManager.html#webhistorymanager)>
동적으로 생성되는 WebHistoryManager 객체를 갖고 있는 변수이다.

<br>
<br>

## Class Methods

<br>
<br>

## Instance Methods

### addThemeEventListener( callback )

테마가 변경될 때 이벤트를 수신받을 함수를 등록한다. 함수에 전달받는 이벤트 객체의 detail 항목에 이전, 현재 테마명 데이터가 있다. e.detail {preTheme: preTheme, curTheme: curTheme}

* `callback` \<Function> 테마변경 수신 함수

```js
//테마 변경에 대한 내용을 수신하기 위해 등록함수 호출
theApp.addThemeEventListener(function(e)
{
    console.log(e.detail);
    //{preTheme: preTheme, curTheme: curTheme}
});
```

### changeTheme( theme )

SpiderGen 툴의 Project View 창에서 Template/Theme 에 추가한(Add Theme) 테마명 목록 중 적용하고 싶은 테마로 변경한다.

* `theme` \<String> 테마명

```js
if(theApp.getTheme() != 'black') theApp.changeTheme('black');
```

<br/>

### closeActiveDocTmplFile( callback, isForce, isSave )

현재 활성화된 컨테이너의 Document 파일을 close한다. 문서가 수정되어 있으면 저장할 지 여부를 묻고 문서를 닫는다. MDI 시스템에서 문서가 닫혀야 하는 경우 이 함수를 호출한다. *(MDI 에서만 사용)*

- `callback` \<Function> 문서가 닫힌 후 호출되는 콜백함수
    - function( result ) --> result \<Number> 0: 예, 1: 아니오, 2: 취소 
- `isForce` \<Boolean> 이 값이 참이면 저장 여부를 묻지 않고 무조건 문서를 닫는다.
- `isSave` \<Boolean> isForce 가 참인 경우만 동작하며 이 값이 참이면 무조건 저장한 후 문서를 닫는다.
```js
function MyTestApp*onCloseBtnClick()
{

	theApp.closeActiveDocTmplFile( function(result) {
        console.log(result);    //0 or 1 or 2
    });

	...
};
```
<br>

### getActiveContainer()

현재 활성화된 컨테이너를 리턴한다. *(MDI 에서만 사용)*

- **Returns** \<[AContainer](./AContainer.html#acontainer)>

<br>

### getActiveDocument()

현재 활성화된 컨테이너의 View 의 Document를 리턴한다. *(MDI 에서만 사용)*

- **Returns** \<[ADocument](./ADocument.html#adocument)>

<br>

### getActiveView()

현재 활성화된 컨테이너의 View 객체를 리턴한다. *(MDI 에서만 사용)*

- **Returns** \<[AView](./AView.html#aview)>

<br>

### getCurrentPath()

현재 응용프로그램이 실행된 경로를 얻어온다. 주로 index.html 의 위치가 된다.

- **Returns** \<String>

<br>

### getDataPath()

현재 응용프로그램이 데이터를 저장할 수 있는 곳의 경로를 얻어온다.

- **Returns** \<String>

<br>

### getMainContainer()

this.[mainContainer](#maincontainer-acontaineracontainerhtmlacontainer) 객체를 얻어온다.

- **Returns** \<[AContainer](./AContainer.html#acontainer)>

<br>

### getOrientation()

모바일 기기의 현재 화면 방향을 얻어온다.

- **Returns** \<String> "portrait" or "landscape"

<br>

### getProcessPath()

Electron 등과 같은 Hybrid 응용프로그램인 경우 브라우저 실행파일의 경로를 얻어온다.

- **Returns** \<String>

<br>

### getRootContainer()
this.[rootContainer](#rootcontainer-acontaineracontainerhtmlacontainer) 객체를 얻어온다.

- **Returns** \<[AContainer](./AContainer.html#acontainer)>

<br>

### getTheme()

현재 활성화된 테마 이름을 가져온다.

* **Returns** \<String> 현재 활성화된 테마명

<br/>

### openDocTmplFile( filePath, noLoad, bSilent )

해당 경로의 파일을 mdi 시스템을 통해 오픈한다. *(MDI 에서만 사용)*

- `filePath` \<String> open 하고자 하는 파일의 경로
- `noLoad` \<Boolean> mdi 탭바에 정보는 추가하되 탭이 최초로 활성화 될 때 파일을 로드할 경우 사용, 동시에 많은 탭 정보를 추가할 경우 성능 향상을 위해 사용
- `bSilent` \<Boolean> 오류 발생 시 메시지 출력 여부 (파일이 존재하지 않는 경우 등)
-  **Returns** \<Boolean> 파일 open 성공 여부

<br>

### removeThemeEventListener( callback )

[addThemeEventListener](#addthemeeventlistener-callback-) 함수를 호출하여 등록한 테마 변경 이벤트 수신 함수를 제거한다. 이 함수를 호출하면 더 이상 이벤트를 전달 받지 않는다.

* `callback` \<Function> 테마변경 수신 등록 함수

```js
var themeChange = function(e)
{
    console.log(e.detail);
    //{preTheme: preTheme, curTheme: curTheme}
};
//테마 변경에 대한 내용을 수신하기 위해 등록함수 호출
theApp.addThemeEventListener(themeChange);

//더 이상 테마변경 내용을 수신하지 않을 경우 제거함수 호출
theApp.removeThemeEventListener(themeChange);
```

### saveActiveDocTmplFile()

현재 활성화된 document의 파일을 저장한다. *(MDI 에서만 사용)*

<br/>

### setMainContainer( cntr )

this.[mainContainer](#maincontainer-acontaineracontainerhtmlacontainer) 객체를 셋팅한다.

- `cntr` \<[AContainer](./AContainer.html#acontainer)>
```js
function MyTestApp*onReady()
{
	super.onReady();

	this.setMainContainer(new APage('main'));            //this.mainContainer 변수를 셋팅한다.
	this.getMainContainer().open('Source/MainView.lay'); //여기서 rootContainer 에 추가된다.

	...
};
```

<br>
<br>

## Global Functions
### AfcMessageBox( title, message, type, callback, modaless )
AFC 프레임웍의 기본 메시지 박스를 띄워준다.

- `title` \<String> 메시지 박스의 타이틀 텍스트
- `message` \<String> 메시지 본문 텍스트
- `type` \<Number> 다이얼로그 창의 버튼 유형
  - AMessageBox.EMPTY = -1;
  - AMessageBox.OK = 0;
  - AMessageBox.OK_CANCEL = 1;
  - AMessageBox.YES_NO = 2;
  - AMessageBox.YES_NO_CANCEL = 3;
- `callback` \<Function> 종료 콜백 함수
  - function( result ) { }
  - `result` \<Number> 선택한 버튼 인덱스
  - 인덱스는 버튼 나열순서, `0:예, 1:아니오 또는 취소, 2:취소`
- `modaless` \<Boolean> 메시지 박스를 모달리스로 띄울지, 일반적으로 생략
```js
function MyTestApp*onBtnClick(comp, info, evt)
{
    AfcMessageBox('알림', '파일이 변경되었습니다. 저장하시겠습니까?', AMessageBox.YES_NO, function(result) {
        if(result==0)   //예, 버튼 클릭
        {

        }
    });
};
```
<br>
<br>

## Events

### onClose()

응용프로그램이 종료될 때 발생되는 이벤트이다.

- **Returns** \<Boolean> 명시적으로 false 를 리턴하면 종료되지 않는다.
```js
function MyTestApp*onClose()
{
    if(this.getActiveDocument().isModified())
    {
        return false;
    }
};
```
<br>

### onError( message, url, lineNumber, colNumber, error )
응용프로그램 동작 도중 스크립트 오류가 발생하면 호출된다.
- `message` \<String> 오류 메시지
- `url` \<String> 오류가 난 파일의 url
- `lineNumber` \<Number> 오류의 row 위치
- `colNumber` \<Number> 오류의 column 위치
- `error` \<Object> 에러 정보를 담고 있는 객체, { stack, ... }
  - stack \<String> callstack 정보
<br>

### onReady()

기본적인 리소스와 라이브러리가 로드되어 응용프로그램에 mainContainer 를 open 할 수 있게 되면 호출된다.
```js
function MyTestApp*onReady()
{
	super.onReady();

	this.setMainContainer(new APage('main'));            //this.mainContainer 변수를 셋팅한다.
	this.getMainContainer().open('Source/MainView.lay'); //여기서 rootContainer 에 추가된다.

	...
};
```
<br/>

