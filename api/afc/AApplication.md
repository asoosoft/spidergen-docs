# AApplication

응용프로그램을 관리하는 클래스, AApplication 의 onReady 함수가 프로그램의 시작 지점이 된다.

<br>
<br>


## Class Variables

<br>
<br>


## Instance Variables

### mdiManager \<[MDIManager](#MDIManager)>

동적으로 생성되는 MDIManager 객체를 갖고 있는 변수이다.
<br>

### webHistoryMgr \<[WebHistoryManager](#WebHistoryManager)>

<br>
<br>

## Class Methods

<br>
<br>

## Instance Methods

### addKeyEventListener( type, listener )

* `type` \<String> type
* `listener` \<String> listener

<br/>

### closeActiveDocTmplFile( callback, isForce, isSave )

현재 활성화된 Document의 파일을 close한다.

* `callback` {Function} 콜백함수
* `isForce` {String} isForce
* `isSave` {String} isSave

<br/>

### getActiveContainer()

현재 활성화된 container를 리턴한다.

- **Returns** \<AContainer>

<br/>

### getActiveDocument()

현재 활성화된 Document를 리턴한다.

- **Returns** \<ADocument>

<br/>

### getActiveView()

현재 활성화된 View를 리턴한다.

- **Returns** \<AView>

<br/>

### getCurrentPath()

현재 어플리케이션의  URL Path를 리턴한다.

- **Returns** \<String>

<br/>

### getDataPath()

- **Returns** \<String>

<br/>


### getMainContainer()

루트 컨테이너 밑으로, 화면을 표현하는 시작 컨테이너를 리턴한다.

- **Returns** \<Object>

<br/>

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

