# ACalendarPicker
**Extends**: [`AView`](./../afc/AView.md)

캘린더 피커는 날짜를 입출력하기 위해 만들어진 컴포넌트이다. 캘린더 피커는 두가지 영역으로 나뉘어져있다. 첫 번째는 직접 날짜를 입력 할수있는 캘린더 피커 영역이고, 두 번째는 달력 아이콘을 클릭했을 때 나타나는 달력 영역이다.

<br/>

## Class Variables

<br/>

## Instance Variables

### childComp \<ACalendarPickerItem>

달력 컴포넌트에서 실질적으로 날짜 및 달력을 관리하는 class

<br/>

## Class Methods

<br/>

## Instance Methods

### createElement( context ) 

엘리먼트 객체를 생성합니다. 일반적으로 init시점에 자동으로 호출되므로 직접 호출할 필요는 없다.

- `context` \<HTML Object> 생성 할 엘리먼트 객체의 컨텍스트

<br/>

### getDate() 

캘린더피커의 현재 날짜를 반환한다.

- **Returns** \<JSON Object> 날짜 정보 Object

```js
var date = this.calendarpicker.getDate();
console.log(date); 
//{year: 2020, month: 8, day: 15}
```

<br/>

### getDateString() 

캘린더피커의 현재 날짜를 문자열로 반환한다.

- **Returns** \<String> 날짜 정보 문자열
```js
var date = this.calendarpicker.getDateString();
console.log(date); 
//20200815
```

<br/>

### getDiffDate( gap ) 

캘린더피커의 날짜에서 매개변수 gap만큼 떨어진 날짜정보를 반환한다.

- `gap` \<number> 
```js
this.calendarpicker.getDate();
//{year: 2020, month: 8, day: 15}

this.calendarpicker.getDiffDate(5);
//{year: 2020, month: 8, day: 20}

this.calendarpicker.getDiffDate(-5);
//{year: 2020, month: 8, day: 10}
```

<br/>

### getMode() 

캘린더피커의 현재 모드를 리턴한다.

- **Returns** \<Number> 현재 모드 숫자값 0 or 1

```js
this.calendarpicker.getMode();
//일별: ACalendarPickerItem.DAYMODE    -> 0
//월별: ACalendarPickerItem.MONTHMODE  -> 1
```

<br/>

### openPopup() 

캘린더피커의 달력을 오픈한다.

<br/>

### setDate( date ) 

데이트피커의 날짜를 설정한다.

- `date` \<JSON Object> JSON Object형식의 날짜

```js
this.calendarpicker.setDate({
	year: 2020, month: 8, day: 15
});
```

<br/>

### setDisabled( isDisabled ) 

캘린더피커의 disabled 속성을 지정한다.

- `isDisabled` \<Boolean> 활성화 여부

<br/>

### setReadOnly( isReadOnly ) 

캘린더피커의 읽기전용 속성을 설정한다.

- `isReadOnly` \<Boolean> 읽기전용 여부 

<br/>

### setCalendarIconLeft() 

달력 모양의 아이콘을 좌측으로 정렬한다.

<br/>

### setCalendarIconRight() 

달력 모양의 아이콘을 우측으로 정렬한다.

<br/>

### setCalendarIconImage( img ) 

달력 모양의 아이콘 이미지를 변경한다.

- `img` \<String> 이미지 URL 
```js
this.calendarpicker.setCalendarIconImage('Assets/img/icon.png');
```

<br/>

### setCalendarPickerStyle( obj ) 

캘린더 피커의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setCalendarPickerStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setCalendarPickerSelectedStyle( obj )

캘린더 피커의 select 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setCalendarPickerSelectedStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setCalendarIconStyle( obj ) 

캘린더 피커의 요소중에 버튼의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setCalendarIconStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setCalendarInputStyle() 

캘린더 피커의 요소중에 텍스트 필드의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setCalendarInputStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setCalendarViewStyle() 

달력 전체를 감싸고 있는 view 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setCalendarViewStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setHeadViewStyle() 

달력의 상단 영역을 감싸는 view 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setHeadViewStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setYearMonthBtnStyle() 

캘린더 피커가 Month모드 일때 달력의 연도 부분의 스타일을 지정한다. 

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setYearMonthBtnStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setLLeftArrowBtnStyle() 

달력의 <<버튼의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setLLeftArrowBtnStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setLeftArrowBtnStyle() 

달력의 <버튼의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setLeftArrowBtnStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setRRightArrowBtnStyle() 

달력의 >>버튼의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setRRightArrowBtnStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setRightArrowBtnStyle() 

달력의 >>버튼의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setRightArrowBtnStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setHeadGridStyle() 

달력의 요일을 보여주는 헤더영역의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setHeadGridStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setListGridStyle() 

달력의 날짜 부분의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setListGridStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setHeadGridTdStyle() 

달력의 요일 하나하나의 td 영역의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setHeadGridTdStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setHeadGridTdFirstStyle()

달력의 요일 중 첫 번째 td인 일요일의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setHeadGridTdFirstStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setHeadGridTdLastStyle()

달력의 요일 중 마지막 td인 토요일의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setHeadGridTdLastStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setListGridTdStyle()

달력의 날짜 영역의 개별 td 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setListGridTdStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setListGridTdFirstStyle()

달력에서 첫 번째 라인인 일요일에 해당하는 날짜 영역의 td 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setListGridTdFirstStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setListGridTdLastStyle()

달력에서 마지막 라인인 토요일에 해당하는 날짜 영역의 td 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setListGridTdLastStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

### setListGridTdSelectedStyle()

달력에서 select된 날짜 영역의 스타일을 지정한다.

- `obj` \<Object> 스타일 Object

```js
this.calendarpicker.setListGridTdSelectedStyle({
	'background-color':'white', 
	'border-color':'black', 
	'border-width':'2px', 
	...
	...
});
```

<br/>

## Events


### change( comp, info, e )

캘린더의 날짜가 변경될때 호출된다.

- `comp` \<ACalendarPicker> 컴포넌트 객체
- `info` \<Object> 변경된 날짜 객체
- `e` \<Object> 이벤트 정보

  
<br/>

