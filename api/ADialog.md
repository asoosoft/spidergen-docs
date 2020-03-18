# ADialog
> **Extends**: `AFrameWnd`

ADialog

<br/>

## Methods

### close( result, data )

다이얼로그를 close하는 함수이다.

* **Returns**: close

* **Parameters**: 
	* **`result`** {String} 결과값
	* **`data`** {String} 결과 데이터

* **Usage**: 
```js
dialog.close();
```

<br/>

### makeTitle()

다이얼로그의 타이틀을 생성하는 함수이다.

<br/>

### onCancel()

취소버튼을 클릭했을때 호출되는 함수이다.

<br/>

### onCreateDone()

다이얼로그 생성 직후에 호출되는 함수이다.

<br/>

### onKeyDown( event )

키다운 이벤트를 매핑합니다. / enter: 확인  esc: 취소

* **Parameters**: 
	* **`event`** {Object} 이벤트

<br/>

### onOK()

확인버튼을 누를때 호출되는 함수이다.

<br/>

### open( viewUrl, parent, width, height )

Dialog를 오픈한다.

* **Returns**: open

* **Parameters**: 
	* **`viewUrl`** {String} url path
	* **`parent`** {String} 부모 컨테이너
	* **`width`** {String} 너비
	* **`height`** {String} 높이

* **Usage**: 
```js
var dialog = new ADialog();
dialog.open('view/dialog.lay',null, 200, 300);
```

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### onCloseBtnClick()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
