# MDIManager
> **Extends**: 

다중 문서 인터페이스 관리 클래스

<br/>

## Properties


### copyTabHistory

저장된 탭의 히스토리를 복사한 배열. 히스토리 처리를 할 때 사용한다.

* **Type**: `Array`
* **Default**: `[]`

<br/>

### docPanel

문서패널 저장 변수. 컨테이너를 분할하여 만든 패널

* **Type**: `AContainer`
* **Default**: `null`

<br/>

### docTmplMap

문서 확장자별 템플릿 저장 객체

* **Type**: `Object`
* **Default**: `{}`

<br/>

### matchingMap

문서 타입별로 연관되는 확장자를 저장하는 객체. 예) cls-lay

* **Type**: `Object`
* **Default**: `{}`

<br/>

### tabHistory

탭의 히스토리를 저장하는 배열

* **Type**: `Array`
* **Default**: `[]`

<br/>

### tabOffset

현재 히스토리 위치를 저장한다.

* **Type**: `Number`
* **Default**: `1`

<br/>

### tabPanel

탭패널 저장 변수. 컨테이너를 분할하여 만든 패널

* **Type**: `AContainer`
* **Default**: `null`

<br/>

### trgContainer

문서를 관리할 컨테이너

* **Type**: `AContainer`
* **Default**: `null`

<br/>

### tabBar



* **Type**: ``
* **Default**: ``

<br/>

### defaultIcon



* **Type**: ``
* **Default**: ``

<br/>

### iconByExtObj



* **Type**: ``
* **Default**: ``

<br/>

### cntrClass



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### activeDocContainer( filePath )

문서를 연다. 파일 경로나 선택할 탭이 없으면 null을 반환한다. 탭을 선택하여 활성화하고 숨겨져있는 탭이면 제일 왼쪽으로 탭의 위치를 변경한다. 탭 히스토리에 저장하고, 문서가 활성화 되어있지 않은 경우 활성화한다.

* **Returns**: AView

* **Parameters**: 
	* **`filePath`** {String} 파일 경로

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var filePath = "C:\SampleProject\SampleProjectApp.cls";
mdiMgr.activeDocContainer(filePath);
```

<br/>

### addMatchingExt( ext1, ext2 )

문서 타입별로 연관되는 확장자를 저장한다. 예) cls-lay

* **Parameters**: 
	* **`ext1`** {String} 확장자1
	* **`ext2`** {String} 확장자2

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
mdiMgr.addMatchingExt('cls', 'lay');
```

<br/>

### applyModifiedMark( doc )

수정여부를 알 수 있게 탭의 이름을 변경하여 적용한다.

* **Parameters**: 
	* **`doc`** {Object} ADocument 인스턴스 또는 상속 클래스의 인스턴스

<br/>

### backDocContainer()

이전 히스토리 탭을 활성화한다.

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
mdiMgr.backDocContainer();
```

<br/>

### closeAllActiveTabs( callback, exTab )

특정 탭을 제외하고 탭들을 모두 닫는 재귀함수이다. 문서가 수정된 상태이면 저장, 취소여부를 묻고 재귀처리한다.

* **Parameters**: 
	* **`callback`** {Function} 콜백 함수
	* **`exTab`** {AView} 닫지않을 탭 객체

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var exTab = mdiMgr.getLastTab();
mdiMgr.closeAllActiveTabs(function(result) {
　// result(true/false) 값에 따라 처리
}, exTab);
```

<br/>

### closeAllTabs( callback )

모든 탭을 닫는다. 현재 활성화된 탭을 제외한 다른 탭부터 모두 닫은 후, 마지막으로 활성화된 탭을 닫는다. 모든 탭이 닫히면 콜백 함수를 호출한다.

* **Parameters**: 
	* **`callback`** {Function} 콜백 함수

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
mdiMgr.closeAllTabs(function() {
　// 탭을 모두 닫은 후의 처리
});
```

<br/>

### closeDocContainer( filePath, callback, isForce, isSave )

문서를 닫는다. 문서가 수정된 경우 강제 처리 및 저장이면 문서를 강제로 저장하고, 강제 처리가 아니면 [저장, 저장안함, 취소] 할 지 여부를 묻는다. 완료된 후 콜백 함수를 호출한다. <br/>#콜백함수에 넘겨주는 파라미터 값<br/>- 강제 처리 아닌 경우 -1:탭없음 0:저장 1:아무일없음 2:취소<br/>- 강제 처리 맞는 경우 -1:탭없음 1: 그외 모든 상황

* **Parameters**: 
	* **`filePath`** {String} 파일 경로
	* **`callback`** {Function} 콜백 함수
	* **`isForce`** {Boolean} 강제 처리 여부
	* **`isSave`** {Boolean} 강제 저장 여부

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var filePath = "C:\SampleProject\SampleProjectApp.cls";
mdiMgr.closeDocContainer(filePath, function(result) {
　// result 값에 따라 처리
}, true, false); // 수정된 상태여도 강제로 저장하지 않고 닫는다.
```

<br/>

### closeOtherTabs( tabId, callback )

특정 탭을 제외한 모든 탭을 닫는다. 수정이 안되었거나 열리지 않은 탭을 먼저 닫고, 활성화된 탭은 순차적으로 닫는다.

* **Parameters**: 
	* **`tabId`** {String} 닫지 않을 탭 아이디
	* **`callback`** {Function} 콜백 함수

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var tabId = mdiMgr.getTabBar().getLastTab().tabId;
mdiMgr.closeOtherTabs('tab01', function(result) {
　// result(true/false) 값에 따라 처리
});
```

<br/>

### contextMenuEvent( acomp, info )

메뉴를 선택하면 발생되는 이벤트 함수이다. 선택한 메뉴정보에 맞게 처리한다.

* **Parameters**: 
	* **`acomp`** {All} AMenu 컴포넌트
	* **`info`** {Object} 선택한 메뉴 정보

<br/>

### findDocTemplate( filePath, index )

파일 경로의 확장자에 해당하는 문서 템플릿 정보를 찾는다. 문서 템플릿 정보가 여러개인 경우 index로 선택 가능하다.

* **Returns**: Object

* **Parameters**: 
	* **`filePath`** {String} 파일 경로
	* **`index`** {Number} 템플릿 배열 위치값. Default: 0

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var filePath = 'C:\SampleProject\sample.cls";
var docTmpl = mdiMgr.findDocTemplate(filePath, 0);
```

<br/>

### getActiveCntrIdx()

현재 활성화된 문서 컨테이너의 탭 순서를 반환한다.

* **Returns**: Number

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var cntrIdx = mdiMgr.getActiveCntrIdx();
```

<br/>

### getActiveContainer()

문서 컨테이너 중 현재 활성화된 컨테이너를 반환한다.

* **Returns**: AContainer

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var actCntr = mdiMgr.getActiveContainer();
```

<br/>

### getAllTabs()

지금까지 열린 문서의 모든 탭을 반환한다.

* **Returns**: Array

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var allTabs = mdiMgr.getAllTabs();
```

<br/>

### getDocPanel()

컨테이너 안의 docPanel 객체를 반환한다.

* **Returns**: APanel

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var docPanel = mdiMgr.getDocPanel();
```

<br/>

### getTabBar()

컨테이너 안의 tabPanel 안의 ATabBar 객체를 반환한다.

* **Returns**: ATabBar

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var tabBar = mdiMgr.getTabBar();
```

<br/>

### getTabPanel()

컨테이너 안의 tabPanel 객체를 반환한다.

* **Returns**: APanel

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var tabPanel = mdiMgr.getTabPanel();
```

<br/>

### getTargetContainer()

지정된 컨테이너를 반환한다.

* **Returns**: AContainer

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var targetCntr = mdiMgr.getTargetContainer();
```

<br/>

### isFileExisting( filePath, isAlert )

경로에 파일이 존재하는지를 판단한다. 웹에서는 사용할 수 없다. 파일이 없으면 isAlert 값에 따라 알림창을 표시한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`filePath`** {String} 파일 경로
	* **`isAlert`** {Boolean} 알림창 표시 여부

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var filePath = "C:\SampleProject\sample.cls";
mdiMgr.isFileExisting(filePath, true); // 파일 없으면 알림창 표시
```

<br/>

### onCloseContainer( tabBtnView )

ATabBar delegate function. 탭을 닫을 때 발생한다. 컨테이너가 닫히지 않게 true 값을 리턴하고 자체적인 로직을 통해 닫는다.

* **Parameters**: 
	* **`tabBtnView`** {AView} 탭 객체

<br/>

### onTabBarSelect( comp, info, e )

탭이 선택되었을 때 발생하는 이벤트 함수이다. 탭 히스토리를 저장하고 문서를 활성화한다. 마우스 오른쪽 클릭인 경우에는 메뉴팝업을 띄운다.

* **Parameters**: 
	* **`comp`** {AView} ATabBar 컴포넌트
	* **`info`** {AView} 탭
	* **`e`** {Object} event 객체

<br/>

### openDocContainer( filePath, docTmpl, noLoad, bSilent )

문서를 연다. 최초로 여는 경우에는 탭바에 문서정보를 가진 탭을 추가하며 noLoad 값이 true인 경우 문서를 활성화하지 않는다. 파일 경로에 해당하는 파일이 없는 경우에 bSilent 값에 따라 알림 처리한다.

* **Returns**: AView

* **Parameters**: 
	* **`filePath`** {String} 파일 경로
	* **`docTmpl`** {Object} 문서 템플릿
	* **`noLoad`** {Boolean} 문서의 활성화 여부
	* **`bSilent`** {Boolean} 경로에 파일이 없는 경우 알림 여부

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var filePath = 'C:\SampleProject\sample.cls";
mdiMgr.openDocContainer(filePath, null, false, true); // 문서 활성화, 파일없어도 알림메시지 안띄움
```

<br/>

### openMatchingDoc( filePath )

파일 경로와 연관되는 문서를 연다. 연관되는 문서는 연관 화장자를 등록한 경우에만 찾을 수 있다.(addMatchingExt)

* **Parameters**: 
	* **`filePath`** {String} 파일 경로

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var filePath = "C:\SampleProject\sample.cls";
mdiMgr.addMatchingExt('cls', 'lay');
mdiMgr.openMatchingDoc(filePath); // sample.lay
```

<br/>

### regDocTemplate( docTemplate )

문서 템플릿을 등록한다. 템플릿 구조는 아래와 같다.<br/>{ containerClass: '', documentClass: '', viewUrl: '', extNames: ['','',''] }<br/>containerClass: 문서를 담을 컨테이너 클래스명<br/>documentClass: ADocument 클래스 또는 상속받은 클래스명<br/>viewUrl: 문서를 보여줄 화면 url('Source/docView.lay')<br/>extNames: 문서 확장자 배열

* **Parameters**: 
	* **`docTemplate`** {Object} 템플릿

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
mdiMgr.regDocTemplate({
　cntrClass: 'AWindow',
　documentClass: 'SampleDoc',
　viewUrl: 'Source/SampleView.lay',
　extNames: ['txt', 'css']
});
```

<br/>

### removeHistory( tabId )

특정 탭을 히스토리에서 제거한다.

* **Parameters**: 
	* **`tabId`** {String} 탭 아이디

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
mdiMgr.removeHistory('tab01');
```

<br/>

### reportModify( doc, modified )

문서의 수정여부를 세팅하고, 수정여부에 따라 수정마크를 표현한다.

* **Parameters**: 
	* **`doc`** {Object} ADocument 인스턴스 또는 상속 클래스의 인스턴스. Default: 현재 활성화된 인스턴스
	* **`modified`** {Boolean} 수정여부

* **Usage**: 
```js
//mdiMgr는 MDIManager 객체
var doc = mdiMgr.getActiveContainer().getView().getDoc();
mdiMgr.reportModify(doc, true);
mdiMgr.reportModify(null, false);
```

<br/>

### saveDocContainer( filePath )

문서를 저장한다. 문서 템플릿이 없거나 수정사항이 없으면 저장하지 않는다.

* **Parameters**: 
	* **`filePath`** {String} 파일 경로

* **Usage**: 
```js
//mdiMgr는 생성한 객체
var filePaht = "C:\SampleProject\SampleProjectApp.cls";
mdiMgr.saveDocContainer(filePath);
```

<br/>

### saveTabHistory( tabId )

아이디에 해당하는 탭을 히스토리에 저장한다.

* **Parameters**: 
	* **`tabId`** {String} 탭 아이디

* **Usage**: 
```js
//mdiMgr는 생성한 객체
mdiMgr.saveTabHistory('tab01');
```

<br/>

### setTargetContainer( trgContainer )

컨테이너를 지정한다. 컨테이너를 분리하여 각각 tabPanel, docPanel 에 저장한다. tabPanel 에는 ATabBar 인스턴스를 생성하여 넣는다.

* **Parameters**: 
	* **`trgContainer`** {AContainer} 컨테이너 객체

* **Usage**: 
```js
//mdiMgr은 생성한 객체
mdiMgr.setTargetContainer(this.getContainer());
```

<br/>

### setOpenCntrClass()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### setDefaultIcon()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### setIconByExt()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### getIconByExt()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### getDocTemplate()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### newDocContainer()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### findDocContainer()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### landTabContainer()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### floatTabContainer()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
