# ADocument
> **Extends**

문서 클래스 ADocument

<br/>

## Class Variables

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

```js
document.newDocument('C:\path\newName.prj', 'newName');
```

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

문서의 수정여부를 지정하면서 theApp.mdiManager의 수정여부를 표현하는 함수를 호출한다.

* `modified` \<Boolean> 수정여부

```js
document.reportModify(true);
document.setModifiedFlag(false);
// 수정여부는 false 지만 표현은 true 이다.
```

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
