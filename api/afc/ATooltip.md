# ATooltip
> **Extends**: [`AFloat`](AFloat.html#afloat)

툴팁 컴포넌트

<br/>

## Properties


### basicCss \<Object>

툴팁 기본 css 속성

<br/>
<br/>


## Class Methods

<br/>
<br/>


## Instance Methods

### show( tooltipMsg, targetRect, isImage ) 

툴팁을 표시한다. 파라미터 targetRect에는 보통 컴포넌트의 getBoundRect()의 리턴값을 그대로 넘겨주거나, 직접 Object로 위치정보를 설정해도 됨. (ex: {left:0, top:0, right:100, bottom:100} )

- `tooltipMsg` \<String> 툴팁에 보여질 텍스트
- `targetRect` \<Object> 툴팁의 위치
- `isImage` \<Boolean> tooltipMsg가 이미지인지 여부

```js
// 툴팁을 보여줄 Label 컴포넌트 ID : lbl

// Label ActionEnter 이벤트 설정
function MainView*onLblActionenter(comp, info, e)
{
	//툴팁을 생성한다.
	this.tooltip = new ATooltip();
	this.tooltip.init();
	
	//툴팁을 보여준다.
	this.tooltip.show('툴팁메시지', comp.getBoundRect());

	//툴팁에 메시지가 아닌 이미지 출력 방법
	//this.tooltip.show('Asset/img/star.jpg', comp.getBoundRect(), true);

};

// Label Actionleave 이벤트 설정
function MainView*onLblActionleave(comp, info, e)
{
	this.tooltip.hide(); //툴팁을 삭제한다.

};
```









<br/>
<br/>
