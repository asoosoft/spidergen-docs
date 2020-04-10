# AFlexView
> **Extends**: `AComponent`

AFlexView

<br/>

## Properties


### views



* **Type**: ``
* **Default**: ``

<br/>


### viewDirection



* **Type**: ``
* **Default**: ``

<br/>
<br/>


## Methods

### getView( index )

해당 인덱스에 대응하는 뷰를 반환합니다.

* **Returns**: AView

* **Parameters**: 
	* **`index`** {Number} 인덱스

<br/>

### insertView( view, index )

뷰를 추가합니다.

* **Parameters**: 
	* **`view`** {AView} 뷰
	* **`index`** {Number} 추가할 뷰의 기준 인덱스

<br/>

### removeAllViews()

뷰를 모두 삭제합니다.

<br/>

### removeFromView( onlyRelease )

부모뷰로 부터 플렉스뷰를 삭제합니다. onlyRelease는 내부적으로만 사용하므로 일반적으로 생략합니다.

* **Parameters**: 
	* **`onlyRelease`** {String} true일 경우 실제로 컴포넌트를 제거하지 않고 연관된 자원만 해제합니다.

<br/>

### setViewDirection( direction )

정렬방향을 설정합니다.

* **Parameters**: 
	* **`direction`** {String} row : 행, column : 열

<br/>

### updatePosition( pWidth, pHeight )

컴포넌트의 위치나 사이즈가 갱신되어져야 할 경우 호출합니다. 브라우저의 사이즈가 변경될 경우 자동으로 호출됩니다.

* **Parameters**: 
	* **`pWidth`** {Number} 부모뷰의 넓이
	* **`pHeight`** {Number} 부모뷰의 높이

<br/>

### init()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>


### callSubActiveEvent()



* **Parameters**: 

* **Usage**: 
```js

```

<br/>
<br/>
