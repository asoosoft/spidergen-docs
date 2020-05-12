# KeyboardManager
> **Extends**: 

네이티브 키보드가 나타날 때 웹 화면의 위치를 변경해주는 객체

<br/>

## Properties


### displayHeight

keyboard show 시에 textfield 위치 계산하기 위한 네이티브 키보드 높이를 저장한다.

* **Type**: `String or Number`
* **Default**: `0`

<br/>

### oriPos

윈도우의 원래 위치를 저장한다.

* **Type**: `Number`
* **Default**: `null`

<br/>

### topWnd

최상위 윈도우를 저장한다. 키보드가 떠서 화면의 위치를 변경하는데 윈도우가 떠 있는 경우에는 윈도우의 위치를 변경해야 한다.

* **Type**: `AWindow`
* **Default**: `null`

<br/>

### wndMove

윈도우의 위치를 변경할 값을 저장한다.

* **Type**: `Number`
* **Default**: `0`

<br/>
<br/>

## Methods

### KeyboardManager.inputScrollToCenter( input, isAppear )

input 관련 태그가 중앙으로 위치할 수 있게 처리한다.

* **Parameters**: 
	* **`input`** {String} input 엘리먼트
	* **`isAppear`** {String} 키보드가 나타날때 호출되었는지 여부

<br/>

### KeyboardManager.onKeyBoardHide()

키보드가 사라질 때 호출된다. input 관련 태그가 중앙으로 위치할 수 있게 처리했던 부분들을 복원한다.

<br/>

### KeyboardManager.onKeyBoardShow( displayHeight, keyboardHeight )

네이티브 키보드가 보여질 때 호출된다. input 관련 태그를 중앙으로 변경하기 위해 필요한 정보를 저장하고 처리를 한 뒤 위치를 변경하는 inputScrollToCenter 함수를 호출한다.

* **Parameters**: 
	* **`displayHeight`** {String} 화면 높이
	* **`keyboardHeight`** {String} 네이티브 키패드 높이

<br/>

### KeyboardManager.replaceHeight()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### KeyboardManager.restoreHeight()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
