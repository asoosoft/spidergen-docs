# AIndicator
> **Extends** [`AFloat`](./AFloat.md)

AIndicator 는 로드 중 상태를 표현한다.

<br/>

## Class Variables

<br/>

## Instance Variables

### isFocusLostClose \<Boolean>

인디케이터 영역이 아닌 다른 부분을 누를 때 닫힘여부

* `Default` `false`

<br/>
<br/>

## Class Methods

### AIndicator.beginOltp()

인디케이터를 표시한다.
<br/>해당 함수를 호출하여 표시된 인디케이터는 [AIndicator.hide()](#-AIndicator.hide) 함수로는 숨겨지지 않으며 오로지 [AIndicator.endOltp()](#-AIndicator.endOltp) 함수를 사용해야 숨겨진다. 

<br/>

### AIndicator.endOltp()

인디케이터를 숨긴다. [AIndicator.show()](#-AIndicator.show) 가 호출된 횟수를 초기화시키므로 사용시 주의해야 한다.

<br/>

### AIndicator.hide()

인디케이터를 숨긴다. [AIndicator.show()](#-AIndicator.show) 가 호출된 횟수만큼 hide 호출해야 숨겨진다.

<br/>

### AIndicator.setClass( cssName )

인디케이터 CSS를 지정한다.

* `cssName` \<String> CSS Selector

### AIndicator.show()

인디케이터를 표시한다. 

<br/>
<br/>
