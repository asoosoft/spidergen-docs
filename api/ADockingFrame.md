# ADockingFrame
> **Extends**: `AFrameWnd`

ADockingFrame

<br/>

## Properties


### dockedCntr



* **Type**: ``
* **Default**: ``

<br/>

### lastDockedCntr



* **Type**: ``
* **Default**: ``

<br/>

### titleHeight



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### close( result )

도킹프레임을 닫는 함수이다. 내부적으로 프레임이 언도킹된 후에 닫힌다.

* **Parameters**: 
	* **`result`** {String} 결과값 반환

* **Usage**: 
```js
dockingFrame.close();
```

<br/>

### ADockingFrame.getFramePosition( frmId )

getFramePosition

* **Parameters**: 
	* **`frmId`** {String} frmId

<br/>

### getPositionInfo()

포지션값들을 리턴한다.

* **Returns**: Object

* **Usage**: 
```js
dockingFrame.getPositionInfo();
```

<br/>

### ADockingFrame.getPosValue( frmId, key )

getPosValue

* **Parameters**: 
	* **`frmId`** {String} frmId
	* **`key`** {String} key

<br/>

### init( context )

컨테이너를 생성하고 초기화 할 때 호출한다. 내부적으론 view 가 그 기능을 대신하므로 this.view 의 init 함수를 호출한다.

* **Parameters**: 
	* **`context`** {String} 컨테이너 생성 및 초기화 정보

<br/>

### makeTitle()

도킹프레임 상단부분의 태그를 생성한다.

<br/>

### onCreateDone()

생성이 완료되면 호출되는 함수이다.

<br/>

### open( viewUrl, parent, left, top, width, height )

도킹프레임을 오픈하는 함수이다.

* **Parameters**: 
	* **`viewUrl`** {String} 로드될 view의 url
	* **`parent`** {AWindow} 부모 컨테이너
	* **`left`** {Number} left
	* **`top`** {Number} top
	* **`width`** {Number} width
	* **`height`** {String} height

* **Usage**: 
```js
var dockingFrame = new ADockingFrame();
dockingFrame.open('view/dock.lay', null, 0,0, 300, 500);
```

<br/>

### ADockingFrame.readFramePosition( path, defPos )

readFramePosition

* **Parameters**: 
	* **`path`** {String} path
	* **`defPos`** {String} defPos

<br/>

### selectIfDocked()

도킹프레임을 선택해준다.

<br/>

### ADockingFrame.setFramePosition( frmId, posInfo )

setFramePosition

* **Parameters**: 
	* **`frmId`** {String} frmId
	* **`posInfo`** {String} posInfo

<br/>

### setPositionInfo( obj )

도킹프레임의 위치를 변경한다.

* **Parameters**: 
	* **`obj`** {String} 포지션 객체

* **Usage**: 
```js
dockFrame.setPositionInfo({x:100, y:100, width: 200, height:300});
```

<br/>

### ADockingFrame.setPosValue( frmId, key, value )

setPosValue

* **Parameters**: 
	* **`frmId`** {String} frmId
	* **`key`** {String} key
	* **`value`** {String} value

<br/>

### ADockingFrame.writeFramePosition( path )

writeFramePosition

* **Parameters**: 
	* **`path`** {String} path

<br/>


### onMinBtnClick()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### hide()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>
