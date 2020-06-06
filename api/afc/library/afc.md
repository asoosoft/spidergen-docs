# afc

Asoosoft Foundation Class 란 의미의 네임스페이스


<br/>

## Methods

### afc.abs( val )

절대값을 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### afc.absComma( val )

절대값으로 변경 후 3자리마다 콤마(,)를 넣어 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### afc.absCommaIfFixed( var )

소수점이 있는 숫자일 때 절대값의 3자리마다 콤마(,) 및 소수점 이하 2자리까지 반올림하여 반환합니다.<br/>소수점이 없는 숫자일 때 절대값의 3자리마다 콤마(,)를 반환합니다.

* **Parameters**: 
	* **`var`** {Number} 숫자

<br/>

### afc.absCommaPercent( val )

절대값의 3자리마다 콤마(,)에다 끝에 %와 함께 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### afc.absFloor1( value )

절대값 소수점1자리 버림해서 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### afc.absFloor2( value )

소수점2자리 버림해서 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### afc.absFloor2Per( value )

절대값 소수점 2자리 버림해서 % 붙여 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### afc.absPercent( val )

절대값으로 치환하여 %붙여 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### afc.addComma( val )

천단위마다 콤마를 추가합니다.

* **Returns**: String

* **Parameters**: 
	* **`val`** {Number} 금액

<br/>

### afc.addCommaIfFixed( value )

소수점이 있는 숫자일 때 3자리마다 콤마(,) 및 소수점 이하 2자리까지 반올림하여 반환합니다. 소수점이 없는 숫자일 때 3자리마다 콤마(,)를 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### afc.addPercent( val )

숫자에 %를 붙여 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### afc.androidVersion()

안드로이드 버전을 가져옵니다.

<br/>

### afc.beginTimeCheck( msg )

시작시간을 체크하기 위해 세팅합니다.

* **Parameters**: 
	* **`msg`** {String} 출력될 메세지

<br/>

### afc.capitalAmount( value )

value/1000000 해서 나온 값을 0보다 적으면 소수점 2자리만큼 반올림해서 반환하고 <br/>아니면 정수형으로 3자리마다 콤마(,)해서 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### afc.commaPercent()

commaPercent

<br/>

### afc.dateToString( date )

DATE객체를 'yyyyMMdd' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`date`** {Date} DATE객체

<br/>

### afc.disableLog()

afc.log와 console.log를 해도 표시되지 않게 비활성화 합니다.

<br/>

### afc.ellapseCheck( msg )

경과된 시간을 세팅합니다.

* **Parameters**: 
	* **`msg`** {String} 출력될 메세지

<br/>

### afc.endTimeCheck( msg )

종료된 시간을 세팅합니다.

* **Parameters**: 
	* **`msg`** {String} 출력될 메세지

<br/>

### afc.floatFix( value, pos )

소수점 자리수만큼 반올림하여 반환합니다. (defalut pos: 2자리)

* **Parameters**: 
	* **`value`** {Float} 숫자 또는 실수
	* **`pos`** {Number} 자리수

<br/>

### afc.floor( value, pos )

value를 pos자리수 만큼 반올림하여 리턴합니다.

* **Returns**: Float

* **Parameters**: 
	* **`value`** {Number} 금액
	* **`pos`** {Number} 버림할 자리수

<br/>

### afc.floor2()

floor2

<br/>

### afc.floor2Per()

floor2Per

<br/>

### afc.floorPer( value, pos )

소수점 자리수만큼 절하(버림)하여 %를 붙여 반환합니다.

* **Parameters**: 
	* **`value`** {Float} number 객체
	* **`pos`** {Number} 자리수

<br/>

### afc.formatDate( dateNum )

년월일 텍스트를 'yyyy/MM/dd' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`dateNum`** {String} 년월일 텍스트

<br/>

### afc.formatDate2( dateNum )

년월일 텍스트를 'yy/MM/dd' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`dateNum`** {String} 년월일 텍스트

<br/>

### afc.formatDateTime( datetimeNum )

월일시분 텍스트를 'MM/dd HH:mm' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`datetimeNum`** {String} 월일시분 텍스트

<br/>

### afc.formatMonth( monthNum )

년월 텍스트를 'yyyy/MM' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`monthNum`** {String} 년월 텍스트

<br/>

### afc.formatSecond( t )

시분초(hhMMdd)의 초의 값으로 반환합니다.

* **Parameters**: 
	* **`t`** {String} 시분초

<br/>

### afc.formatTic( datetimeNum )

일시분초 텍스트를 'dd HH:mm:ss' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`datetimeNum`** {String} 월일시분 텍스트

<br/>

### afc.getClassName( funcObj )

오브젝트의 클래스 이름을 반환합니다.

* **Parameters**: 
	* **`funcObj`** {Function} 함수

<br/>

### afc.getUrlParameter()

현재 페이지의 도메인 주소(location.href)에서 파라메터만 추출하여 json으로 반환합니다.

<br/>

### afc.intComma( val )

정수형으로 치환 후 3자리마다 콤마(,)를 붙여 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### afc.iosVersion()

ISO 버전을 가져옵니다.

<br/>

### afc.isDeviceOf( device )

파라미터로 넘어온 device문자열로 디바이스를 구분하여 결과를 리턴한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`device`** {String} 디바이스문자열 ex) afc.isDeviceOf('Android')

<br/>

### afc.loadCss( url )

스타일시트(css) 파일을 로드합니다.

* **Parameters**: 
	* **`url`** {String} 주소

<br/>

### afc.loadScript( url )

js파일을 로드합니다.

* **Parameters**: 
	* **`url`** {String} 주소

<br/>

### afc.log( msg )

로그를 표시합니다.

* **Parameters**: 
	* **`msg`** {String} 로그메세지

<br/>

### afc.logOption( option )

로그의 옵션을 셋팅합니다.

* **Parameters**: 
	* **`option`** {Object} 로그옵션 { compElement: false }

<br/>

### afc.makeDummyString( length )

데이터의 길이만큼 더미문자(*)를 생성하여 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`length`** {Number} 데이터의 길이

<br/>

### afc.oneHundredMillionAmount( value )

value/100000000으로 나눠 0보다 작으면 소수점 2자리만큼 반올림해서 반환하고<br/>아니면 정수형으로 3자리마다 콤마(,)해서 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### afc.removeComma( val )

천단위 콤마를 제거합니다.

* **Returns**: String

* **Parameters**: 
	* **`val`** {String} 콤마가 붙은 금액

<br/>

### afc.removeCss( url )

html DOM에서 스타일시트를 제거합니다.

* **Parameters**: 
	* **`url`** {String} 주소

<br/>

### afc.setLogFilter( filter )

로그를 필터할 문구를 세팅합니다.

* **Parameters**: 
	* **`filter`** {String} 필터할 문구

<br/>

### afc.setLogOption( option )

로그의 옵션을 셋팅합니다.

* **Parameters**: 
	* **`option`** {Object} 로그옵션 { compElement: false }

<br/>

### afc.toFixed( num, fixed )

num을 소수점 fixed 자리수 이하 버림해서 반환하는 함수

* **Parameters**: 
	* **`num`** {Number} 숫자
	* **`fixed`** {Number} 자리수

<br/>

### afc.toFixed2( value )

소수점2자리 반올림해서 반환합니다.

* **Parameters**: 
	* **`value`** {String} 숫자

<br/>

### afc.enableUserSelect()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.enableScrollIndicator()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.log()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.log2()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.stringifyOnce()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.makeCompIdPrefix()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>


### afc.mergeObject()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.loadSync()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.setVersionMap()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.removeScript()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.existScriptSrc()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.setIndexScriptMap()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.refreshApp()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.makeMeta()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.changeScale()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.browserCheck()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.deviceCheck()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.addRule()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.hogaComma()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.formatTime()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.formatHMS()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.switchButtonColor()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.plusfloorPercen()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.sigaTotalAmount()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.isResize()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### Date.prototype.format()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### String.prototype.str()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### String.prototype.zf()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### Number.prototype.zf()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### String.prototype.replaceAt()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### window.onerror()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>

### afc.loadCSSIfNotLoaded()



* **Parameters**: 


* **Usage**: 
```js

```

<br/>
<br/>
