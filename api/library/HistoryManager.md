# HistoryManager
> **Extends**: 

히스토리 관리 클래스

<br/>

## Properties


### actData

히스토리 정보를 저장한다. 히스토리 안의 각 정보는 여러개의 정보로 구성될 수 있다.<br/>히스토리 구조 :<br/>[<br/>[ {info: info, undo: undoFunc, redo: redoFunc} ],<br/>[ {info: info, undo: undoFunc, redo: redoFunc}, {info: info, undo: undoFunc, redo: redoFunc} ],<br/>...<br/>]

* **Type**: `Array`
* **Default**: `[]`

<br/>

### offset

히스토리 현재 위치

* **Type**: `Number`
* **Default**: `-1`

<br/>
<br/>

## Methods

### clear()

히스토리를 초기화한다.

* **Usage**: 
```js
var hisMgr = new HistoryManager();
hisMgr.clear();
```

<br/>

### getCurrentHistory()

현재 히스토리를 반환한다.(정보, 실행취소 함수, 다시실행 함수 객체정보를 항목으로 가진 배열)

* **Returns**: Array

* **Usage**: 
```js
var hisMgr = new HistoryManager();
var curHis = hisMgr.getCurrentHistory();
```

<br/>

### getCurrentOffset()

현재 히스토리의 위치값을 반환한다.

* **Returns**: Number

* **Usage**: 
```js
var hisMgr = new HistoryManager();
var curOfs = hisMgr.getCurrentOffset();
```

<br/>

### getPosHistory( pos )

특정 위치의 히스토리 정보를 반환한다.(정보, 실행취소 함수, 다시실행 함수 객체정보를 항목으로 가진 배열)

* **Returns**: Array

* **Parameters**: 
	* **`pos`** {String} 위치값

* **Usage**: 
```js
var hisMgr = new HistoryManager();
var his = hisMgr.getPosHistory(10);
```

<br/>

### redo()

히스토리 현재 위치를 다시실행 위치(현재위치+1)로 변경하고, 다시실행 가능여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var hisMgr = new HistoryManager();
if(!hisMgr.redo()) return; //redo 불가능
var hisArr = this.history.getCurrentHistory();
for(var i=0; i&lt;hisArr.length; i++) { history.redo(hisArr[i].info); }
```

<br/>

### reg( info, undoFunc, redoFunc )

히스토리를 등록한다. 히스토리 병합(info.merge) 정보가 있으면 마지막 히스토리 정보와 함께 등록된다.

* **Parameters**: 
	* **`info`** {String} 히스토리 정보
	* **`undoFunc`** {Function} 실행 취소 함수
	* **`redoFunc`** {String} 다시 실행 함수

* **Usage**: 
```js
var hisMgr = new HistoryManager();
var info = { undoData: '언두', redoData: '리두'};
hisMgr.reg(info, function(info) {
　alert(info.undoData); // undo 처리 
},
function(info) {
　alert(info.redoData);    // redo 처리
});
```

<br/>

### undo()

히스토리 현재 위치를 실행취소 위치(현재위치-1)로 변경하고, 실행취소 가능여부를 반환한다.

* **Returns**: Boolean

* **Usage**: 
```js
var hisMgr = new HistoryManager();
if(hisMgr.getCurrentOffset() < 0) return; // undo 불가
var hisArr = hisMgr.getCurrentHistory(); // curHis에 있는 정보로 undo 처리
for(var i=0; i&lt;hisArr.length; i++) { history.undo(hisArr[i].info); }
hisMgr.undo(); // undo 처리 후 반드시 호출
```

<br/>
<br/>
