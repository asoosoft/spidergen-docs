# ADocument

ADocument 는 MDI 에서 AView 와 매칭되는 클래스이다.
즉, AView 가 화면을 표현하기 위한 Data 를 저장하고 있는 영역이다. 화면을 표현하기 위해 Data 에 접근하는 기능 외에 Data 를 특정 파일로 저장하거나 불러오는 등의 기능을 내장하고 있다.

<br/>

## Class Variables
없음

<br/>

## Instance Variables

### contents \<String>

문서 내용

<br/>

### docName \<String>

문서 이름

<br/>

### docType \<String>

문서 확장자

<br/>

### isNewDoc \<Boolean>

문서 새로 생성여부

<br/>

### modified \<Boolean>

문서 수정여부

<br/>

### uri \<String>

문서 경로

<br/>

### view \<AView>

문서에 연결된 AView 객체. 문서 내용을 화면에 표현한다.

<br/>
<br/>

## Class Methods
없음

<br/>

## Instance Methods

### closeDocument()

문서를 닫는다.

<br/>

### getView()

바인드 되어있는 뷰를 리턴한다.

* **Returns** \<[AView](./AView.md)> 바인드 된 뷰

<br/>

### isClosed()

문서의 닫힘상태 여부를 가져온다.

* **Returns** \<Boolean> 닫힘여부

<br/>

### isModified()

문서의 수정상태를 가져온다.

* **Returns** \<Boolean> 수정여부

<br/>

### newDocument( uri, docName )

문서를 새로 만든다.

* `uri` \<String> 문서 경로
* `docName` \<String> 문서 이름

<br/>

### openDocument( openPath )

문서를 오픈한다.

* `openPath` \<String> 오픈 경로
* **Returns** \<Boolean> 오픈여부

```js
document.openDocument('C:\path\filename.prj');
```

<br/>

### reportModify( modified )

문서의 수정여부를 지정하면서 theApp.mdiManager 의 applyModifiedMark 함수를 내부적으로 호출한다. applyModifiedMark 함수는 문서가 수정중임을 화면에 표시한다.

* `modified` \<Boolean> 수정여부

<br/>

### saveDocument( savePath )

경로에 문서를 저장한다. savePath 가 없는 경우 this.uri 에 저장

* `savePath` \<String> 저장 경로
* **Returns** \<Boolean> 저장여부

```js
document.saveDocument('C:\path\saveFile.prj');
```

<br/>

### setModifiedFlag( modified )

문서의 수정여부 값만 설정한다.

* `modified` \<Boolean> 수정여부

```js
document.setModifiedFlag(false);
```

<br/>

### setView( view )

문서에 연결할 뷰를 설정한다.

* `view` \<[AView](./AView.md)> 문서에 연결될 뷰 객체

```js
var view = new AView();
view.init();
.
.
document.setView(view);
```

<br/>
<br/>
