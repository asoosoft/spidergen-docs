<<<<<<< HEAD
# BackupManager
> **Extends**: 

특정 element의 내부에 표현될 항목의 최대 개수와 복원 개수를 지정하여 항목을 무한히 추가하지 않고 관리하는 클래스

<br/>

## Properties


### $contentEle

항목이 추가되고 제거되는 jQuery 객체이다.

* **Type**: `jQuery Object`
* **Default**: `null`

<br/>

### backupScroll

복원할 스크롤 위치값. 항목들을 복원, 백업할 때 스크롤 위치를 변경하기 위해 사용한다.

* **Type**: `Number`
* **Default**: `0`

<br/>

### delegator

BackupManager를 사용하는 객체를 저장한다. 객체에는 반드시 getTopItem, getBottomItem, getTotalCount 메서드가 있어야 한다.

* **Type**: `Object`
* **Default**: `null`

<br/>

### headStack

윗부분의 엘리먼트들을 저장하고 있을 보이지 않는 div jQuery 객체

* **Type**: `jQuery Object`
* **Default**: `null`

<br/>

### itemContentCnt

한번에 추가되는 항목의 로우 개수. 항목이 1개의 로우가 아닌 2개 이상의 로우로 구성될 수 있기 때문에  저장한다.

* **Type**: `Number`
* **Default**: `0`

<br/>

### itemHeight

하나의 항목의 높이를 지정한다.

* **Type**: `Number`
* **Default**: `0`

<br/>

### maxRow

내부 항목들이 화면에 보여질 최대 개수를 지정한다.

* **Type**: `Number`
* **Default**: `50`

<br/>

### restoreCount

내부 항목들이 한번에 복원될 개수를 지정한다.

* **Type**: `Number`
* **Default**: `20`

<br/>

### scrollEle

스크롤이 발생하는 엘리먼트. 항목들이 복원 될때 스크롤 위치를 변경해야 할 수도 있기 때문에 저장한다.

* **Type**: `HTML Object`
* **Default**: `null`

<br/>

### tailStack

아래부분의 엘리먼트들을 저장하고 있을 보이지 않는 div jQuery 객체

* **Type**: `jQuery Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### appendItemManage( items, isApplyBackupScroll )

항목을 append 한다. 백업을 해야하는 경우와 아닌 경우를 판단하여 처리한다. 백업이 되었으면 true, 안되었으면 false를 반환한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`items`** {jQuery Object} 추가할 항목들
	* **`isApplyBackupScroll`** {Boolean} 백업 스크롤 적용 여부

<br/>

### applyBackupScroll()

복원 스크롤 위치값을 실제 스크롤 위치에 반영한다.(복원 스크롤 위치값을 기존 스크롤 값에 더한다.)

* **Returns**: Number

<br/>

### backupHead( row )

항목을 headStack 에 append 한다.

* **Parameters**: 
	* **`row`** {jQuery Object} 추가할 항목

<br/>

### backupHeadPre( row )

항목을 headStack 에 prepend 한다.

* **Parameters**: 
	* **`row`** {jQuery Object} 추가할 항목

<br/>

### backupTail( row )

항목을 tailStack 에 append 한다.

* **Parameters**: 
	* **`row`** {jQuery Object} 추가할 항목

<br/>

### backupTailPre( row )

항목을 tailStack 에 prepend 한다.

* **Parameters**: 
	* **`row`** {jQuery Object} 추가할 항목

<br/>

### checkHeadBackup()

head 쪽에 복원할 항목이 있는 경우 복원한다. 복원한 양 만큼 tail 쪽에 백업하고 스크롤 위치를 변경한다.

* **Returns**: Boolean

<br/>

### checkTailBackup()

tail 쪽에 복원할 항목이 있는 경우 복원한다. 복원한 양 만큼 head 쪽에 백업하고 스크롤 위치를 변경한다.

* **Returns**: Boolean

<br/>

### clearAll()

headStack과 tailStack에 저장된 백업항목들을 제거한다.

<br/>

### clearHead()

headStack 에 저장된 항목들을 제거한다.

<br/>

### clearTail()

tailStack 에 저장된 항목들을 제거한다.

<br/>

### create( delegator, maxRow, restoreCount )

복원, 백업을 하기 위한 정보들을 지정한다. 가장 먼저 호출해야 한다. headStack과 tailStack을 생성하며, 파라미터로 넘어온 정보들을 저장한다.

* **Parameters**: 
	* **`delegator`** {Object} BackupManager를 사용하는 객체
	* **`maxRow`** {Number} 표현될 항목의 최대 개수
	* **`restoreCount`** {Number} 복원할 항목의 개수

<br/>

### destroy()

headStack과 tailStack을 제거한다.

<br/>

### getHeadCount()

headStack 안에 있는 항목의 개수를 반환한다.

* **Returns**: Number

<br/>

### getHRestoreCount()

headStack 안에 있는 항목의 개수와 한번에 복원할 개수 중 작은 값을 반환한다.

* **Returns**: Number

<br/>

### getTailCount()

tailStack 안에 있는 항목의 개수를 반환한다.

* **Returns**: Number

<br/>

### getTRestoreCount()

tailStack 안에 있는 항목의 개수와 한번에 복원할 개수 중 작은 값을 반환한다.

* **Returns**: Number

<br/>

### minusBackupScroll( count )

복원 스크롤 위치값을 추가될 항목들의 총 높이만큼 뺀다.

* **Parameters**: 
	* **`count`** {Number} 개수

<br/>

### plusBackupScroll( count )

복원 스크롤 위치값을 추가될 항목들의 총 높이만큼 더한다.

* **Parameters**: 
	* **`count`** {Number} 개수

<br/>

### prependItemManage( items )

항목을 prepend 한다. 백업을 해야하는 경우와 아닌 경우를 판단하여 처리한다. 백업이 되었으면 true, 안되었으면 false를 반환한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`items`** {jQuery Object} 추가할 항목들

<br/>

### restoreHead()

headStack 에서 마지막 항목을 뽑아서 반환한다.

* **Returns**: jQuery Object

<br/>

### restoreTail()

tailStack 에서 마지막 항목을 뽑아서 반환한다.

* **Returns**: jQuery Object

<br/>

### setBackupInfo( itemHeight, itemContentCnt, scrollEle, $contentEle )

백업정보를 지정한다.

* **Parameters**: 
	* **`itemHeight`** {Number} 항목 높이
	* **`itemContentCnt`** {Number} 한번에 추가되는 항목의 로우 개수
	* **`scrollEle`** {HTML Object} 스크롤이 발생하는 엘리먼트
	* **`$contentEle`** {jQuery Object} 항목이 추가되고 제거되는 jQuery 객체

<br/>

### setItemHeight( itemHeight )

항목의 높이를 지정한다.

* **Parameters**: 
	* **`itemHeight`** {Number} 항목 높이

<br/>

### isMoveReal()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setMoveReal()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
=======
# BackupManager
> **Extends**: 

특정 element의 내부에 표현될 항목의 최대 개수와 복원 개수를 지정하여 항목을 무한히 추가하지 않고 관리하는 클래스

<br/>

## Properties


### $contentEle

항목이 추가되고 제거되는 jQuery 객체이다.

* **Type**: `jQuery Object`
* **Default**: `null`

<br/>

### backupScroll

복원할 스크롤 위치값. 항목들을 복원, 백업할 때 스크롤 위치를 변경하기 위해 사용한다.

* **Type**: `Number`
* **Default**: `0`

<br/>

### delegator

BackupManager를 사용하는 객체를 저장한다. 객체에는 반드시 getTopItem, getBottomItem, getTotalCount 메서드가 있어야 한다.

* **Type**: `Object`
* **Default**: `null`

<br/>

### headStack

윗부분의 엘리먼트들을 저장하고 있을 보이지 않는 div jQuery 객체

* **Type**: `jQuery Object`
* **Default**: `null`

<br/>

### itemContentCnt

한번에 추가되는 항목의 로우 개수. 항목이 1개의 로우가 아닌 2개 이상의 로우로 구성될 수 있기 때문에  저장한다.

* **Type**: `Number`
* **Default**: `0`

<br/>

### itemHeight

하나의 항목의 높이를 지정한다.

* **Type**: `Number`
* **Default**: `0`

<br/>

### maxRow

내부 항목들이 화면에 보여질 최대 개수를 지정한다.

* **Type**: `Number`
* **Default**: `50`

<br/>

### restoreCount

내부 항목들이 한번에 복원될 개수를 지정한다.

* **Type**: `Number`
* **Default**: `20`

<br/>

### scrollEle

스크롤이 발생하는 엘리먼트. 항목들이 복원 될때 스크롤 위치를 변경해야 할 수도 있기 때문에 저장한다.

* **Type**: `HTML Object`
* **Default**: `null`

<br/>

### tailStack

아래부분의 엘리먼트들을 저장하고 있을 보이지 않는 div jQuery 객체

* **Type**: `jQuery Object`
* **Default**: `null`

<br/>
<br/>

## Methods

### appendItemManage( items, isApplyBackupScroll )

항목을 append 한다. 백업을 해야하는 경우와 아닌 경우를 판단하여 처리한다. 백업이 되었으면 true, 안되었으면 false를 반환한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`items`** {jQuery Object} 추가할 항목들
	* **`isApplyBackupScroll`** {Boolean} 백업 스크롤 적용 여부

<br/>

### applyBackupScroll()

복원 스크롤 위치값을 실제 스크롤 위치에 반영한다.(복원 스크롤 위치값을 기존 스크롤 값에 더한다.)

* **Returns**: Number

<br/>

### backupHead( row )

항목을 headStack 에 append 한다.

* **Parameters**: 
	* **`row`** {jQuery Object} 추가할 항목

<br/>

### backupHeadPre( row )

항목을 headStack 에 prepend 한다.

* **Parameters**: 
	* **`row`** {jQuery Object} 추가할 항목

<br/>

### backupTail( row )

항목을 tailStack 에 append 한다.

* **Parameters**: 
	* **`row`** {jQuery Object} 추가할 항목

<br/>

### backupTailPre( row )

항목을 tailStack 에 prepend 한다.

* **Parameters**: 
	* **`row`** {jQuery Object} 추가할 항목

<br/>

### checkHeadBackup()

head 쪽에 복원할 항목이 있는 경우 복원한다. 복원한 양 만큼 tail 쪽에 백업하고 스크롤 위치를 변경한다.

* **Returns**: Boolean

<br/>

### checkTailBackup()

tail 쪽에 복원할 항목이 있는 경우 복원한다. 복원한 양 만큼 head 쪽에 백업하고 스크롤 위치를 변경한다.

* **Returns**: Boolean

<br/>

### clearAll()

headStack과 tailStack에 저장된 백업항목들을 제거한다.

<br/>

### clearHead()

headStack 에 저장된 항목들을 제거한다.

<br/>

### clearTail()

tailStack 에 저장된 항목들을 제거한다.

<br/>

### create( delegator, maxRow, restoreCount )

복원, 백업을 하기 위한 정보들을 지정한다. 가장 먼저 호출해야 한다. headStack과 tailStack을 생성하며, 파라미터로 넘어온 정보들을 저장한다.

* **Parameters**: 
	* **`delegator`** {Object} BackupManager를 사용하는 객체
	* **`maxRow`** {Number} 표현될 항목의 최대 개수
	* **`restoreCount`** {Number} 복원할 항목의 개수

<br/>

### destroy()

headStack과 tailStack을 제거한다.

<br/>

### getHeadCount()

headStack 안에 있는 항목의 개수를 반환한다.

* **Returns**: Number

<br/>

### getHRestoreCount()

headStack 안에 있는 항목의 개수와 한번에 복원할 개수 중 작은 값을 반환한다.

* **Returns**: Number

<br/>

### getTailCount()

tailStack 안에 있는 항목의 개수를 반환한다.

* **Returns**: Number

<br/>

### getTRestoreCount()

tailStack 안에 있는 항목의 개수와 한번에 복원할 개수 중 작은 값을 반환한다.

* **Returns**: Number

<br/>

### minusBackupScroll( count )

복원 스크롤 위치값을 추가될 항목들의 총 높이만큼 뺀다.

* **Parameters**: 
	* **`count`** {Number} 개수

<br/>

### plusBackupScroll( count )

복원 스크롤 위치값을 추가될 항목들의 총 높이만큼 더한다.

* **Parameters**: 
	* **`count`** {Number} 개수

<br/>

### prependItemManage( items )

항목을 prepend 한다. 백업을 해야하는 경우와 아닌 경우를 판단하여 처리한다. 백업이 되었으면 true, 안되었으면 false를 반환한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`items`** {jQuery Object} 추가할 항목들

<br/>

### restoreHead()

headStack 에서 마지막 항목을 뽑아서 반환한다.

* **Returns**: jQuery Object

<br/>

### restoreTail()

tailStack 에서 마지막 항목을 뽑아서 반환한다.

* **Returns**: jQuery Object

<br/>

### setBackupInfo( itemHeight, itemContentCnt, scrollEle, $contentEle )

백업정보를 지정한다.

* **Parameters**: 
	* **`itemHeight`** {Number} 항목 높이
	* **`itemContentCnt`** {Number} 한번에 추가되는 항목의 로우 개수
	* **`scrollEle`** {HTML Object} 스크롤이 발생하는 엘리먼트
	* **`$contentEle`** {jQuery Object} 항목이 추가되고 제거되는 jQuery 객체

<br/>

### setItemHeight( itemHeight )

항목의 높이를 지정한다.

* **Parameters**: 
	* **`itemHeight`** {Number} 항목 높이

<br/>

### isMoveReal()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setMoveReal()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
>>>>>>> bc729ae47e04917eefd0eaed80c7b915b82b4564
