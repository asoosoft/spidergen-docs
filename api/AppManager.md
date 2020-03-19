# AppManager
> **Extends**: 

네이티브 기능을 호출하는 클래스

<br/>

## Methods

### beep( volumn )

네이티브의 알림음을 발생시킵니다.

* **Parameters**: 
	* **`volumn`** {Number} 볼륨

<br/>

### beginOltp( sec )

여러 TR요청을 하나의 프로그레스바로 묶는 Oltp를 시작합니다.

* **Parameters**: 
	* **`sec`** {Number} 프로그레스바 제한시간(초)

<br/>

### clearPref( key )

네이티브에 저장한 데이터를 삭제합니다.

* **Parameters**: 
	* **`key`** {String} 삭제할 데이터 키 값

<br/>

### enableApp( isEnable )

앱의 활성화여부를 셋팅합니다.

* **Parameters**: 
	* **`isEnable`** {Boolean} 활성화여부(true:활성 / false:비활성)

<br/>

### endOltp()

여러 TR요청을 하나의 프로그레스바로 묶는 Oltp를 종료합니다.

<br/>

### exitApp()

앱을 종료 시킵니다.

<br/>

### getModelName( callback )

네이티브의 모델명을 가져옵니다.

* **Parameters**: 
	* **`callback`** {Function} 모델명을 가져온 후 실행해야할 함수

<br/>

### getPref( key, callback )

네이티브에 저장한 데이터를 가져옵니다.

* **Parameters**: 
	* **`key`** {String} 불러올 데이터의 키값
	* **`callback`** {Function} 데이터를 가져온 후 실행해야할 함수

<br/>

### getVersion( callback )

네이티브의 버전정보를 가져옵니다.

* **Parameters**: 
	* **`callback`** {Function} 버전정보를 가져온 후 실행해야할 함수

<br/>

### goUrl( callback, isClose )

네이티브의 기본 브라우저를 띄웁니다.

* **Parameters**: 
	* **`callback`** {String} 버전정보를 가져온 후 실행해야할 함수
	* **`isClose`** {Boolean} 앱을 종료할지 여부(true:종료 / false:종료안함)

<br/>

### hideProgress()

프로그레스바를 숨김니다.

<br/>

### openPdf( url )

네이티브에서 Pdf 문서를 엽니다.

* **Parameters**: 
	* **`url`** {String} Pdf문서 경로

<br/>

### sendSMS( phone, msg )

네이티브에서 문자를 전송합니다.

* **Parameters**: 
	* **`phone`** {String} 전화번호
	* **`msg`** {String} 전송할 메세지

<br/>

### setPortrait( isPortrait )

스크린 방향을 셋팅합니다.

* **Parameters**: 
	* **`isPortrait`** {Boolean} 세로여부(true: 세로모드 / false: 가로모드)

<br/>

### setPref( key, val )

네이티브에 데이터를 저장합니다.

* **Parameters**: 
	* **`key`** {String} 저장할 데이터의 키값
	* **`val`** {String} 저장할 데이터

<br/>

### showProgress( sec )

프로그레스바를 표시합니다.

* **Parameters**: 
	* **`sec`** {Number} 프로그레스바 제한시간(초)

<br/>

### vibrator()

네이티브의 진동을 발생시킵니다.

<br/>

### loadWebView()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### bringToFront()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### destroyWebView()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### sendEmail()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setOrientation()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### deleteFile()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### kakaoLogin()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### screenShoot()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### callApp()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### goDeepLink()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### addLog()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### appAlert()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### closeAppAlert()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### callApplication()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### applyPref()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### hidePatchView()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
>

### getSystemInfo()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getAppName()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### goUrlWebView()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### touchDelay()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### screenshoot()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getAppId()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### playAudio()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getPhoneInfo()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### phoneCall()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getUuid()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getIpAddress()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### consoleLog()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### downloadFile()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getImageBase64()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### getResponseText()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### openChrome()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### openChromeCustom()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### wowEncode()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### wowExEncode()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### wowDecode()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### wowExDecode()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
