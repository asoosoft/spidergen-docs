# EXSecureTextField
> **Extends**: [`ATextField`](./../afc/ATextField.md)

보안키패드를 띄워주는 텍스트필드 상속 컴포넌트

[SecurePadManager](#SecurePadManager-작성-요령) 또는 SecureWebPadManager 의 함수를 이용하여 호출한다.

<br/>

## Properties

<!-- ### frwName



* **Type**: ``
* **Default**: ``

<br/> -->

<!-- ### useSecure



* **Type**: ``
* **Default**: `false`

<br/> -->

### cipherData \<String>

키패드에서 전달된 암호화 데이터

<br/>

### pwLength \<Number>

키패드에서 전달된 암호화 데이터 길이

<br/>

### padOption \<Object>

암호화 키패드에 적용될 옵션

```js
this.padOption =
{
    title: '비밀번호 입력',
    padType: 'char', 
    returnType: "1",
    maxLength: 20,
    minLength: 4
};
```

<br/>

<!-- ### isTabable



* **Type**: ``
* **Default**: ``

<br/> -->

<br/>

## Method

### init( context, evtListener )

padOption을 셋팅한다.

- `context` \<String> or \<Element> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<Object> context 에 매핑된 이벤트 수신자

<br/>

### setCipherData( cipherData ) 

암호화 데이터를 저장한다.

- `cipherData` \<String> or \<Object> 

```js
this.sxf.setCipherData(cipherData);
```

<br/>

### getCipherData()

암호화 데이터를 반환한다.

* **Returns** \<String> or \<Object>

```js
this.sxf.getCipherData();
```

<br/>

### setPwLength(len)

암호화 데이터 길이를 세팅한다.

- `len` \<Number> 

```js
this.sxf.setPwLength(len);
```

<br/>

### getPwLength()

암호화 데이터 길이를 반환한다.

* **Returns**: \<Number>

```js
this.sxf.getPwLength();
```

<br/>

### reset()

데이터를 초기화한다.

```js
this.sxf.clear();
```

<br/>

### openPad()

키패드 옵션에 맞는 네이티브 키패드를 오픈한다.

```js
this.sxf.openPad();
```

<br/>

### openWebPad()

키패드 옵션에 맞는 웹 키패드를 오픈한다.

```js
this.sxf.openWebPad();
```

<br/>

## 추가 정보

### SecurePadManager 작성 요령
```js
var SecurePadManager = {
    isEnable: true, //사용여부
    callback: null, //콜백저장
    sxf: null,      //SecureTexField 객체 저장
    openPad: function(padOption, callback, sxf) {

        //콜백, sxf 저장
        SecurePadManager.callback = callback;
        SecurePadManager.sxf = sxf;

        //padOption 에 맞게 보안키패드 오픈

        //키패드 입력 완료시 호출
        callback(true, cipherData, len);
        
        //키패드 입력 취소
        callback(true, null, 0);
        //콜백, sxf 제거
        //SecurePadManager.callback = null;
        //SecurePadManager.sxf = null;
    },

    //키패드 입력시에 화면에 표시하고 싶은 경우 호출
    onKeyPadClick: function(obj) {
        if(SecurePadManager.callback) {
            SecurePadManager.callback(false, null, obj.len);
        }
    }
};
```