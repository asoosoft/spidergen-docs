# SecurePadManager
**Extends**: `Object`

보안 키패드 객체

<br/>

## Properties


### callbackFunc \<Function>

보안 키패드 입력 후 호출할 콜백함수 저장 변수.

<br/>
<br/>

## Class Methods

### functionCheck( callback )

이미 저장된 콜백함수가 없으면 파라미터로 넘어온 콜백함수를 저장한다. 저장을 한 경우 true, 저장을 못한 경우 false를 반환한다.

- `callback` \<Function> 콜백함수
- **Returns** \<Boolean>

<br/>

### openPad( option, callback )

키패드 옵션에 맞는 네이티브 키패드를 오픈한다.

- `option` \<String> 키패드 옵션 정보 객체
- `callback` \<String> 콜백 함수

<br/>

### padWorkDone( code, data, len )

보안 키패드 입력 완료 후 호출된다. 저장된 콜백함수를 호출하고 제거한다.

- `code` \<String> 결과값(확인 또는 취소)
- `data` \<String> 키패드로 입력된 값 정보
- `len` \<String> 입력 길이

<br/>

### resetCallback()

저장한 콜백함수를 제거한다.

<br/>
<br/>
