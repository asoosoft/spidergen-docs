# AButton
**Extends**: [`AComponent`](AComponent.html#AComponent)

버튼 컴포넌트

<br/>

## Properties

### btnStyles \<Array>

버튼의 상태별 스타일 클래스명

```js
//순서대로 over, down, disable의 스타일이다.
btn.btnStyle = ['', '', ''];
```

<br/>

### isTabable \<Boolean>
탭키 이동이 가능한 컴포넌트 여부

```js
btn.isTabable = true;
```

<br/>
<br/>

## Instance Methods

### applyBaseState()

button의 defStyle변수에 저장해둔 기본클래스를 적용한다.<br/>저장해둔 defStyle이 없다면 baseState변수에서 background-color와 border style만 적용한다.

<br/>

### changeBtnState( newState )

Button의 상태를 변경한다.

- `newState` \<String> 변경할 상태값 / AButton.OVER, AButton.DOWN, AButton.DISABLE

```js
btn.changeBtnState(AButton.OVER);
```

<br/>

### clearStateClass()

Button의 상태를 삭제한다.

<br/>

### defaultBtnState()

Button이 Enable이 true일때 버튼의 상태를 초기 화한다. <br/>내부적으로 clearBtnState함수와 applyBaseState함수를 호출한다.

<br/>

### disableState()

button 의 downState함수를 호출해주는 함수이다.

<br/>

### downState()

button의 background-color속성의 보색으로 border를 지정하고 밝기를 줄이는 함수이다.

<br/>

### enable( isEnable )

Button의 활성, 비활성 상태를 세팅한다.

- `isEnable` \<Boolean> 활성화 여부

<br/>

### getCheck()

isCheckBtn인 경우 체크상태를 리턴한다.

- **Returns** \<Boolean>

<br/>

### getHtml()

버튼의 HTML 내용을 리턴한다.

- **Returns** \<String>

<br/>

### getIconMargin()

아이콘 버튼인경우 아이콘에 마진을 주어 위치를 조정한다.

- **Return** \<String> 마진 ex)'10px 10px 10px 0px'

<br/>

### getIconSize()

아이콘 버튼인 경우 아이콘의 사이즈를 리턴한다.

- **Return** \<String>

<br>

### getImage()

Button의 Image src값을 리턴한다.

- **Returns** \<String>

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getText()

버튼의 텍스트 값을 얻어온다.

- **Returns** \<String:>

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var btn = new AButton();
btn.init();
```

<br/>

### overState()

button의 밝기를 늘려주는 함수이다.

<br/>

### saveBaseState()

Button이 초기화될때 호출되는 함수로, data-style 속성을 defStyle변수에 저장해 둔다. 만약 data-style속성에 값이 없다면 baseState변수에 background-color, border style값을 저장해둔다.

<br/>

### setBtnStyle( state, styles )

Button의 상태별 스타일 클래스명을 세팅한다.

- `state` \<String> Button 상태 / AButton.OVER, AButton.DOWN, AButton.DISABLE
- `styles` \<String> 클래스 이름

```js
btn.setBtnStyle(AButton.OVER, 'ClassName');
```

<br/>

### setCheck( check )

isCheckBtn인 경우 체크상태로 변경시킨다.

- `check` 체크 상태 여부

<br/>

### setData( data )

데이터를 세팅한다.

- `data` \<Any> 아무 형식의 데이터

<br/>

### setDefStyle( style )

Button의 기본 스타일을 지정한다.

- `style` \<String> Style object

```js
btn.setDefStyle({width:'80px', height:'22px'});
```

<br/>

### setHtml( text )

Button의 html값을 셋팅한다.

- `text` \<String> html 내용 또는  String

```js
btn.setHtml('<div>test</div>');
```

<br/>

### setIconMargin( value )

아이콘 버튼인경우 아이콘에 마진을 주어 위치를 조정한다.

- `value` \<String> 마진

```js
btn.setIconMargin('10px 10px 10px 0px');
```

<br/>

### setIconSize( value )

아이콘 버튼인 경우 아이콘의 사이즈를 조정한다.

- `value` \<String> 사이즈의 가로, 세로를 띄어쓰기로 구분 한  문자열

```js
btn.setIconSize('auto 10px');
```

<br/>

### setImage( url )

Button의 Image를 세팅한다.

- `url` \<String> 이미지 url

```js
btn.setImage('asset/img/btn.png');
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setText( text )

버튼의 텍스트 값을 셋팅한다.

- `text` \<String> 텍스트


<br/>
<br/>

## Events

공통부분은 설명은 \<[AComponent Events](AComponent.html#events)> 참조

### click

버튼이 클릭되면 발생되는 이벤트

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>

### longtab

버튼을 길게 탭할 경우 발생되는 이벤트

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br>
<br>

## Attribute

### Data

* **Text:** 버튼의 텍스트를 설정하는 속성
* **Align:** 버튼 텍스트의 정렬을 설정하는 속성
    * **left:** 텍스트 좌측 정렬
    * **center:** 텍스트 중앙 정렬
    * **right:** 텍스트 우측 정렬

* **Icon:** : 버튼에 아이콘을 삽입하는 속성
* **After Text:** 삽입된 아이콘이 텍스트 다음에 위치한다.
* **New Line Text:** 삽입된 아이콘과 텍스트를 위아래로 위치 시킨다. Icon After Text 옵션을 이용해서 텍스트와 아이콘의 위 아래 위치를 변경 할 수 있다. 

### Option

* **Fast Click:** 연속으로 클릭이 가능하도록 한다.
* **Tool Button:** 툴버튼으로 세팅한다. default, down, over, disable 4개의 이미지를 버튼 가로크기의 4배로 이어붙여서 버튼의 백그라운드 이미지로 지정하면 자동으로 해당 이벤트 시 이미지가 변경된다.
* **Check Button:** 체크버튼으로 설정한다. setCheck(), getCheck() 함수를 사용할 수 있다.
* **Down State:** 자동으로 버튼 다운 상태의 밝기를 바꿔준다. 체크 해제 시 스타일을 넣지 않으면 버튼 다운상태여도 아무런 변화가 없다.
