# ADocument
> **Extends**: 

ADocument

<br/>

## Properties


### docName



* **Type**: ``
* **Default**: ``

<br/>

### uri



* **Type**: ``
* **Default**: ``

<br/>

### docType



* **Type**: ``
* **Default**: ``

<br/>

### view



* **Type**: ``
* **Default**: ``

<br/>

### modified



* **Type**: ``
* **Default**: ``

<br/>

### isNewDoc



* **Type**: ``
* **Default**: ``

<br/>

### contents



* **Type**: ``
* **Default**: ``

<br/>
<br/>


## Methods

### closeDocument()

다큐먼트를 닫는다.

* **Usage**: 
```js
document.closeDocument();
```

<br/>

### getView()

바인드 되어있는 뷰를 리턴한다.

* **Returns**: AView

* **Usage**: 
```js
var result = document.getView();
```

<br/>

### isClosed()

다큐먼트의 클로즈상태 여부를 리턴한다.

* **Returns**: bool

<br/>

### isModified()

다큐먼트의 수정상태 여부를 리턴한다.

* **Returns**: bool

* **Usage**: 
```js
var reuslt = document.isModified();
```

<br/>

### newDocument( docName )

다큐먼트를 새로 만든다.

* **Parameters**: 
	* **`docName`** {String} 다큐먼트 이름

* **Usage**: 
```js
document.newDocument('newName');
```

<br/>

### openDocument( openPath )

다큐먼트를 오픈한다.

* **Returns**: bool

* **Parameters**: 
	* **`openPath`** {String} 오픈 경로

* **Usage**: 
```js
document.openDocument('C:\path\filename.prj');
```

<br/>

### saveDocument( savePath )

다큐먼트를 저장한다.

* **Returns**: bool

* **Parameters**: 
	* **`savePath`** {String} 저장 경로

* **Usage**: 
```js
document.saveDocument('C:\path\saveFile.prj');
```

<br/>

### setModifiedFlag( modified )

다큐먼트의 수정여부를 설정한다.

* **Parameters**: 
	* **`modified`** {String} 수정여부

* **Usage**: 
```js
document.setModifiedFlag(true);
```

<br/>

### setView( view )

뷰를 설정한다.

* **Parameters**: 
	* **`view`** {String} 뷰

* **Usage**: 
```js
var view = new AView();
view.init();
.
.
document.setView(view);
```

<br/>

### reportModify()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

<br/>
