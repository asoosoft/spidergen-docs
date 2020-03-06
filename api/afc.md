# afc
> **Extends**: 

afc ()

<br/>

## Methods

### abs( val )

절대값을 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### absComma( val )

절대값으로 변경 후 3자리마다 콤마(,)를 넣어 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### absCommaIfFixed( var )

소수점이 있는 숫자일 때 절대값의 3자리마다 콤마(,) 및 소수점 이하 2자리까지 반올림하여 반환합니다.<br/>소수점이 없는 숫자일 때 절대값의 3자리마다 콤마(,)를 반환합니다.

* **Parameters**: 
	* **`var`** {Number} 숫자

<br/>

### absCommaPercent( val )

절대값의 3자리마다 콤마(,)에다 끝에 %와 함께 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### absFloor1( value )

절대값 소수점1자리 버림해서 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### absFloor2( value )

소수점2자리 버림해서 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### absFloor2Per( value )

절대값 소수점 2자리 버림해서 % 붙여 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### absPercent( val )

절대값으로 치환하여 %붙여 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### addComma( val )

천단위마다 콤마를 추가합니다.

* **Returns**: String

* **Parameters**: 
	* **`val`** {Number} 금액

<br/>

### addCommaIfFixed( value )

소수점이 있는 숫자일 때 3자리마다 콤마(,) 및 소수점 이하 2자리까지 반올림하여 반환합니다. 소수점이 없는 숫자일 때 3자리마다 콤마(,)를 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### addPercent( val )

숫자에 %를 붙여 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### androidVersion()

안드로이드 버전을 가져옵니다.

<br/>

### beginTimeCheck( msg )

시작시간을 체크하기 위해 세팅합니다.

* **Parameters**: 
	* **`msg`** {String} 출력될 메세지

<br/>

### capitalAmount( value )

value/1000000 해서 나온 값을 0보다 적으면 소수점 2자리만큼 반올림해서 반환하고 <br/>아니면 정수형으로 3자리마다 콤마(,)해서 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### commaPercent()

commaPercent

<br/>

### dateToString( date )

DATE객체를 'yyyyMMdd' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`date`** {Date} DATE객체

<br/>

### disableLog()

afc.log와 console.log를 해도 표시되지 않게 비활성화 합니다.

<br/>

### ellapseCheck( msg )

경과된 시간을 세팅합니다.

* **Parameters**: 
	* **`msg`** {String} 출력될 메세지

<br/>

### enableApp( isEnable )

앱의 사용유무를 세팅합니다.

* **Parameters**: 
	* **`isEnable`** {Boolean} 사용유무

<br/>

### endTimeCheck( msg )

종료된 시간을 세팅합니다.

* **Parameters**: 
	* **`msg`** {String} 출력될 메세지

<br/>

### floatFix( value, pos )

소수점 자리수만큼 반올림하여 반환합니다. (defalut pos: 2자리)

* **Parameters**: 
	* **`value`** {Float} 숫자 또는 실수
	* **`pos`** {Number} 자리수

<br/>

### floor( value, pos )

value를 pos자리수 만큼 반올림하여 리턴합니다.

* **Returns**: Float

* **Parameters**: 
	* **`value`** {Number} 금액
	* **`pos`** {Number} 버림할 자리수

<br/>

### floor2()

floor2

<br/>

### floor2Per()

floor2Per

<br/>

### floorPer( value, pos )

소수점 자리수만큼 절하(버림)하여 %를 붙여 반환합니다.

* **Parameters**: 
	* **`value`** {Float} number 객체
	* **`pos`** {Number} 자리수

<br/>

### formatDate( dateNum )

년월일 텍스트를 'yyyy/MM/dd' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`dateNum`** {String} 년월일 텍스트

<br/>

### formatDate2( dateNum )

년월일 텍스트를 'yy/MM/dd' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`dateNum`** {String} 년월일 텍스트

<br/>

### formatDateTime( datetimeNum )

월일시분 텍스트를 'MM/dd HH:mm' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`datetimeNum`** {String} 월일시분 텍스트

<br/>

### formatMonth( monthNum )

년월 텍스트를 'yyyy/MM' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`monthNum`** {String} 년월 텍스트

<br/>

### formatSecond( t )

시분초(hhMMdd)의 초의 값으로 반환합니다.

* **Parameters**: 
	* **`t`** {String} 시분초

<br/>

### formatTic( datetimeNum )

일시분초 텍스트를 'dd HH:mm:ss' 형태로 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`datetimeNum`** {String} 월일시분 텍스트

<br/>

### getClassName( funcObj )

함수 명을 반환합니다.

* **Parameters**: 
	* **`funcObj`** {Function} 함수

<br/>

### getEventList( baseName )

컴포넌트 클래스가 구현 가능한 모든 이벤트 목록을 얻어 옵니다.

* **Parameters**: 
	* **`baseName`** {String} 컴포넌트 클래스명

<br/>

### getFileSrc( url, isEnc )

ajax통해서 파일 내용을 가져옵니다.

* **Parameters**: 
	* **`url`** {String} 주소
	* **`isEnc`** {Boolean} 암호화 여부

<br/>

### getRandomColor()

랜덤으로 컬러값을 생성합니다.

* **Returns**: #6자리

<br/>

### getUrlParameter()

현재 페이지의 도메인 주소(location.href)에서 파라메터만 추출하여 json으로 반환합니다.

<br/>

### intComma( val )

정수형으로 치환 후 3자리마다 콤마(,)를 붙여 반환합니다.

* **Parameters**: 
	* **`val`** {Number} 숫자

<br/>

### iosVersion()

ISO 버전을 가져옵니다.

<br/>

### isDeviceOf( device )

파라미터로 넘어온 device문자열로 디바이스를 구분하여 결과를 리턴한다.

* **Returns**: Boolean

* **Parameters**: 
	* **`device`** {String} 디바이스문자열 ex) afc.isDeviceOf('Android')

<br/>

### loadCss( url )

스타일시트파일을 로드합니다.

* **Parameters**: 
	* **`url`** {String} 주소

<br/>

### loadScript( url )

js파일을 로드합니다.

* **Parameters**: 
	* **`url`** {String} 주소

<br/>

### loadScriptSync( url, isEnc )

스크립트 내용을 스크립트화 합니다.

* **Parameters**: 
	* **`url`** {String} 주소
	* **`isEnc`** {Boolean} 암호화 유무

<br/>

### log( msg )

로그를 표시합니다.

* **Parameters**: 
	* **`msg`** {String} 로그메세지

<br/>

### logOption( option )

로그의 옵션을 셋팅합니다.

* **Parameters**: 
	* **`option`** {Object} 로그옵션 { compElement: false }

<br/>

### makeAccText( accInfo, isGroup )

계좌정보에 표현할 텍스트를 가공하여 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`accInfo`** {Object} 계좌객체
	* **`isGroup`** {Boolean} 그룹바이 여부

<br/>

### makeDummyString( length )

데이터의 길이만큼 더미문자(*)를 생성하여 리턴합니다.

* **Returns**: String

* **Parameters**: 
	* **`length`** {Number} 데이터의 길이

<br/>

### oneHundredMillionAmount( value )

value/100000000으로 나눠 0보다 작으면 소수점 2자리만큼 반올림해서 반환하고<br/>아니면 정수형으로 3자리마다 콤마(,)해서 반환합니다.

* **Parameters**: 
	* **`value`** {Number} 숫자

<br/>

### phoneCall( phoneNumber )

파라미터로 넘어온 전화번호로 전화를 겁니다.

* **Parameters**: 
	* **`phoneNumber`** {String} 전화번호

<br/>

### removeComma( val )

천단위 콤마를 제거합니다.

* **Returns**: String

* **Parameters**: 
	* **`val`** {String} 콤마가 붙은 금액

<br/>

### removeCss( url )

html DOM에서 스타일시트를 제거합니다.

* **Parameters**: 
	* **`url`** {String} 주소

<br/>

### returnAsIt( val )

인자값을 그래돌 되돌려줍니다.

* **Parameters**: 
	* **`val`** {String} 인자 값

<br/>

### setLogFilter( filter )

로그를 필터할 문구를 세팅합니다.

* **Parameters**: 
	* **`filter`** {String} 필터할 문구

<br/>

### setLogOption( option )

로그의 옵션을 셋팅합니다.

* **Parameters**: 
	* **`option`** {Object} 로그옵션 { compElement: false }

<br/>

### toFixed( num, fixed )

num을 소수점 fixed 자리수 이하 버림해서 반환하는 함수

* **Parameters**: 
	* **`num`** {Number} 숫자
	* **`fixed`** {Number} 자리수

<br/>

### toFixed2( value )

소수점2자리 반올림해서 반환합니다.

* **Parameters**: 
	* **`value`** {String} 숫자

<br/>

### touchDelay()

터치 지연시간만큼 앱을 중지합니다.

<br/>
<br/>
