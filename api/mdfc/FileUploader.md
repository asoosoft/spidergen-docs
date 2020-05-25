# FileUploader
**Extends**: [`AView`](./../afc/AView.md)

파일업로드 컴포넌트.

<br/>

## Class Variables

<br/>

## Instance Variables

<br/>

## Class Methods

<br/>

## Instance Methods

### getUrl()

컴포넌트에 지정된 업로드 url 정보를 가져온다.

- **Returns** \<String> 업로드 url

<br/>

### getValue()

파일 업로드로 첨부된 파일의 정보를 가져온다.

- **Returns** \<JSON Object> 첨부된 파일의 정보
  - fileName 파일의 이름
  - size 파일의 크기(byte 단위)
  - sizeMB 파일의 크기(KB 또는 MB등으로 간소화)
  - multiple 다중 선택 여부
  - accept 파일의 검색 타입 

<br/>

### send( data, callback)

파일업로더 컴포넌트로 선택한 파일을 전송한다.

- `data` \<JSON Object> 선택된 파일과 함께 전송할 데이터 객체
- `callback` \<function> 콜백함수

<br/>

### setAccept( accept )

파일 종류를 설정한다.

- `accept` \<String> 파일 종류
```js
this.fileUploader.setAccept('*.*');        //전체
this.fileUploader.setAccept('image/*');    //이미지파일
this.fileUploader.setAccept('text/plain'); //텍스트 파일
this.fileUploader.setAccept('text/html');  //웹문서
this.fileUploader.setAccept('video/*');    //비디오파일
this.fileUploader.setAccept('audio/*');    //오디오파일
this.fileUploader.setAccept('.cls');       //확장자가 cls인 파일
this.fileUploader.setAccept('.lay');       //확장자가 lay인 파일
```

<br/>

### setDisabled( isDisabled )

컴포넌트의 사용여부를 설정한다.

- `isDisabled` \<Boolean> 사용여부

<br/>

### setDragdrop( blean )

첨부파일을 drag & drop으로 추가하는 기능 사용 여부

- `blean` \<Boolean> 기능 사용 여부

<br/>

### setReadOnly( isReadOnly )

컴포넌트의 읽기전용 속성을 설정한다.

- `isReadOnly` \<Boolean> 읽기전용 속성 여부

<br/>

### setMultiple( blean )

다중 첨부 가능 여부를 설정한다.

- `blean` \<Boolean> 다중 첨부 가능 여부

<br/>

### removeAll()

파일 업로더 컴포넌트를 초기화한다.

<br/>
