# FileUpload
> **Extends**: `AView`

지정된 url에 ajax사용하여 파일첨부를 한다.

<br/>

## Methods

### createElement( context )

엘러먼트를 생성해 줍니다.<br/>내부적으로 사용하는 함수입니다.<br/>이 함수가 실행된 이후에 init 함수가 실행됩니다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트를 생성 및 초기화 정보

<br/>

### getValue()

파일업로더에 설정된 파일의 정보를 반환한다.

* **Returns**: json

* **Usage**: 
```js
var info = this.fileupload.getValue();
console.log(info);
//{fileName: "a.zip (5 MB)", size: 1112, sizeMB: "1 MB", multiple: false, accept: ""}
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출합니다. 동적으로 객체를 생성할 경우 파라미터를 생략하고 호출합니다.

* **Parameters**: 
	* **`context`** {Object} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {Object} context에 매핑된 이벤트 수신자

<br/>

### send( callback )

파일업로드에 지정한 파일을 실제 url에 전송 후<br/>매개변수 callback 함수에 result 인자를 담아 호출한다.

* **Parameters**: 
	* **`callback`** {Function} 콜백함수

* **Usage**: 
```js
this.fileupload.send(function(result) {
    console.log(result);
    //{result: true, message: "전송완료"}
});
```

<br/>

### setAccept( accept )

파일업로드에서 선택가능한 파일형식을 설정한다.

* **Parameters**: 
	* **`accept`** {String} 속성 문자열

* **Usage**: 
```js
this.fileupload.setAccept('image/*');

/*
모든파일 : '*.*'
이미지 파일 : 'image/*'
텍스트 파일 : 'text/plain'
Html 파일 : 'text/html'
*/
```

<br/>

### setDisabled( isDisabled )

파일업로더의 사용여부를 설정한다.

* **Parameters**: 
	* **`isDisabled`** {Boolean} 사용여부

* **Usage**: 
```js
this.fileupload.setDisabled(true);
```

<br/>

### setDragdrop( blean )

파일업로더에 드래그&드롭을 설정한다.

* **Parameters**: 
	* **`blean`** {Boolean} 설정여부

* **Usage**: 
```js
this.fileupload.setDragdrop(true);
```

<br/>

### setMultiple( blean )

파일업로더의 다중 파일 선택 속성을 설정한다.

* **Parameters**: 
	* **`blean`** {Boolean} 설정여부

* **Usage**: 
```js
this.fileupload.setMultiple(true);
```

<br/>

### setReadOnly( isReadOnly )

파일업로더의 읽기전용 속성을 설정한다.

* **Parameters**: 
	* **`isReadOnly`** {Boolean} 읽기전용 여부

* **Usage**: 
```js
this.fileupload.setReadOnly(true);
```

<br/>
<br/>
