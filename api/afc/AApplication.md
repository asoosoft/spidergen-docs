# AApplication
> **Extends**: 

응용프로그램을 관리하는 클래스, AApplication 의 onReady 함수가 프로그램의 시작 지점이 된다.

<br/>

## Properties


### curPath

어플리케이션의 작업 디렉토리 경로를 갖고있는 변수이다.

* **Type**: `String`
* **Default**: 

<br/>

### keyDownListeners

keyDownListeners배열

* **Type**: `Array`
* **Default**: 

<br/>

### keyUpListeners

keyUpListeners배열

* **Type**: `Array`
* **Default**: 

<br/>

### mainContainer

루트 컨테이너 밑으로, 화면을 표현하는 시작 컨테이너

* **Type**: `Object`
* **Default**: 

<br/>

### mdiManager

동적으로 생성되는 MDIManager 객체를 갖고 있는 변수이다.

* **Type**: `Object`
* **Default**: 

<br/>

### orientation

현재 화면 방향을 저장해두는 변수이다. (portrait 또는 landscape)

* **Type**: `String`
* **Default**: 

<br/>

### resPool

동적으로 생성되는 resPool 객체를 갖고 있는 변수이다.

* **Type**: `Object`
* **Default**: 

<br/>

### rootContainer

body 태그를 기반으로 하는 최상위 컨테이너, 화면을 표현하지는 않는다.

* **Type**: `Object`
* **Default**: 

<br/>

<br/>

## Methods

### addKeyEventListener( type, listener )

기존에 추가된것이 리스너가 있다면 제거하고 KeyEventListener를 추가한다.

* **Parameters**: 
	* **`type`** {String} type
	* **`listener`** {String} listener

<br/>

### closeActiveDocTmplFile( callback, isForce, isSave )

현재 활성화된 Document의 파일을 close한다.

* **Parameters**: 
	* **`callback`** {Function} 콜백함수
	* **`isForce`** {String} isForce
	* **`isSave`** {String} isSave

<br/>

### getActiveContainer()

현재 활성화된 container를 리턴한다.

* **Returns**: Object

<br/>

### getActiveDocument()

현재 활성화된 Document를 리턴한다.

* **Returns**: Object

<br/>

### getActiveView()

현재 활성화된 View를 리턴한다.

* **Returns**: Object

<br/>

### getCurrentPath()

현재 어플리케이션의  URL Path를 리턴한다.

* **Returns**: String

<br/>

### getMainContainer()

루트 컨테이너 밑으로, 화면을 표현하는 시작 컨테이너를 리턴한다.

* **Returns**: Object

<br/>

### getOrientation()

현재 화면 방향을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
theApp.getOrientation();
```

<br/>

### initKeyEvent()

root document에 이벤트를 등록해서 keydown, keyup이벤트를 하위 리스너에게 전달해주는 역할을 하는 함수이다. 마지막에 추가된 리스너가 우선적으로 호출하고 onKeydown 또는 onKeyUp함수에서 true를 리턴하면 다른 리스너에게 더 이상 전달되지 않는다.

<br/>

### onBackKeyManage()

android에서 back button 처리를 하기 위한 함수이다.

* **Returns**: Boolean

<br/>

### onClose()

어플리케이션이 Close될때 사용되는 함수이다. 네이티브가 종료될때 호출한다.

* **Returns**: boolean

<br/>

### onReady()

디바이스가 Ready상태일떄 호출된다.

<br/>

### openDocTmplFile( filePath )

해당 경로의 파일을 오픈한다.

* **Parameters**: 
	* **`filePath`** {String} filePath

<br/>

### removeKeyEventListener( type, listener )

등록된 KeyEventListener를 제거한다.

* **Parameters**: 
	* **`type`** {String} type
	* **`listener`** {String} listener

<br/>

### saveActiveDocTmplFile()

현재 활성화된 document의 파일을 저장한다.

<br/>

### setCurrentPath()

어플리케이션의 URL Path를 설정한다.

<br/>

### setMainContainer( container )

루트 컨테이너 밑으로, 화면을 표현하는 시작 컨테이너를 설정한다.

* **Parameters**: 
	* **`container`** {String} container

<br/>

### unitTest( unitUrl )

개발자가 테스트 목적으로 파라미터로 받은 url을 바로 실행해서 보여주는 함수이다.

* **Parameters**: 
	* **`unitUrl`** {String} url

* **Usage**: 
```js
theApp.unitTest('view/test.lay');
```

<br/>

### getDataPath()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getProcessPath()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getRootContainer()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### onError()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### loadThemeInfo()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### changeTheme()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### getTheme()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setTheme()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### reportThemeEvent()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### addThemeEventListener()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### removeThemeEventListener()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>
