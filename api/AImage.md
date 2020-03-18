# AImage
> **Extends**: `AComponent`

이미지 컴포넌트

<br/>

## Methods

### getImage()

이미지 주소를 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = image.getImage();
```

<br/>

### setImage( url )

이미지 주소를 세팅한다.

* **Parameters**: 
	* **`url`** {String} 이미지주소 (src)

* **Usage**: 
```js
image.setImage('../path/temp.png');
```

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### getQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### setQueryData()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>

<br/>
## Events


### load()

이미지 로드시 호출합니다.

### load( comp, info, e )

리소스의 로드가 완료될 때 호출되는 이벤트 함수.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트 객체
	* **`info`** {String} 이미지 경로 주소
	* **`e`** {Object} 이벤트 객체

<br/>

