# ACheckBox
**Extends**: [`AComponent`](AComponent.html#AComponent)

체크박스와 문자열을 두어 체크하거나 언체크 할 수 있는 컴포넌트

<br/>

## Properties

### checkClass \<String>
체크 시의 스타일 클래스 명

<br/>

### isChecked \<Boolean>
현재 체크가 되어있는지 여부

<br/>

### isSafeClick \<Boolean>
연속클릭 불가능 여부

<br/>

### isTabable \<Boolean>
탭키 이동이 가능한 컴포넌트 여부

<br/>
<br/>

## Instance Methods

### getCheck()

체크여부를 리턴한다.

- **Returns** \<Boolean>

<br/>

### getCheckAlign()

CheckBox컴포넌트에서 체크영역 정렬속성을 리턴한다.

- **Returns** \<String>

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채운다.<br/>dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### getText()

CheckBox의 텍스트를 리턴한다.
- **Returns** \<String>

<br/>

### getValue()

CheckBox에 저장된  데이터값을 리턴한다.

- **Returns** \<String>

<br/>

### init( context, evtListener )

체크박스 컴포넌트를 생성하고 초기화 할 때 호출한다. <br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context 에 매핑된 이벤트 수신자

```js
var chk = new ACheckBox();
chk.init();
```

<br/>

### setCheck( check )

CheckBox의 체크여부를 지정한다.

- `check` \<Boolean> 체크여부

<br/>

### setCheckAlign( align )

CheckBox컴포넌트에서 체크영역의 정렬을 설정한다.

- `align` \<String> left : 왼쪽정렬, right : 오른쪽정렬

<br/>

### setCheckStyle( cBg, ncBg )

CheckBox 스타일에 사용 될 클래스명을 지정한다.

- `cBg` \<String> 체크클래스명
- `ncBg` \<String> 미체크클래스명

```js
chk.setCheckStyle('check','non-check');
```

<br/>

### setData( data )
CheckBox에 저장된 value값과 같은경우 체크한다.

- `data` \<Any> 세팅할 데이터

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 세팅한다. <br/>dataArr은 AQueryData 특정부분의 참조자 이다.<br/><br/>자세한 구조 및 상세설명은 QuerySystem.pptx 참조


- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### setText( text )

CheckBox의 텍스트를 지정한다.

- `text` \<String> 텍스트

<br/>

### setValue( value )

CheckBox에 저장할  데이터값을 세팅한다. 해당 값은 data-check-value속성에 저장된다.

- `value` \<String> 값

<br/>
<br/>

## Events

공통부분은 설명은 \<[AComponent Events](AComponent.html#-Events)> 참조

### click( comp, info, e )

체크박스가 클릭될떄 호출된다.

- `info` \<null> 추가적인 이벤트 정보가 없다.

<br/>

## Attribute

### Data  

- **Text:** 체크박스의 텍스트를 설정하는 속성
- **Align:** 체크박스의 텍스트 정렬을 설정하는 속성
    * **left:** 텍스트를 좌측으로 정렬한다
    * **center:** 텍스트를 중앙으로 정렬한다
    * **right:** 텍스트를 우측으로 정렬한다

- **Check Pos:** 체크박스의 체크 위치를 설정하는 속성
    * **left:** 체크가 텍스트 좌측에 위치한다
    * **right:** 체크가 텍스트 우측에 위치한다
    
- **Value:** 체크박스의 보유값을 설정하는 속성
