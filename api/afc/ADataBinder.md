# ADataBinder
> **Extends**: 

바인더들을 등록하고, 등록된 순서대로 동작을 전달하여 관리하는 클래스

<br/>

## Properties


### dataContainer

데이터바인더를 저장할 객체. 보통 동작의 주체를 저장한다.

* **Type**: `Object`
* **Default**: `null`

<br/>

### dataListeners

동작 이벤트를 수신받을 리스너들을 저장하는 배열

* **Type**: `Array`
* **Default**: `[]`

<br/>
<br/>

## Methods

### addDataListener( listener )

동작 이벤트를 수신받을 리스너를 추가한다.

* **Parameters**: 
	* **`listener`** {String} 동작 이벤트를 수신받을 리스너

* **Usage**: 
```js
var binder = new ADataBinder();
binder.addDataListener(this);
```

<br/>

### removeDataListener( listener )

리스너를 제거한다.

* **Parameters**: 
	* **`listener`** {String} 리스너

* **Usage**: 
```js
var binder = new ADataBinder();
binder.addDataListener(this);
binder.removeDataListener(this);
```

<br/>

### reportChange( type, index, data, update, except )

입력 정보들을 리스너들의 onDataChanged(dataContainer, param) 함수를 호출하여 전달한다. 만약 except (동작을 전달하지 않을 리스너) 를 입력한 경우 except를 제외한 리스너들에게 전달한다.<br/>param은 {'type':type, 'index':index, 'data':data, 'update':update} 형태이다.

* **Parameters**: 
	* **`type`** {String or Number} 타입
	* **`index`** {All} 인덱스
	* **`data`** {All} 전달할 데이터
	* **`update`** {All} 업데이트 여부
	* **`except`** {String} 전달하지 않을 리스너

* **Usage**: 
```js
var binder = new ADataBinder();
binder.addDataListener(this);
binder.addDataListener(theApp);
binder.reportChange(ADataBinder.ITEM_SELECT, 0, 'sampleData', true, this);
```

<br/>

### reportChangeTo( type, index, data, update, listeners )

입력 정보들을 특정 리스너들의 onDataChanged(dataContainer, param) 함수를 호출하여 전달한다.<br/>param은 {'type':type, 'index':index, 'data':data, 'update':update} 형태이다.

* **Parameters**: 
	* **`type`** {String} 타입
	* **`index`** {All} 인덱스
	* **`data`** {All} 전달할 데이터
	* **`update`** {All} 업데이트 여부
	* **`listeners`** {String} 전달받을 리스너배열

* **Usage**: 
```js
var binder = new ADataBinder();
binder.addDataListener(this);
binder.addDataListener(theApp);
binder.reportChangeTo(ADataBinder.ITEM_INSERT, 0, 'sampleData', true, [this, theApp]);
```

<br/>

### setDataContainer( dataContainer )

동작의 주체가 되는 객체를 저장한다. 리스너들의 onBindData(dataContainer) 함수를 호출하여 동작의 주체를 전달한다.

* **Parameters**: 
	* **`dataContainer`** {Object} 동작의 주체가 되는 객체

* **Usage**: 
```js
var binder = new ADataBinder();
binder.setDataContainer(this);
```

<br/>

### reportChange()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

<br/>
## Events


### onBindData( dataContainer )

사용자가 setDataContainer 함수를 호출하는 경우, 즉 동작의 주체가 되는 객체를 저장할 때 addDataListener 메서드로 등록한 리스너에 발생한다.

* **Parameters**: 
	* **`dataContainer`** {AContainer} 동작의 주체가 되는 객체

### onDataChanged( dataContainer, param )

사용자가 reportChange, reportChangeTo 함수를 호출하는 경우 addDataListener 메서드로 등록한 리스너에 발생한다. <br/>param은 {'type':type, 'index':index, 'data':data, 'update':update} 형태이다.

* **Parameters**: 
	* **`dataContainer`** {AContainer} 동작의 주체가 되는 객체
	* **`param`** {Object} 동작 정보 객체

<br/>

