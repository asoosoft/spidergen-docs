# EXHogaView
> **Extends**: [`AView`](./../afc/AView.md)



<br/>

## Properties

### frwName

* `Default` "stock"

<br/>

### isAutoResizeChildren \<Boolean>

자동으로 자식들의 위치, 높이를 변경할지 안할지에 대한 값

* `Default` true

<br/>

### showCount \<Number>

현재 뷰에서 보여줄 호가(행)의 개수

* `Default` 11

<br/>
<br/>

## Method

### updatePosition( pWidth, pHeight )

사이즈 변경될 때 호출되는 함수

- `pWidth` \<Number> 부모뷰의 넓이
- `pHeight` \<Number> 부모뷰의 높이

<br/>

### setShowCount( cnt )

현재 뷰에서 보여줄 호가의 개수를 지정한다.

* `cnt` \<Number> 

<br/>

### scrollToQuoteCenter()

1호가가 중간에 위치하도록 스크롤 위치를 변경한다.

<br/>

### getShowCount()

현재 뷰에서 보여줄 호가의 개수 리턴한다.

* **Returns** \<Number>

<br/>

### setAutoResizeChildren( isAuto )

자동으로 자식들의 위치, 높이를 변경할지 안할지를 지정한다.

* `isAuto` \<Boolean> 


<br/>

### getAutoResizeChildren()

자식들의 위치, 높이 자동변경여부를 리턴한다.

<br/>

### onRowCountChange()

호가그리드의 행개수가 변경될 때 호출되는 함수

<br/>