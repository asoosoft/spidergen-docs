# AMessageBox
**Extends**: [`ADialog`](ADialog.html#ADialog)

원하는 텍스트의 메시지박스를 띄운다.

<br/>

## Properties

### message \<String>

메시지박스에 띄울 메시지

<br/>

### type \<Number>

타입에 따라 버튼의 구성이 바뀐다.

- AMessageBox.EMPTY : 버튼 없음
- AMessageBox.OK : OK
- AMessageBox.OK_CANCEL : OK, CANCEL
- AMessageBox.YES_NO : YES, NO
- AMessageBox.YES_NO_CANCEL : YES, NO, CANCEL

```js
messageBox.type = AMessageBox.OK_CANCEL;
```

<br/>
<br/>

## Instance Methods

### addCustomButton( text, value )

커스텀버튼을 추가한다

* `text` \<String> 텍스트
* `value` \<String> 데이터

```js
var msgBox = new AMessageBox('sample');
msgBox.openBox(null, '커스텀버튼 메시지입니다',  AMessageBox.EMPTY, function(result)
{
　if(result == 999) console.log('확인'); // 확인시 처리
});
msgBox.addCustomButton('확인', '999');
```

<br/>

### init( context )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.<br/>openBox()를 호출 하면 자동으로 init 되므로 바로 오픈하는 경우에는 생략할 수 있다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보

```js
var msgBox = new AMessageBox();
msgBox.init();
```

<br/>

### onBtnClick( comp, info )

makeButton으로 만든 버튼을 클릭했을때 호출되는 함수, 객체에 저장해둔 value값을 리턴한다

* `comp` \<AButton> 버튼 객체
* `info` \<Object> listener 의 이벤트 함수에 두번째 파라미터로 전달되는 값

<br/>

### onCancel()

취소버튼을 눌렀을때 메세지박스를 닫으면서 호출되는 함수. callback 함수에 타입에 따라서 result값이 전달된다. 전달되는 값은 다음과 같다

- AMessageBox.OK : 0
- AMessageBox.OK_CANCEL : 1
- AMessageBox.YES_NO : 1
- AMessageBox.YES_NO_CANCEL : 2
- default : 1

<br/>

### openBox( parent, message, type, callback )

MessageBox를 오픈한다

- `parent` \<AContainer> 부모 컨테이너
- `message` \<String> 메시지박스에 보여줄 메세지
- `type` \<Number> 메세지 박스의 종류 (AMessageBox.EMPTY, AMessageBox.OK, AMessageBox.OK_CANCEL, AMessageBox.YES_NO, AMessageBox.YES_NO_CANCEL)
- `callback` \<Function> 메세지 박스가 종료될때 실행되는 콜백함수

```js
var msgBox = new AMessageBox('sample');
msgBox.openBox(null, '메시지박스 오픈 예제입니다', AMessageBox.OK, function(result)
{
　console.log('확인');
});
```

<br/>

### setMessage( msg )

메시지박스에 띄울 메시지를 세팅한다

- `msg` \<String> 메시지

<br/>

### setWidth( w )

메시지박스의 넓이를 지정한다. 메시지박스 내부의 뷰 넓이는 -20 한 값으로 지정한다.

- `w` \<Number> 넓이

```js
var msgBox = new AMessageBox('sample');
msgBox.openBox(null, '샘플', AMessageBox.OK_CANCEL, function(result)
{
　if(result==0) console.log('확인'); // 확인시 처리
});
msgBox.setWidth(300);
```

<br/>