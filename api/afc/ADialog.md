# ADialog
**Extends** [`AFrameWnd`](./AFrameWnd.md)

원하는 lay파일을 화면 위에 띄우는 다이얼로그

<br/>

## Instance Methods

### makeTitle()

다이얼로그의 타이틀을 생성하는 함수이다.

<br/>

### onCancel()

취소버튼을 클릭했을때 호출되는 함수이다.

<br/>

### onCloseBtnClick()

클로즈 버튼 클릭 시 발생하는 이벤트이며 직접 호출 시에도 클로즈 된다.

```js
dialog.onCloseBtnClick();
```

<br/>

### onOK()

확인버튼을 누를때 호출되는 함수이다.

<br/>

### open( viewUrl, parent, width, height )

Dialog를 오픈한다.

- `viewUrl` \<String> url path
- `parent` \<String> 부모 컨테이너
- `width` \<String> 너비
- `height` \<String> 높이

```js
var dialog = new ADialog();
dialog.open('view/dialog.lay',null, 200, 300);
```

<br/>
