# ScrollManager
> **Extends**: 

자체적인 스크롤기능을 구현해주는 클래스

<br/>

## Properties

### scrlTimer



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### startTime



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### oldTime



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### startPos



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### oldPos



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### posGap



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### oldDis



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### totDis



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### scrollState



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### isScrollStop



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### scrollEnable



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### disableManagers



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### moveStart



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### stopCallback



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### option



* **Type**: ``
* **Default**: ``

<br/>

## Properties

### endVelocity



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### enableScroll( enable )

스크롤을 가능/불가능하게 만든다. 기본적으로 true 이다.

* **Parameters**: 
	* **`enable`** {Boolean} .

<br/>

### setOption( option )

스크롤 이동에 대한 감도를 셋팅한다. <br/>startDelay: 10, //최초 자동 스크롤 시작시 속도값. (값이 커질수록 느려진다.) <br/>endDelay: 20, //스크롤을 종료시킬 속도값. (값이 커질수록 천천히 멈춘다.)<br/><br/>scrollAmount: 50, //스크롤 이동 수치. (값이 작아질 수록 미세하기 움직이며 이동량이 작아진다.) <br/>speedRatio: 0.02 //스크롤 속도를 감속시킬 비율. (비율이 커질수록 최초 스크롤속도가 빨리 감속된다.)

* **Parameters**: 
	* **`option`** {Object} .

<br/>

### addDisableManager()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### removeDisableManager()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### removeAllDisableManager()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### setStopCallback()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### stopScrollTimer()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### initScroll()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### updateScroll()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### scrollCheck()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### autoScroll()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### autoScroll2()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
