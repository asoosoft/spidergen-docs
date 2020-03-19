# ATooltip
> **Extends**: `AFloat`

ATooltip

<br/>

## Properties

### isBgCheck



* **Type**: ``
* **Default**: ``

<br/>

### basicCss



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### hide()

툴팁을 숨깁니다.

<br/>

### init()

프래임을 세팅합니다.

<br/>

### show( tooltipMsg, targetRect, isImage )

툴팁을 표시합니다. 파라미터 targetRect에는 보통 컴포넌트의 getBoundRect()의 리턴값을 그대로 넘겨주거나, 직접 Object로 위치정보를 넣어도 됩니다. (ex: {left:0, top:0, right:100, bottom:100} )

* **Parameters**: 
	* **`tooltipMsg`** {String} 툴팁에 보여질 텍스트
	* **`targetRect`** {Object} 툴팁의 위치
	* **`isImage`** {Boolean} tooltipMsg가 이미지인지 여부

<br/>
<br/>
