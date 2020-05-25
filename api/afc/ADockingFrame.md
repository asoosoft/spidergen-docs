# ADockingFrame( containerid )
> **Extends**: [`AFrameWnd`](./AFrameWnd.md)

* `containerid` \<String> 컨테이너 아이디

ADockingFrame

<br/>

## Class Variables

<br/>

## Instance Variables

### dockedCntr \<[ADockablePanel](./ADockablePanel.md)>

프레임이 도킹된 컨테이너. 도킹될 때 세팅된다.

<br/>

### lastDockedCntr \<[ADockablePanel](./ADockablePanel.md)>

프레임이 마지막으로 도킹되었던 컨테이너. 도킹될 때 세팅된다.

<br/>

### titleHeight \<Number>

타이틀 높이

* `Default` 22

<br/>
<br/>

## Class Methods

### ADockingFrame.getFramePosition( ?frmId )

frmId 에 해당하는 프레임 위치 정보를 가져온다. frmId 가 없으면 지금까지 열려진 프레임들의 모든 프레임 위치 정보를 가져온다.  

* `?frmId` \<String> 프레임 아이디
* **Returns** \<Object> 위치 정보 객체 또는 모든 위치 정보 객체

<br/>

### ADockingFrame.getPosValue( frmId, key )

frmId 에 해당하는 프레임 위치 정보 중 특정 key 에 해당하는 값을 가져온다.

* `frmId` \<String> 프레임 아이디
* `key` \<String> 키
* **Returns** \<All> 위치 정보 중 특정값 

<br/>

### ADockingFrame.readFramePosition( path, defPos )

path 에 해당하는 파일을 읽어 프레임 위치 정보에 저장한다.

* `path` \<String> 위치 정보 저장 경로
* `defPos` \<Object>> 기본 위치 정보

<br/>

### ADockingFrame.setFramePosition( frmId, posInfo )

frmId 에 해당하는 프레임 위치 정보를 저장한다.

* `frmId` \<String> 프레임 아이디
* `posInfo` \<Object>> 위치 정보

<br/>

### ADockingFrame.setPosValue( frmId, key, value )

frmId 에 해당하는 프레임 위치 정보 중 특정 key 에 해당하는 값을 저장한다.

* `frmId` \<String> 프레임 아이디
* `key` \<String> 위치 정보
* `value` \<All> 값

<br/>

### ADockingFrame.writeFramePosition( path )

프레임 위치 정보를 path 에 파일로 저장한다.

* `path` \<String> 위치 정보 저장 경로

<br/>

## Instance Methods

### getPositionInfo()

포지션값들을 리턴한다. 도킹된 상태인 경우 dockedCntrId, dockedIndex 정보를 포함한다.

* **Returns** \<Object>

```js
dockingFrame.getPositionInfo();
//is Docked : {x:0, y:0, width:100, height:100}
```

<br/>

### makeTitle()

도킹프레임 상단부분에 태그를 생성한다. min, max 버튼은 숨김처리.

<br/>

### selectIfDocked()

도킹상태이면 프레임을 선택해준다.

<br/>

### setPositionInfo( obj )

도킹프레임의 위치를 변경한다. 도킹상태로 지정하려면 dockedCntrId, dockedIndex 정보를 위치 정보에 포함한다.

* `obj` \<String> 위치 정보 객체 {x:0, y:0, width:100, height:100}

```js
dockFrame.setPositionInfo({x:100, y:100, width: 200, height:300});
```

<br/>
