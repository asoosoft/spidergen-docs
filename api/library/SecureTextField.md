# EXSecureTextField
**Extends**: [`ATextField`](../api/ATextField.html#atextfield)

보안 키패드를 띄운다. 네이티브에 보안키패드 라이브러리 혹은 기능이 있어야 한다.

<br/>

## Properties

### cipherData \<String>

암호화 된 데이터

<br/>

### pwLength \<Number>

입력 된 비밀번호의 길이

<br/>

### padOption \<Object>

보안 키패드의 옵션<br/>

title: \<String> 타이틀<br/>
padType: \<String> 패드 유형<br/>
returnType: \<Number> 반환 유형<br/>
maxLength: \<Number> 최대길이<br/>
minLength: \<Number> 최소길이

<br/>

### isTabable \<Boolean>

탭키 이동이 가능한 컴포넌트 여부

<br/>
<br/>

## Instance Methods



### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var securePad = new EXSecureTextField();
securePad.init();
```