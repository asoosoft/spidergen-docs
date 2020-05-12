# ResPool
> **Extends**: 

AView 를 재사용하기 위한 메모리 풀 AView 객체 자체를 캐쉬하여 여러 곳에서 재사용한다.

<br/>

## Properties


### areaPool

뷰의 url을 키값으로 하여 뷰 엘리먼트를 넣어놓는 객체

* **Type**: `Object`
* **Default**: `{}`

<br/>

### viewPool

뷰의 url을 키값으로 하여 뷰 객체를 넣어놓는 객체

* **Type**: `Object`
* **Default**: `{}`

<br/>
<br/>

## Methods

### popView( url )

AView 를 메모리 풀에서 얻어온다. aview.url 값이 키값이 된다.

* **Returns**: AView

* **Parameters**: 
	* **`url`** {String} 얻고자 하는 AView 키값

<br/>

### pushView( aview )

AView 를 메모리 풀에 반환한다.

* **Parameters**: 
	* **`aview`** {AView} .

<br/>
<br/>
