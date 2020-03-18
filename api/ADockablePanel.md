# ADockablePanel
> **Extends**: 

ADockablePanel

<br/>

## Properties


### dockDir



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### activeFrame( frame )

해당 frame을 활성화 한다.

* **Parameters**: 
	* **`frame`** {String} frame

* **Usage**: 
```js
//frame은 ADockingFrame객체이다.
dockablePanel.activeFrame();
```

<br/>

### dockFrame( frame, inx, pos, dockSize )

frame을 도킹한다.

* **Parameters**: 
	* **`frame`** {String} frame
	* **`inx`** {Number} index
	* **`pos`** {Object} 도킹 되는 위치 / -1:insert before, 0:assign, 1:insert after
	* **`dockSize`** {String} 도킹 사이즈 / pos가 0일경우 기존자리에 추가되므로 입력할 필요가 없음

* **Usage**: 
```js
//frame은 ADockingFrame객체이다.
dockablePanel.dockFrame(frame, 1, 1);
```

<br/>

### init( context )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보

* **Usage**: 
```js
var dockablePanel = new ADockablePanel();
dockablePanel.init();
```

<br/>

### setDockDirection( dir )

도킹패널의 분할방향을 설정한다.

* **Parameters**: 
	* **`dir`** {String} 컨테이너 분할 방향

* **Usage**: 
```js
dockablePanel.setDockDirection('row');   //열
dockablePanel.setDockDirection('column');  //행
```

<br/>

### undockFrame( frame, x, y, w, h )

Frame의 도킹을 해제한다.

* **Parameters**: 
	* **`frame`** {String} frame
	* **`x`** {Number} 도킹을 해제하고 나서 left값
	* **`y`** {Number} 도킹을 해제하고 나서 top값
	* **`w`** {Number} 도킹을 해제하고 나서 width값
	* **`h`** {String} 도킹을 해제하고 나서 height값

* **Usage**: 
```js
//frame은 ADockingFrame객체이다.
//포지션값은 %와 px를 생략하고 입력해야한다.
dockablePanel.undockFrame(frame, 100, 200, 500, 500);
```

<br/>

### setDelegator()



* **Parameters**: 

* **Usage**: 
```js

```


### activeFrameByIndex()



* **Parameters**: 

* **Usage**: 
```js

```
