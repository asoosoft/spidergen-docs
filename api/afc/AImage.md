# AImage
**Extends**: `AComponent`

이미지 컴포넌트

<br/>

## Instance Methods

### getImage()

이미지 주소를 리턴한다.

- **Returns** \<String>

```js
var result = image.getImage();
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr의 정보에 따라 dataArr에 채운다.<br/>
dataArr은 AQueryData 특정부분의 참조자다.<br/><br/>
자세한 구조 및 상세설명은 QuerySystem.pptx 참조

- `dataArr` \<Array> [ {key1:value, key2:value ...}, {}, ... ]
- `keyArr` \<Array> [ key1, key3, key10 ]
- `queryData` \<AQueryData> AQueryData의 전체 값, 필요시 참조

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>
동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

- `context` \<String> 컴포넌트 생성 및 초기화 정보
- `evtListener` \<String> context에 매핑된 이벤트 수신자

```js
var image = new AButton();
image.init();
```

<br/>

### setBtnStyle( state, styles )

Button의 상태별 스타일 클래스명을 세팅한다.

- `state` \<String> Button 상태 / AButton.OVER, AButton.DOWN, AButton.DISABLE
- `styles` \<String> 클래스 이름

```js
btn.setBtnStyle(AButton.OVER, 'ClassName');
```

<br/>

### setData( data )

데이터를 세팅한다.

- `data` \<Any> 아무 형식의 데이터

<br/>

### setImage( url )

이미지 주소를 세팅한다.

- `url` \<String> 이미지주소 (src)

```js
image.setImage('../path/temp.png');
```

<br/>
<br/>

## Events

### load()

이미지 로드시 호출합니다.

<br/>

### load( comp, info, e )

리소스의 로드가 완료될 때 호출되는 이벤트 함수.

- `comp` \<AComponent> 컴포넌트 객체
- `info` \<String> 이미지 경로 주소
- `e` \<Object> 이벤트 객체

<br/>
<br/>

## Attribute

### Data  

* **Src:** 이미지의 프로젝트내 위치 경로를 설정하는 속성입니다. 
* **Alt:** 이미지의 대체 텍스트를 설정하는 속성입니다. 

<br/>

