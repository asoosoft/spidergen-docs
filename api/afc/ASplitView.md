# ASplitView
**Extends**: [`AComponent`](AComponent.html#AComponent)

ASplitView 는 컨테이너처럼 스플릿 기능을 갖는다.<br/>
createSplit 호출 시 비어있는 item 을 생성해 준다.<br/>
이후 분할된 곳에 setSplitView 함수를 호출하여 뷰를 셋팅 또는 로드한다.

<br/>

## Class Variables

### ASplitter.BAR_COLOR \<String>

분할 프레임 사이의 스플릿바 색상

* `Default` `#bbb`

## Instance Variables

### splitter
splitter의 Instance Variables 참조

<br/>
<br/>

## Instance Methods

### appendSplit( splitSize )

분할 아이템을 마지막에 추가한다.

- `splitSize` \<Number> 아이템의 크기

<br/>

### callSubActiveEvent( funcName, isFirst )

컨테이너에 스플리터가 있다면 각각의 액티브, 디액티브 함수를 실행시킵니다. <br/>
('onWillActive' / 'onActive' / 'onActiveDone' / 'onWillDeactive' / 'onDeactive' / 'onDeactiveDone')

- `funcName` \<String> 액티브, 디액티브 함수명
- `isFirst` \<Boolean> 처음 실행 여부

<br/>

### createSplit( count, sizeArr, splitDir, barSize )

내부에 분할 아이템을 생성한다.

- `count` \<Number> 아이템의 갯수
- `sizeArr` \<Array> 사이즈 배열 (-1일 경우 자동)
- `splitDir` \<String> 분리 방향 (row:좌우, column:상하)
- `barSize` \<Number> 분할 바의 사이즈

```js
this.splitView.createSplit(2, [100, -1], 'column', 5);
```

<br/>

### destroySplit()

분할 된 뷰들의 자원을 해제한다.


<br/>

### getSplit( inx )

특정 위치의 분할 아이템을 반환한다.

* `inx` \<Number> 스플릿 위치
* **Returns** \<HTMLElement> 프레임 엘리먼트

<br/>

### getSplitBar( inx )

특정 위치의 스플릿바를 가져온다.

- `inx` \<Number> 위치
- **Returns** \<HTMLElement> 스플릿바 엘리먼트

<br/>

### getSplitView( inx )

특정 위치의 분할 아이템 내부의 뷰를 반환한다.
 
- `inx` \<Number> 아이템 인덱스

<br/>

### includeChildView()

부모 뷰에 자식 뷰로 설정한다.

<br/>

### insertSplit( inx, splitSize, isAfter )

분할 아이템을 설정한 위치에 추가한다.

* `inx` \<Number> 삽입할 아이템의 인덱스
* `splitSize` \<Number> 분할 아이템의 크기
* `isAfter` \<Boolean>> 앞인지 뒤인지 여부

```js
this.splitView.insertSplit(0, 100, true);
```

<br/>

### onSplitChanged( splitFrame )

분할 뷰에 리사이즈 이벤트를 통보한다.

- `splitFrame` \<String> 분할 프레임

<br/>

### prependSplit( splitSize )

분할 아이템을 맨앞에 추가한다.

- `splitSize` \<Number> 아이템의 크기

```js
this.splitView.prependSplit(100);
```

<br/>

### removeFromView()

부모 뷰로부터 자신을 제거한다.

<br/>

### removeSplit( inx )

분할 아이템을 삭제한다.

- `inx` \<Number> 아이템의 인덱스

<br/>

### setSplitView( inx, view )

매개변수 inx 에 해당하는 아이템에 뷰를 설정한다.<br/>
매개변수 view는 문자열일 경우 해당하는 뷰를 생성한다.

- `inx` \<Number> 인덱스
- `view` \<AView> 설정 할 뷰
- **Returns** \<AView>

```js
var view = this.splitView.setSplitView(0, 'Source/t1.lay');
console.log(view);
```

<br/>

### updatePosition( pWidth, pHeight )

컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출합니다.
 
- `pWidth` \<String> pWidth
- `pHeight` \<String> pHeight

<br/>