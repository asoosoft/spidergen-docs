# AButton
> **Extends**: `AComponent`

버튼 컴포넌트

<br/>

## Properties

### btnStyles

버튼의 상태별 스타일 클래스명

* **Type**: `Array`
* **Default**: `null`

<br/>

### isTabable



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### applyBaseState()

button의 defStyle변수에 저장해둔 기본클래스를 적용한다.<br/>저장해둔 defStyle이 없다면 baseState변수에서 background-color와 border style만 적용한다.

* **Usage**: 
```js
btn.applyBaseState();
```

<br/>

### changeBtnState( newState )

Button의 상태를 변경한다.

* **Parameters**: 
	* **`newState`** {String} 변경할 상태값 / AButton.OVER, AButton.DOWN, AButton.DISABLE

* **Usage**: 
```js
btn.changeBtnState(AButton.OVER);
```

<br/>

### clearStateClass()

Button의 상태를 삭제한다.

* **Usage**: 
```js
btn.clearStateClass();
```

<br/>

### defaultBtnState()

Button이 Enable이 true일때 버튼의 상태를 초기 화한다. <br/>내부적으로 clearBtnState함수와 applyBaseState함수를 호출한다.

* **Usage**: 
```js
btn,defaultBtnState();
```

<br/>

### disableState()

button 의 downState함수를 호출해주는 함수이다.

* **Usage**: 
```js
btn.disableState();
```

<br/>

### downState()

button의 background-color속성의 보색으로 border를 지정하고 밝기를 줄이는 함수이다.

* **Usage**: 
```js
btn.downState();
```

<br/>

### enable( isEnable )

Button의 활성, 비활성 상태를 세팅한다.

* **Parameters**: 
	* **`isEnable`** {Boolean} 활성화 여부

* **Usage**: 
```js
btn.enable(true);
```

<br/>

### getHtml()

버튼의 HTML 내용을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
var result = btn.getHtml();
```

<br/>

### getImage()

Button의 Image src값을 리턴한다.

* **Returns**: String

* **Usage**: 
```js
btn.getImage();
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채웁니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### getText()

버튼의 텍스트 값을 얻어온다.

* **Returns**: String:

* **Usage**: 
```js
var result = btn.getText();
```

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.<br/>동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** {String} 컴포넌트 생성 및 초기화 정보
	* **`evtListener`** {String} context 에 매핑된 이벤트 수신자

* **Usage**: 
```js
var btn = new AButton();
btn.init();
```

<br/>

### overState()

button의 밝기를 늘려주는 함수이다.

* **Usage**: 
```js
btn.overState();
```

<br/>

### saveBaseState()

Button이 초기화될때 호출되는 함수로, data-style 속성을 defStyle변수에 저장해 둔다. 만약 data-style속성에 값이 없다면 baseState변수에 background-color, border style값을 저장해둔다.

* **Usage**: 
```js
btn.saveBaseState();
```

<br/>

### setBtnStyle( state, styles )

Button의 상태별 스타일 클래스명을 세팅한다.

* **Parameters**: 
	* **`state`** {String} Button 상태 / AButton.OVER, AButton.DOWN, AButton.DISABLE
	* **`styles`** {String} 클래스 이름

* **Usage**: 
```js
btn.setBtnStyle(AButton.OVER, 'ClassName');
```

<br/>

### setDefStyle( style )

Button의 기본 스타일을 지정한다.

* **Parameters**: 
	* **`style`** {String} Style object

* **Usage**: 
```js
btn.setDefStyle({width:'80px', height:'22px'});
```

<br/>

### setHtml( text )

Button의 html값을 셋팅한다...

* **Parameters**: 
	* **`text`** {String} html 내용 또는  String입니다.

* **Usage**: 
```js
btn.setHtml('<div>test</div>');
```

<br/>

### setImage( url )

Button의 Image를 세팅한다.

* **Parameters**: 
	* **`url`** {String} 이미지 url

* **Usage**: 
```js
btn.setImage('asset/img/btn.png');
```

<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### setText( text )

버튼의 텍스트 값을 셋팅한다.

* **Parameters**: 
	* **`text`** {String} value

* **Usage**: 
```js
var value= 'Hello';
btn.setText(value);
```

<br/>

### beforeInit()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>

### setCheck()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>

### getCheck()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>

### getLastBgColor()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>

### _changeBgLightness()



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

### setIconMargin()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>

### setIconSize()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>

### getIconSize()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>

### _getDataStyleObj()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>

### _setDataStyleObj()



* **Parameters**: 

* **Usage**: 
```js
```

<br/>
<br/>

## Events


### click( comp, info, e )

버튼 클릭시 호출된다.

* **Parameters**: 
	* **`comp`** {AButton} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

### dragend()

버튼 드래그를 끝냈을때 호출합니다.

### dragstart()

버튼을 드래그하기 시작할때 호출합니다.

### drop()

버튼을 드롭했을때 호출합니다.

### longtab( comp, info, e )

버튼을 길게 탭할 때 호출된다.

* **Parameters**: 
	* **`comp`** {AButton} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

<br/>

## Attribute

### Data
* **Text:** 버튼의 텍스트를 설정하는 속성입니다.
* **Align:** 버튼 텍스트의 정렬을 설정하는 속성입니다. 
> * **left:** 텍스트 좌측 정렬 
> * **center:** 텍스트 중앙 정렬   
> * **right:** 텍스트 우측 정렬 
* **Icon:** : 버튼에 아이콘을 삽입하는 속성입니다. 
* **After Text:** 삽입된 아이콘이 텍스트 다음에 위치합니다. 
* **New Line Text:** 삽입된 아이콘과 텍스트를 위아래로 위치 시킵니다. Icon After Text 옵션을 이용해서 텍스트와 아이콘의 위 아래 위치를 변경 할 수 있습니다. 

### Option
* **Fast Click:** 설명이 필요합니다.
* **Tool Button:** 설명이 필요합니다.
* **Check Button:** 설명이 필요합니다.
* **Down State:** 설명이 필요합니다.
