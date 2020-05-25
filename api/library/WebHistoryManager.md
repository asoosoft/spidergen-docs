# WebHistoryManager
> **Extends**

웹 히스토리를 등록, 관리한다.

<br/>

## Class Variables

<br/>

## Instance Variables

### targets \<Object>

히스토리 이동 처리할 컴포넌트를 특정 키에 저장하는 객체

<br/>
<br/>

## Class Methods

<br/>
<br/>

## Instance Methods

### init()

히스토리 이벤트를 등록하는 등 웹 히스토리 매니저를 초기화한다.

```js
var whm = new WebHistoryManager();
whm.init();
```

<br/>

### setHistoryTarget( key, target )

히스토리 이동을 처리할 컴포넌트를 특정 키로 등록한다.

* `key` \<String> 키
* `target` \<[ATabView](./../afc/ATabView.md) | [ANavigator](../afc/ANavigator.md) | [AWindow](../afc/AWindow.md)> 컴포넌트 객체

```js
var whm = new WebHistoryManager();
whm.init();
whm.setHistoryTarget('tabview', this.tabView);
whm.pushHistory({target:'tabview', data1: 'data1' }; //...
```

<br/>

### pushHistory( data, title )

히스토리를 등록한다. 데이터에는 히스토리 이동을 처리할 target 으로 [setHistoryTarget](#sethistorytarget-key-target) 함수를 호출하여 세팅한 컴포넌트에 대한 키값을 반드시 지정해야 한다. 

* `data` \<Object> 히스토리 정보 객체 { target: 히스토리 이동처리 컴포넌트 객체키 }
* `title` \<String> 상태에 대한 짧은 제목

<br/>

### popHistory()

히스토리 뒤로가기를 수행한다.

<br/>