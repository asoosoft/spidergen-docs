# KeyboardManager
**Extends**: 

네이티브 키보드가 나타날 때 웹 화면의 위치를 변경해주는 객체

<br/>

## Properties


<br/>

### resizeWebview \<Boolean>

웹뷰 사이즈를 재설정 할지 여부

<br/>
<br/>

## Class Methods

### KeyboardManager.inputScrollToCenter( input, isAppear )

input 관련 태그가 중앙으로 위치할 수 있게 처리한다.

- `input` \<String> input 엘리먼트
- `isAppear` \<String> 키보드가 나타날때 호출되었는지 여부

<br/>

### KeyboardManager.onKeyBoardHide()

키보드가 사라질 때 호출된다. input 관련 태그가 중앙으로 위치할 수 있게 처리했던 부분들을 복원한다.

<br/>

### KeyboardManager.onKeyBoardShow( displayHeight, keyboardHeight )

네이티브 키보드가 보여질 때 호출된다. input 관련 태그를 중앙으로 변경하기 위해 필요한 정보를 저장하고 처리를 한 뒤 위치를 변경하는 inputScrollToCenter 함수를 호출한다.

- `displayHeight` \<String> 화면 높이
- `keyboardHeight` \<String> 네이티브 키패드 높이

<br/>
<br/>
