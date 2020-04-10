# ACalendar
> **Extends**: `AGrid`

캘린더뷰 객체 입니다.

<br/>

## Properties

### frwName



* **Type**: ``
* **Default**: ``

<br/>

### date



* **Type**: ``
* **Default**: ``

<br/>

### holiday



* **Type**: ``
* **Default**: ``

<br/>
<br/>

## Methods

### makeCalendar( year, month, day )

지정한 날짜로 캘린더를 생성한다.<br/>매개변수 year, month 가 모두 있을때 지정한 날짜로 생성하고 아니라면 현재날짜를 기준으로 한다.

* **Parameters**: 
	* **`year`** {String} 년도
	* **`month`** {Number} 월
	* **`day`** {String} 일

* **Usage**: 
```js
this.calendar.makeCalendar(2018, 3, 20);
```

<br/>

### nextMonth()

캘린더의 월을 이후 월로 변경한다.

* **Usage**: 
```js
this.calendar.nextMonth();
```

<br/>

### nextYear()

캘린더의 년도를 이후 년도로 변경한다.

* **Usage**: 
```js
this.calendar.nextYear();
```

<br/>

### prevMonth()

캘린더의 월을 이전 월로 변경한다.

* **Usage**: 
```js
this.calendar.prevMonth();
```

<br/>

### prevYear()

캘린더의 년도를 이전 년도로 변경한다.

* **Usage**: 
```js
this.calendar.prevYear();
```

<br/>

### setSelectCalEvent( evtName, listener, funcName )

캘린더에 이벤트를 추가한다.

* **Parameters**: 
	* **`evtName`** {String} 이벤트 이름(select, dblclick, ....)
	* **`listener`** {String} 이벤트를 전달받을 객체
	* **`funcName`** {String} 이벤트 발생시 호출할 listener 의 멤버함수 이름

* **Usage**: 
```js
this.calendar.setSelectCalEvent('select', this, 'onCalendarClick');
```

<br/>


### init()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>

## Events


### dblclick( comp, info, e )

더블 클릭시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

### longtab( comp, info, e )

길게 탭할때 호출 된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {String} null
	* **`e`** {Object} 이벤트 정보

### select( comp, info, e )

아이템 선택 시 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {jQuery Object} 아이템의 jQuery 객체
	* **`e`** {Object} 이벤트 정보

<br/>

