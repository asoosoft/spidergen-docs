# AApplication

응용프로그램을 관리하는 클래스, AApplication 의 onReady 함수가 프로그램의 시작 지점이 된다.

<br>
<br>


## Class Variables

<br>
<br>


## Instance Variables

### rootContainer \<[AContainer](#AContainer)>
응용프로그램이 시작되는 최상위 컨테이너, 화면을 표현하지는 않는다. mainContainer 의 부모 컨테이너 역할만 한다.

### mainContainer \<[AContainer](#AContainer)>
rootContainer 에 추가되는 유일한 컨테이너, mainContainer 로부터 화면 표현이 시작된다.


### mdiManager \<[MDIManager](#MDIManager)>

동적으로 생성되는 MDIManager 객체를 갖고 있는 변수이다.
<br>

### webHistoryMgr \<[WebHistoryManager](#WebHistoryManager)>
동적으로 생성되는 WebHistoryManager 객체를 갖고 있는 변수이다.

<br>
<br>

## Class Methods

<br>
<br>

## Instance Methods

### closeActiveDocTmplFile( callback, isForce, isSave )

현재 활성화된 컨테이너의 Document 의 파일을 close한다. (MDI 시스템에서만 사용)

- `callback` \<Function> 콜백함수
- `isForce` \<Boolean> 
- `isSave` \<Boolean> 

<br>

### getActiveContainer()

현재 활성화된 컨테이너를 리턴한다. (MDI 시스템에서만 사용)

- **Returns** \<[AContainer](#AContainer)>

<br>

### getActiveDocument()

현재 활성화된 컨테이너의 View 의 Document를 리턴한다. (MDI 시스템에서만 사용)

- **Returns** \<[ADocument](#ADocument)>

<br>

### getActiveView()

현재 활성화된 컨테이너의 View 객체를 리턴한다. (MDI 시스템에서만 사용)

- **Returns** \<[AView](#AView)>

<br>

### getCurrentPath()

현재 응용프로그램이 실행된 경로를 얻어온다.

- **Returns** \<String>

<br>

### getDataPath()

현재 응용프로그램이 데이터를 저장할 수 있는 곳의 경로를 얻어온다.

- **Returns** \<String>

<br>

### getMainContainer()

this.[mainContainer](#mainContainer) 객체를 얻어온다.

- **Returns** \<[AContainer]()>

<br>


----
여기부터
----


### getOrientation()

현재 화면 방향을 리턴한다.

- **Returns** \<String>
<br/>


### getProcessPath()

- **Returns** \<String>

<br>

### getRootContainer()

<br>

### openDocTmplFile( filePath )

해당 경로의 파일을 오픈한다.

- `filePath` {String} filePath

<br/>

### removeKeyEventListener( type, listener )

등록된 KeyEventListener를 제거한다.

- `type` {String} type
- `listener` {String} listener

<br/>

### saveActiveDocTmplFile()

현재 활성화된 document의 파일을 저장한다.

<br/>

### setMainContainer( container )

루트 컨테이너 밑으로, 화면을 표현하는 시작 컨테이너를 설정한다.

- `container` {String} container

<br/>

----
*아래함수 작성하고 알파벳 순서 위치로 이동, 노출하지 않아도 되는 함수는 제거*
### loadThemeInfo()
### changeTheme()
### getTheme()
### setTheme()
### reportThemeEvent()
### addThemeEventListener()
### removeThemeEventListener()
----


<br>
<br>

## Global Functions
### AfcMessageBox( title, message, type, callback, modaless )

<br>
<br>

## Events

### onClose()

어플리케이션이 Close될때 사용되는 함수이다. 네이티브가 종료될때 호출한다.

- **Returns**: boolean

<br/>

### onError()

<br>

### onReady()

디바이스가 Ready상태일떄 호출된다.

<br/>

