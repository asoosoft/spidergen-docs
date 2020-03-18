# AMessageBox
> **Extends**: `ADialog`

AMessageBox

<br/>

## Properties


### message



* **Type**: ``
* **Default**: ``

<br/>

### type



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### addCustomButton( text, value )

커스텀버튼을 추가합니다.

* **Parameters**: 
	* **`text`** {String} Text
	* **`value`** {String} Vaule

* **Usage**: 
```js
var msgBox = new AMessageBox('sample');
msgBox.openBox(null, '커스텀버튼 메시지입니다',  AMessageBox.EMPTY, function(result)
{
　if(result == 999) console.log('확인'); // 확인시 처리
});
msgBox.addCustomButton('확인', '999');
```

<br/>

### addTypeButton()

type에 따라서 버튼을 생성하는 함수입니다. (onCreate될때 자동으로 호출되므로 따로 호출할 필요는 없습니다.)

<br/>

### makeButton( text, value )

버튼을 만드는 함수입니다. (addTypeButton나 addCustomButton함수에서 버튼을 만들때 내부적으로 사용하는 함수입니다.)

* **Returns**: AButton

* **Parameters**: 
	* **`text`** {String} text
	* **`value`** {String} value

<br/>

### onBtnClick( comp, info )

makeButton으로 만든 버튼을 클릭했을때 호출되는 함수, 객체에 저장해둔 value값을 리턴합니다.

* **Returns**: Object

* **Parameters**: 
	* **`comp`** {AButton} 버튼 객체
	* **`info`** {Object} listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값

<br/>

### onCancel()

취소버튼을 눌렀을때 메세지박스를 닫으면서 호출되는 함수입니다. callback 함수에 타입에 따라서 result값이 전달됩니다. 전달되는 값은 다음과 같습니다.<br/>AMessageBox.OK : 0,<br/>AMessageBox.OK_CANCEL : 1,<br/>AMessageBox.YES_NO : 1,<br/>AMessageBox.YES_NO_CANCEL : 2<br/>default : 1

<br/>

### openBox( parent, message, type, callback )

MessageBox를 오픈합니다.

* **Parameters**: 
	* **`parent`** {AContainer} 부모 컨테이너
	* **`message`** {String} 메시지박스에 보여줄 메세지
	* **`type`** {Number} 메세지 박스의 종류 (AMessageBox.EMPTY, AMessageBox.OK, AMessageBox.OK_CANCEL, AMessageBox.YES_NO, AMessageBox.YES_NO_CANCEL)
	* **`callback`** {Function} 메세지 박스가 종료될때 실행되는 콜백함수

* **Usage**: 
```js
var msgBox = new AMessageBox('sample');
msgBox.openBox(null, '메시지박스 오픈 예제입니다', AMessageBox.OK, function(result)
{
　console.log('확인');
});
```

<br/>

### setWidth( w )

메시지박스의 넓이를 지정한다. 메시지박스 내부의 뷰 넓이는 -20 한 값으로 지정한다.

* **Parameters**: 
	* **`w`** {Number} 넓이

* **Usage**: 
```js
var msgBox = new AMessageBox('sample');
msgBox.openBox(null, '샘플', AMessageBox.OK_CANCEL, function(result)
{
　if(result==0) console.log('확인'); // 확인시 처리
});
msgBox.setWidth(300);
```

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### onCreate()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### setMessage()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

### addCustomButton()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>
