# AImage
**Extends**: [`AComponent`](AComponent.html#AComponent)

이미지 컴포넌트

<br/>

## Instance Variables

<br/>
<br/>

## Instance Methods

### getImage()

이미지 주소를 리턴한다.

- **Returns** \<String>

<br/>

### setBtnStyle( state, styles )

Button의 상태별 스타일 클래스명을 세팅한다.

- `state` \<String> Button 상태 / AButton.OVER, AButton.DOWN, AButton.DISABLE
- `styles` \<String> 클래스 이름

```js
btn.setBtnStyle(AButton.OVER, 'ClassName');
```

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

- `comp` \<[AComponent](AComponent.html#AComponent)> 컴포넌트 객체
- `info` \<String> 이미지 경로 주소
- `e` \<Object> 이벤트 객체

<br/>
<br/>

## Attribute

### Data  

- `Src` 이미지의 프로젝트내 위치 경로를 설정하는 속성입니다. 
- `Alt` 이미지의 대체 텍스트를 설정하는 속성입니다. 

<br/>