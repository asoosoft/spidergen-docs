# ACalendarPicker
> **Extends**: `AView`

ACalendarPicker

<br/>

## Methods

### createElement( context )

엘리먼트 객체를 생성합니다.

* **Parameters**: 
	* **`context`** {HTML Object} 생성 할 엘리먼트 객체의 컨텍스트

<br/>

### getDate()

캘린더피커의 현재 날짜를 반환한다.

* **Returns**: json

* **Usage**: 
```js
var date = this.calendarpicker.getDate();
console.log(date); //{year: 2018, month: 3, day: 20}
```

<br/>

### getDateString()

캘린더피커의 현재 날짜를 문자열로 반환한다.

* **Returns**: String

* **Usage**: 
```js
var date = this.calendarpicker.getDateString();
 console.log(date); //20180320
```

<br/>

### getMode()

데이터피커의 현재 모드를 리턴한다.

* **Returns**: Number

* **Usage**: 
```js
var mode = this.calendarpicker.getMode();
console.log(mode);
//일별: ACalendarPickerItem.DAYMODE : 0
//월별: ACalendarPickerItem.MONTHMODE  : 1
```

<br/>

### getQueryData( dataArr, keyArr, queryData )

컴포넌트가 갖고 있는 정보를 keyArr 의 정보에 따라 dataArr에 채웁니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dataArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### openPopup()

캘린더피커의 팝업을 오픈한다.

* **Usage**: 
```js
this.calendarpicker.openPopup();
```

<br/>

### setDate( date )

데이트피커의 날짜를 설정한다.

* **Parameters**: 
	* **`date`** {Object} JSON object형식의 날짜

* **Usage**: 
```js
this.calendarpicker.setDate({
	year: 2018,
	month: 5,
	day: 10
});
```

<br/>

### setDisabled( isDisabled )

캘린더피커의 사용여부를 설정한다.

* **Parameters**: 
	* **`isDisabled`** {Boolean} 사용여부

* **Usage**: 
```js
this.calendarpicker.setDisabled(true);
```

<br/>

### setQueryData( dateArr, keyArr, queryData )

파라미터로 넘어온 dataArr 값을 keyArr 의 정보를 참조하여 컴포넌트에 셋팅합니다. dataArr은 AQueryData 특정부분의 참조자 입니다. 자세한 구조 및 상세설명은 QuerySystem.pptx 참조

* **Parameters**: 
	* **`dateArr`** {Array} [ {key1:value, key2:value ...}, {}, ... ]
	* **`keyArr`** {Array} [ key1, key3, key10 ]
	* **`queryData`** {AQueryData} AQueryData의 전체 값, 필요시 참조합니다.

<br/>

### setReadOnly( isReadOnly )

캘린더피커의 읽기전용 속성을 설정한다.

* **Parameters**: 
	* **`isReadOnly`** {Boolean} 읽기전용 여부

* **Usage**: 
```js
this.calendarpicker.setReadOnly(true);
```

<br/>
<br/>
## Events


### change( comp, info, e )

캘린더의 날짜가 변경될때 호출된다.

* **Parameters**: 
	* **`comp`** {AComponent} 컴포넌트
	* **`info`** {Object} 변경된 날짜 객체
	* **`e`** {Object} 이벤트 정보

<br/>

