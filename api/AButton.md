# AButton
 > **Extends**: `AComponent`  
 
버튼 컴포넌트

<br/>

## Properties


### bgColors

버튼의 상태별 배경 색상

* **Type**: `Array`
* **Default**: `null`

<br/>

### bgImages

버튼의 상태별 배경 색상

* **Type**: `Array`
* **Default**: `null`

<br/>

### btnStyles

버튼의 상태별 스타일 클래스명

* **Type**: `Array`
* **Default**: `null`

<br/>

### isSpeedBtn

버튼의 연속 터치에 대해 빠르게 반응할지 여부

* **Type**: `Boolean`
* **Default**: `false`

<br/>

### isStyleOver

버튼의 상태 변경시 스타일을 중첩하여 적용할지 여부 .
ex) normal 에서 touch 로 변경시 normal 의 스타일을 유지한 채 touch 의 스타일을 중첩하여 적용할 지 여부. 
false 로 지정하면 이전 스타일 값을 제거하고 변경된 스타일을 적용한다.

* **Type**: `Boolean`
* **Default**: `true`

<br/>

### txtColors

버튼의 상태별 텍스트 색상

* **Type**: `Array`
* **Default**: `null`

<br/>
<br/>

## Methods

### applyBaseState()

button의 defStyle변수에 저장해둔 기본클래스를 적용한다.  
저장해둔 defStyle이 없다면 baseState변수에서 background-color와 border style만 적용한다.

* **Usage**: 
  ```js
	btn.applyBaseState();
  ```		

<br/>

### changeBtnState( newState )

Button의 상태를 변경한다.

* **Parameters**: 
	* `newState` { String }  변경할 상태값  `AButton.OVER, AButton.DOWN, AButton.DISABLE`

* **Usage**: 
  ```js
	btn.changeBtnState(AButton.OVER);
  ```		

<br/>

### changeLigntness( colorKey, ratio, important )

밝기를 변경하는 함수이다. downState함수와 overState함수에서 밝기를 변경할 때 호출하는 함수이다.

* **Parameters**: 
	* **`colorKey`** { String }  css key값. `'background-color'`
	* **`ratio`** { Float }  밝기율. `0.7, 1.5`
	* **`important`** { String }  important여부. `'important'`

* **Usage**: 
  ```js
	btn.changeLigntness('background-color', 0.7, 'important');
  ```		
  
<br/>

### changeOppositeColor( colorKey, important )

지정되어 있는 RGB값을 추출해서 해당 RGB의 보색을 구해서 다시 지정하는 함수이다.

* **Parameters**: 
	* **`colorKey`** { String }  css key값. `'background-color'`
	* **`important`** { String }  important여부. `'important'`

* **Usage**: 
  ```js
	btn.changeOppositeColor('background-color', 'important');
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

Button이 Enable이 true일때 버튼의 상태를 초기 화한다.  
내부적으로 `clearBtnState`함수와 `applyBaseState`함수를 호출한다.

* **Usage**: 
  ```js
	btn,defaultBtnState();
  ```		

<br/>

### downState()

button의 background-color속성의 보색으로 border를 지정하고 밝기를 줄이는 함수이다.

* **Usage**: 
  ```js
	btn.downState();
  ```		

<br/>

### enable(isEnable)

Button의 활성, 비활성 상태를 세팅한다.

* **Parameters**: 
	* **`isEnable`** { Boolean }  활성화 여부.
	
* **Usage**: 
  ```js
	btn.enable(true);
  ```		

<br/>

### getHtml()

버튼의 HTML 내용을 리턴한다.

* **Returns**:  String

* **Usage**: 
  ```js
	var result = btn.getHtml();
  ```		

<br/>

### getImage()

Button의 Image src값을 리턴한다.

* **Returns**:  String

* **Usage**: 
  ```js
	btn.getImage();
  ```		

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채웁니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** { Array }  `[ {key1:value, key2:value ...}, {}, ... ]`
	* **`keyArr`** { Array }   `'[ key1, key3, key10 ]'`
    * **`queryData`** { AQueryData }   AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### getText()

버튼의 텍스트 값을 얻어온다.

* **Returns**:  String

* **Usage**: 
  ```js
	var result = btn.getText();
  ```		

<br/>

### init( context, evtListener )

컴포넌트를 생성하고 초기화 할 때 호출한다.  
동적으로 객체를 생성할 경우 파라미터를 생략하고 호출한다.

* **Parameters**: 
	* **`context`** { String }  컴포넌트 생성 및 초기화 정보
	* **`evtListener`** { String }  context 에 매핑된 이벤트 수신자

* **Usage**: 
  ```js
	var btn = new AButton();
	btn.init();
  ```		
  
<br/>

### overState( )

button의 밝기를 늘려주는 함수이다.

* **Usage**: 
  ```js
	btn.overState();
  ```		
  
<br/>

### saveBaseState( )

Button이 초기화될때 호출되는 함수로, data-style 속성을 defStyle변수에 저장해 둔다. 만약 data-style속성에 값이 없다면 baseState변수에 background-color, border style값을 저장해둔다.

* **Usage**: 
  ```js
	btn.saveBaseState();
  ```		
  
<br/>

### setBtnStyle( state, styles )

Button의 상태별 스타일 클래스명을 세팅한다.

* **Parameters**: 
	* **`state`** { String } Button 상태  `AButton.OVER, AButton.DOWN, AButton.DISABLE`
	* **`styles`** { String }  클래스 이름
        
* **Usage**: 
  ```js
	btn.setBtnStyle(AButton.OVER, 'ClassName');
  ```		
  
<br/>

### setDefStyle( style )

Button의 상태별 스타일 클래스명을 세팅한다.

* **Parameters**: 
	* **`style`** { Object }  Style object
        
* **Usage**: 
  ```js
	btn.setDefStyle({width:'80px', height:'22px'});
  ```		
  
<br/>

### setHtml( text )

Button의 html값을 셋팅한다.

* **Parameters**: 
	* **`text`** { String }  html 내용 또는 String입니다.
        
* **Usage**: 
  ```js
	btn.setHtml('test');
  ```		
  
<br/>

### setImage( url )

Button의 Image를 세팅한다.

* **Parameters**: 
	* **`url`** { String }  이미지 url
       
* **Usage**: 
  ```js
	btn.setImage('asset/img/btn.png');
  ```		
  
<br/>

### setQueryData( dataArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem 참조

* **Parameters**: 
	* **`dataArr`** { Array }  [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** { Array }  [ key1, key3, key10 ]
	* **`queryData`** { AQueryData }  AQueryData의 전체 값, 필요시 참조합니다.
  
<br/>

### setText( text )

버튼의 텍스트 값을 셋팅한다.

* **Parameters**: 
	* **`text`** { String }  텍스트
        
* **Usage**: 
  ```js
	 var value= 'Hello';
	 btn.setText(value);
  ```		
  
<br/>
<br/>

<!--
## Events


### click( comp, info, e )

마우스 버튼 클리 후 또는 스크린에서 손가락을 때고 난 후 발생한다.

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>


### longtab( comp, info, e )

버튼이 길게 클릭 될 때 또는 스크린에서 손가락을 길게 닿고 있을때 발생한다. (1000ms 이상)

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>

### actiondown( comp, info, e )

마우스 버튼이 눌릴 때 또는 스크린에 손가락이 닿을 때 발생한다.

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>

### actionmove( comp, info, e )

마우스 포인트가 움직일때 또는 스크린에서 손가락이 닿은 채로 움직일때 발생한다.

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>

### actionup( comp, info, e )

마우스 버튼이 올라올 때 또는 스크린에서 손가락을 뗄 때 발생된다.

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>

### actioncancel( comp, info, e )

시스템에서 이벤트를 취소 시킬 때 발생한다. 

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>	

### actionenter( comp, info, e )

마우스가 요소의 경계를 외부에서 내부로 진입 할 때 발생한다.

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>	

### actionleave( comp, info, e )

마우스가 요소의 경계를 내부에서 외부로 이동 할 때 발생한다.

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>	

### keydown( comp, info, e )

키보드의 키가 눌릴 때 발생한다.

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>	


### keyup( comp, info, e )

키보드의 키가 눌렸다 올라올 때 발생한다.

* **Parameters**: 
	* **`comp`** { AButton } 버튼 컴포넌트
	* **`info`** { String }  null
	* **`e`** { Object }  이벤트 객체
	
<br/>	

-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAwNzI2MzI1MF19
-->