# ABuffer( size )
> **Extends**

* `size` \<Number> 버퍼 사이즈

Uint8Array 컨트롤 클래스

<br/>

## Class Variables

### ABuffer.MAX_INT \<Number>

* `Math.pow(2, 53)`

<br/>

### ABuffer.MASK31 \<Number>

* `0x7fffffff`

<br/>

### ABuffer.MASK32 \<Number>

* `0xffffffff`

<br/>

### ABuffer.VAL31 \<Number>

* `0x80000000`

<br/>

### ABuffer.VAL32  \<Number>

* `0x100000000`

<br/>


<br/>

## Instance Variables

### buf \<UInt8Array>

Uint8Array 버퍼(byte buffer)

<br/>

### charset \<String>

String 변환시 적용할 인코딩 값. 'utf-8', 'euc-kr' ...

<br/>

### dataSize \<Number>

버퍼 사이즈가 아닌 데이터 사이즈를 나타내는 정수이다.

<br/>

### decoder \<Object>

setCharset 함수에서 생성된 디코딩 객체이다.

<br/>

### emptyChar \<String>

setString 또는 setOriString 같은 문자열 세팅 함수에서 문자열을 셋팅하고 남은 빈자리를 채우는 문자이다.

* `Default` 0x20

<br/>

### emptyNumChar \<String>

setNumString 또는 setSNumString 같은 숫자 세팅 함수에서 숫자를 셋팅하고 남은 빈자리를 채우는 문자이다.

* `Default` 0x30

<br/>

### encoder \<Object>

setCharset 함수에서 생성된 인코딩 객체이다.

<br/>

### offset \<Number>

버퍼의 특정 위치를 가리키고 있는 값 add~ 계열 함수에서 참조하여 현재 offset에 값을 셋팅한다. set~ 계열 함수가 호출되면 셋팅된 데이터의 마지막 위치의 다음을 가리킨다.

<br/>
<br/>

## Class Methods

<br/>

## Instance Methods

### addBinary( size, value )

현재의 offset 부터 size 만큼 문자열 또는 배열의 binary값을 셋팅한다.

* `size` \<String> 길이
* `value` \<String or Array>

```js
var buf = new ABuffer(10);
buf.addBinary(3, '123');
buf.addBinary(3, [10, 11, 12]); 
buf.addBinary(3, [0x10, 0x11, 0x12]);
```

<br/>

### addByte( value )

현재의 offset 에 byte value 를 셋팅한다.

* `value` \<String> 추가할 문자

```js
var buf = new ABuffer(10);
buf.addByte(255);
buf.addByte(0xff);
buf.getByte(0); // 255
```

<br/>

### addChar( value )

현재의 offset 에 char value 를 셋팅한다. 하나의 문자열을 넘기면 char code 로 변환하여 셋팅된다.

* `value` \<String> 문자열

```js
var buf = new ABuffer(10);
buf.addChar('Z');
```

<br/>

### addDWord( value )

현재 offset 부터 4 byte 공간에 우측정렬하여 이진수를 셋팅한다. 부호가 음수인 경우 2의 보수법으로 처리한다.

* `value` \<String> 값

```js
var buf = new ABuffer(10);
buf.addDWord(0xffffffff);
buf.addDWord(-256);
buf.getDWord(0); //4294967295
buf.getInt(4); //-256
```

<br/>

### addNumString( size, value )

현재의 offset 에 숫자를 문자열로 변환하여 셋팅한다. size 를 기준으로 우측정렬하여 문자열을 셋팅하고 남은 빈자리는 앞에서부터 0 으로 채운다

* `size` \<String> 문자열 길이
* `value` \<String> 변환할 값

```js
var buf = new ABuffer(10);
buf.addNumString(4, 1234);
buf.addNumString(6, '987654');
```

<br/>

### addOffset( add )

현재의 버퍼 offset 값을 add 만큼 이동시킨다

* `add` \<String> offset 이동할 값

```js
var buf = new ABuffer(10);
buf.addOffset(3);
buf.addChar('A');  // [0, 0, 0, 65, 0, ... 0]
```

<br/>

### addOriString( size, value )

현재의 offset 에 문자열을 셋팅한다. size 를 기준으로 문자열을 셋팅하고 남은 빈자리는 this.emptyChar로 채운다. this.charset 을 셋팅했지만 인코딩이 되지 말아야 할 경우 사용한다.

* `size` \<Number> 길이
* `value` \<String> 값

```js
var buf = new ABuffer(11);
buf.setOriString(0, 1, 'Z');
buf.addOriString(10, 'abcdefghij');
buf.getOriString(0, 1); // 'Z'
buf.nextOriString(10); // 'abcdefghij'
```

<br/>

### addSNumString( size, value )

현재의 offset 에 숫자를 문자열로 변환하여 셋팅한다. 부호를 offset 위치에 표현하고 size 를 기준으로 우측정렬하여 문자열을 셋팅하고 남은 빈자리는 앞에서부터 this.emptyNumChar 로 채운다.

* `size` \<Number> 길이
* `value` \<String or Number> 값

```js
var buf = new ABuffer(10);
buf.setSNumString(0, 4, -123);
buf.getString(0, 4);
```

<br/>

### addString( size, value )

현재의 offset 에 문자열을 셋팅한다. size 를 기준으로 문자열을 셋팅하고 남은 빈자리는 공백으로 채운다. this.charset 이 셋팅되어져 있으면 인코딩 과정을 거친후 셋팅되어 진다.

* `size` \<Number> size 가 1보다 작으면 value 의 길이만큼 셋팅된다.
* `value` \<String> 값

```js
var buf = new ABuffer(10);
buf.setCharset('euc-kr');
buf.setOffset(3);
buf.addString(5, '샘플 ');
buf.getString(3, 5, true);
```

<br/>

### addType( size, value )

현재 offset 부터 size 만큼 value의 메모리 값을 세팅한다. 부호가 음수인 경우 2의 보수법으로 처리한다

* `size` \<Number> 길이
* `value` \<String or Number> 값

```js
var buf = new ABuffer(10);
buf.addType(0, 2, 10);
buf.setOffset(0);
buf.nextType(2, true);
```

<br/>

### addWord( value )

현재 offset 부터 2 byte 공간에 우측정렬하여 이진수를 셋팅한다. 부호가 음수인 경우 2의 보수법으로 처리한다.

* `value` \<String or Number> 값

```js
var buf = new ABuffer(10);
buf.addWord(0xffff);
buf.addWord(-0xfff);
buf.getWord(0); //65535
buf.getShort(2); //-4095
```

<br/>

### copyBuffer( fromBuf, offset )

fromBuf 의 내용을 offset 위치부터 복사한다.

* `fromBuf` \<Array> 타입 Uint8Array
* `offset` \<Number> 위치

```js
var buf = new ABuffer(10);
var copiedBuf = new Uint8Array([1, 2, 3, 4, 5]);
buf.copyBuffer(copiedBuf, 3); // [0,0,0,1,2,3,4,5,0,0]
```

<br/>

### EOF()

this.offset과 this.dataSize로 판단한 데이터의 끝 여부를 반환한다.

* **Returns** \<Boolean>

```js
var buf = new ABuffer(10);
buf.EOF(); // false
buf.setDataSize(8);
buf.setOffset(10);
buf.EOF(); // true
```

<br/>

### fillBuffer( value, size )

value의 값을 처음부터 size 만큼 버퍼에 채운다. size 값이 생략되면 마지막까지 채운다.

* `value` \<String> 값
* `size` \<String> 길이

```js
var buf = new ABuffer(10);
buf.fillBuffer(0x20);
buf.fillBuffer(0x30, 5);
```

<br/>

### getBinary( offset, size )

버퍼의 특정 offset 부터 size 만큼의 binary값을 배열로 반환한다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* **Returns** \<Array>

```js
var buf = new ABuffer(10);
buf.addBinary(10, '0123456789');
buf.getBinary(3, 5); // [3,4,5,6,7]
```

<br/>

### getBuffer()

생성된 버퍼의 객체를 넘겨준다.

* **Returns** \<Uint8Array>

```js
var buf = new ABuffer(10);
buf.getBuffer();
```

<br/>

### getBufSize()

생성된 버퍼의 사이즈를 리턴한다.

* **Returns** \<Number>

```js
var buf = new ABuffer(10);
var bufSize = buf.getBufSize(); //10
```

<br/>

### getByte( offset )

버퍼의 특정 offset 으로부터 byte value 를 얻어온다.

* `offset` \<Number> 위치
* **Returns** \<Byte>

```js
var buf = new ABuffer(10);
buf.setByte(0, 255);
buf.getByte(0); // 255
```

<br/>

### getCharset()

String 변환시 적용할 인코딩 값을 얻어온다. 'utf-8', 'euc-kr' ...

* **Returns** \<String>

```js
var buf = new ABuffer(10);
buf.setCharset('euc-kr');
var charset = buf.getCharset();
```

<br/>

### getDataSize()

버퍼 사이즈가 아닌 데이터 사이즈를 반환한다.

* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.setDataSize(8);
var dataSize = buf.getDataSize(); //8
```

<br/>

### getDWord( offset )

버퍼의 특정 offset 부터 4 byte 만큼의 바이너리 이진수를 Number타입 숫자로 변환하여 리턴한다. 부호는 없다고 판단한다.

* `offset` \<Number> 위치
* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.addDWord(0xffffffff);
buf.getDWord(0); //4294967295
```

<br/>

### getInt( offset )

버퍼의 특정 offset 부터 4 byte 만큼을 정수로 변환하여 리턴한다.

* `offset` \<Number> 위치
* **Returns** \<Integer>

```js
var buf = new ABuffer(10);
buf.addDWord(0xffffffff);
buf.addDWord(-256);
buf.getDWord(0);
buf.getInt(4);
```

<br/>

### getIpString( offset )

버퍼의 특정 offset 부터 12자리를 읽어 IPv4 주소형태의 문자열을 반환한다. 예를 들어 "127.0.0.1"

* `offset` \<Number> 위치
* **Returns** \<String>

```js
var buf = new ABuffer(12);
buf.addOriString(12, '127001010100');
buf.getIpString(0);
```

<br/>

### getOffset()

현재의 버퍼 offset 값을 리턴한다. this.offset 참조.

* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.setOffset(4);
var ofs= buf.getOffset(); //4
```

<br/>

### getOriString( offset, size, noTrim )

버퍼의 특정 offset 부터 size 만큼의 문자열을 얻어온다. this.charset 을 셋팅했지만 디코딩이 되지 말아야 할 경우 사용되어진다. noTrim 값에 따라 앞뒤 공백이 trim 처리되거나 처리되지 않고 리턴된다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* `noTrim` \<Boolean> trim 여부
* **Returns** \<String>

```js
var buf = new ABuffer(11);
buf.setOriString(0, 1, 'Z');
buf.addOriString(10, 'abcdefghij');
buf.getOriString(0, 1); // 'Z'
buf.nextOriString(10); // 'abcdefghij'
```

<br/>

### getParseFloat( offset, size )

버퍼의 특정 offset 부터 size 만큼의 문자열을 읽어 부동소수점 숫자로 변환하여 리턴한다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* **Returns** \<Float>

```js
var buf = new ABuffer(10);
buf.setSNumString(0, 10, -123.1);
buf.getParseFloat(0, 10); // -123.1
buf.getString(0, 10); // -0000123.1
```

<br/>

### getParseInt( offset, size )

버퍼의 특정 offset 부터 size 만큼의 문자열을 읽어 정수로 변환하여 리턴한다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* **Returns** \<Int>

```js
var buf = new ABuffer(10);
buf.setSNumString(0, 10, -123.1);
buf.getParseInt(0, 10); // -123
buf.getString(0, 10); // -0000123.1
```

<br/>

### getShort( offset )

버퍼의 특정 offset 부터 2 byte 만큼의 바이너리 이진수를 Number타입 숫자로 변환하여 리턴한다. 최상위 비트를 부호 비트라고 판단한다.

* `offset` \<Number> 위치
* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.addWord(-0xfff);
buf.getShort(0); //-4095
```

<br/>

### getString( offset, size, noTrim )

버퍼의 특정 offset 부터 size 만큼의 문자열을 얻어온다. this.charset 이 셋팅되어져 있으면 디코딩 과정을 거친후 리턴되어 진다. noTrim 값에 따라 앞뒤 공백이 trim 처리되거나 처리되지 않고 리턴된다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* `noTrim` \<Boolean> trim  여부
* **Returns** \<String>

```js
var buf = new ABuffer(10);
buf.setCharset('euc-kr');
buf.setString(0, 5, '샘플 ');
buf.getString(0, 5, true);
```

<br/>

### getStringTo( offset, endValue )

버퍼의 특정 offset 부터 endValue 가 있는 곳까지의 문자열을 얻어온다. this.charset 이 셋팅되어져 있으면 디코딩 과정을 거친후 리턴되어 진다.

* `offset` \<Number> 위치
* `endValue` \<Number> Byte

```js
var buf = new ABuffer(10);
buf.setString(0, 5, 'abcd$efgh$');
buf.getStringTo(0, '$'.charCodeAt(0)); // abcd
```

<br/>

### getType( offset, size, unsigned )

버퍼의 특정 offset 부터 size 만큼의 바이너리 이진수를 Number타입 숫자로 변환하여 리턴한다. signed 인 경우 2의보수 처리한다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* `unsigned` \<Boolean> 부호여부
* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.setType(0, 2, 10);
buf.getType(0, 2);
```

<br/>

### getWord( offset )

버퍼의 특정 offset 부터 2 byte 만큼의 바이너리 이진수를 Number타입 숫자로 변환하여 리턴한다. 부호는 없다고 판단한다.

* `offset` \<Number> 위치
* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.addWord(0xffff);
buf.addWord(-0xfff);
buf.getWord(0); //4294967295
buf.getShort(2); //-4095
```

<br/>

### nextBinary( size )

현재의 offset 부터 size 만큼의 binary값을 배열로 반환한다.

* `size` \<Number> 길이
* **Returns** \<Array>

```js
var buf = new ABuffer(10);
buf.addBinary(10, '0123456789');
buf.setOffset(0);
buf.nextBinary(5); // [3,4,5,6,7]
```

<br/>

### nextByte()

현재의 offset 으로부터 byte value 를 얻어온다.

* **Returns** \<Byte>

```js
var buf = new ABuffer(10);
buf.setByte(1, 255);
buf.setOffset(1);
buf.nextByte(); // 255
```

<br/>

### nextDWord()

현재의 offset 부터 2 byte 만큼의 바이너리 이진수를 Number타입 숫자로 변환하여 리턴한다. 부호는 없다고 판단한다.

* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.addDWord(0xffffffff);
buf.setOffset(0);
buf.nextDWord(); //4294967295
```

<br/>

### nextInt( size )

현재의 offset 부터 4 byte 만큼을 정수로 변환하여 리턴한다.

* `size` \<Number> 길이
* **Returns** \<Integer>

```js
var buf = new ABuffer(10);
buf.addDWord(-256);
buf.setOffset(0);
buf.nextInt();
```

<br/>

### nextIpString()

현재의 offset 부터 12자리만큼을 IPv4 주소형태의 문자열로 변환하여 반환한다. 예를 들어 "127.0.0.1"

* **Returns** \<String>

```js
var buf = new ABuffer(12);
buf.addOriString(12, '127001010100');
buf.setOffset(0);
buf.nextIpString();
```

<br/>

### nextOriString( size, noTrim )

현재의 offset 부터 size 만큼의 문자열을 얻어온다. this.charset 을 셋팅했지만 디코딩이 되지 말아야 할 경우 사용되어진다. noTrim 값에 따라 앞뒤 공백이 trim 처리되거나 처리되지 않고 리턴된다.

* `size` \<Number> 길이
* `noTrim` \<Boolean> trim 여부
* **Returns** \<String>

```js
var buf = new ABuffer(11);
buf.setOriString(0, 1, 'Z');
buf.addOriString(10, 'abcdefghij');
buf.getOriString(0, 1); // 'Z'
buf.nextOriString(10); // 'abcdefghij'
```

<br/>

### nextParseFloat( size )

현재의 offset 부터 size 만큼의 문자열을 읽어 부동소수점 숫자로 변환하여 리턴한다.

* `size` \<Number> 길이
* **Returns** \<Float>

```js
var buf = new ABuffer(10);
buf.setSNumString(0, 10, -123.1);
buf.setOffset(0);
buf.nextParseFloat(10); // -123.1
buf.getString(0, 10); // -0000123.1
```

<br/>

### nextParseInt( size )

현재의 offset 부터 size 만큼의 문자열을 읽어 정수로 변환하여 리턴한다.

* `size` \<Number> 길이
* **Returns** \<Int>

```js
var buf = new ABuffer(10);
buf.setSNumString(0, 10, -123.1);
buf.setOffset(0);
buf.nextParseInt(10); // -123
buf.getString(0, 10); // -0000123.1
```

<br/>

### nextShort()

현재 offset 부터 2 byte 만큼의 바이너리 이진수를 Number타입 숫자로 변환하여 리턴한다. 최상위 비트를 부호 비트라고 판단한다.

* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.addWord(-0xfff);
buf.setOffset(0);
buf.nextShort(); //-4095
```

<br/>

### nextString( size, noTrim )

현재의 offset 부터 size 만큼의 문자열을 얻어온다. this.charset 이 셋팅되어져 있으면 디코딩 과정을 거친후 리턴되어 진다. noTrim 값에 따라 앞뒤 공백이 trim 처리되거나 처리되지 않고 리턴된다.

* `size` \<Number> 길이
* `noTrim` \<Boolean> trim 여부

```js
var buf = new ABuffer(10);
buf.setCharset('euc-kr');
buf.setString(0, 5, '샘플 ');
buf.setOffset(0);
buf.nextString(5, true);
```

<br/>

### nextStringTo( endValue )

현재의 offset 부터 endValue 가 있는 곳까지의 문자열을 얻어온다. this.charset 이 셋팅되어져 있으면 디코딩 과정을 거친후 리턴되어 진다.

* `endValue` \<Number> Byte

```js
var buf = new ABuffer(10);
buf.setString(0, 5, 'abcd$efgh$');
buf.getStringTo(0, '$'.charCodeAt(0)); // abcd
buf.nextStringTo('$'.charCodeAt(0)); // efgh
```

<br/>

### nextType( size, unsigned )

현재 offset 부터 size 만큼의 바이너리 이진수를 Number타입 숫자로 변환하여 리턴한다. signed 인 경우 2의보수 처리한다.

* `size` \<Number> 길이
* `unsigned` \<Boolean> 부호여부
* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.addType(0, 2, 10);
buf.setOffset(0);
buf.nextType(2, true);
```

<br/>

### nextWord()

현재 offset 부터 2 byte 만큼의 바이너리 이진수를 Number타입 숫자로 변환하여 리턴한다. 부호는 없다고 판단한다.

* **Returns** \<Number>

```js
var buf = new ABuffer(10);
buf.addWord(0xffff);
buf.setOffset(0);
buf.nextWord(0); //65535
```

<br/>

### printBuffer( inx, size, radix )

버퍼의 특정 위치부터 size만큼 문자열로 만들어 브라우저의 디버깅 콘솔에 표현하고, 문자열을 반환한다. radix가 있는 경우 값을 진수값으로 표현한다. 예를 들어 15인 경우 2인 경우 1111, 8인 경우 17, 16인 경우 f로 표현한다.

* `inx` \<String> 시작 위치
* `size` \<Number> 길이
* `radix` \<String> 옵션. 숫자를 나타내는데 사용할 진수. 2와 36사이의 정수여야 한다.
* **Returns** \<String>

```js
var buf = new ABuffer(10);
buf.printBuffer(0, buf.getBufSize(), 10);
buf.printBuffer(5, 10, 16);
```

<br/>

### printBySize( sizeInfo, offset, radix )

offset 위치에서부터 사이즈 정보 배열(예. [ 5, 10, 2, 3, 10 ... ] ) 에 들어있는 항목의 크기만큼씩 문자열로 만들어 브라우저의 디버깅 콘솔에 표현하고, 문자열을 반환한다. radix가 있는 경우 값을 진수값으로 표현한다. 예를 들어 15인 경우 2인 경우 1111, 8인 경우 17, 16인 경우 f로 표현한다.

* `sizeInfo` \<Array> 사이즈 정보 배열
* `offset` \<Number> 시작 위치
* `radix` \<Number> 옵션. 숫자를 나타내는데 사용할 진수. 2와 36사이의 정수여야 한다.
* **Returns** \<String>

```js
var buf =  new ABuffer(10);
buf.setBinary(0, 10, '0123456789');
buf.printBySize([1,2,3], 4, 16);
```

<br/>

### setBinary( offset, size, value )

버퍼의 특정 offset 부터 size 만큼 문자열 또는 배열의 binary값을 셋팅한다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* `value` \<String or Array>

```js
var buf =  new ABuffer(10);
buf.setBinary(3, 3, [1,2,3]); // buf.setBinary(3, 3, '123');
buf.getBinary(3, 3);
```

<br/>

### setBuffer( buf )

직접 생성한 Uint8Array 버퍼 객체를 셋팅한다.

* `buf` \<Array> Uint8Array

```js
var buf =  new ABuffer(10);
var uarr = new Uint8Array([48, 96, 144, 192, 240]);
buf.setBuffer(uarr);
buf.printBuffer(0, null, 16); //"30 60 90 c0 f0 "
```

<br/>

### setBufferByString( str )

str 값을 인코딩 처리하여 버퍼에 세팅한다. 반드시 인코더가 있어야 한다.

* `str` \<String> 버퍼에 세팅할 문자

```js
var buf = new ABuffer(10);
buf.setCharset('euc-kr');
var str = '0123456789가나다라마바사';
buf.setBufferByString(str);
buf.getString(0, 24); // 10+(7*2) 숫자:1byte, 한글:2byte
```

<br/>

### setByte( offset, value )

버퍼의 특정 offset 에 byte value 를 셋팅한다.

* `offset` \<Number> 위치
* `value` \<All> Byte

```js
var buf = new ABuffer(10);
buf.setByte(8, 0xff);
buf.getByte(8);
```

<br/>

### setChar( offset, value )

버퍼의 특정 offset 에 char value 를 셋팅한다. 하나의 문자열을 넘기면 char code 로 변환하여 셋팅된다.

* `offset` \<Number> 위치
* `value` \<String> 값

```js
var buf = new ABuffer(10);
buf.setChar(9, 'Z');
buf.getString(9, 1);
```

<br/>

### setCharset( charset )

String 변환시 적용할 인코딩 값을 셋팅한다. 'utf-8', 'euc-kr' ...

* `charset` \<String> 'utf-8', 'euc-kr' ...

```js
var buf = new ABuffer(10);
buf.setCharset('euc-kr');
```

<br/>

### setDataSize( size )

버퍼 사이즈가 아닌 데이터 사이즈를 세팅한다.

* `size` \<Number> 데이터 사이즈

```js
var buf = new ABuffer(10);
buf.setDataSize(8);
```

<br/>

### setDWord( offset, value )

버퍼의 특정 offset 부터 4 byte 공간에 value의 메모리값을 셋팅한다. 부호가 음수인 경우 2의 보수법으로 처리한다.

* `offset` \<Number> 위치
* `value` \<String or Number> 값

```js
var buf = new ABuffer(10);
buf.setDWord(1, 0xffffffff);
buf.getDWord(1); //4294967295
```

<br/>

### setEmptyChar( emptyChar )

문자열 세팅함수에서 빈자리를 채우는 문자를 지정한다.

* `emptyChar` \<String> 1 byte 문자

```js
var buf = new ABuffer(10);
buf.setEmptyChar(0x20);
```

<br/>

### setEmptyNumChar( emptyNumChar )

숫자 세팅함수에서 빈자리를 채우는 문자를 지정한다.

* `emptyNumChar` \<String> 1 byte 문자

```js
var buf = new ABuffer(10);
buf.setEmptyNumChar(0x30);
```

<br/>

### setNumString( offset, size, value )

버퍼의 특정 offset 에 숫자를 문자열로 변환하여 셋팅한다. size 를 기준으로 우측정렬하여 문자열을 셋팅하고 남은 빈자리는 앞에서부터 this.emptyNumChar 로 채운다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* `value` \<String or Number> 값

```js
var buf = new ABuffer(10);
buf.setNumString(2,5, 123);
buf.getString(2, 5); // '00123'
```

<br/>

### setOffset( offset )

현재의 버퍼 offset 값을 셋팅한다. this.offset 참조.

* `offset` \<String> 위치

```js
var buf = new ABuffer(10);
buf.setOffset(4);
var ofs = buf.getOffset(); //4
```

<br/>

### setOriString( offset, size, value )

버퍼의 특정 offset 에 문자열을 셋팅한다. size 를 기준으로 문자열을 셋팅하고 남은 빈자리는 this.emptyChar로 채운다. this.charset 을 셋팅했지만 인코딩이 되지 말아야 할 경우 사용한다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* `value` \<String> 값

```js
var buf = new ABuffer(11);
buf.setOriString(0, 1, 'Z');
buf.addOriString(10, 'abcdefghij');
buf.getOriString(0, 1); // 'Z'
buf.nextOriString(10); // 'abcdefghij'
```

<br/>

### setSNumString( offset, size, value )

버퍼의 특정 offset 에 숫자를 문자열로 변환하여 셋팅한다. 부호를 offset 위치에  표현하고 size 를 기준으로 우측정렬하여 문자열을 셋팅하고 남은 빈자리는 앞에서부터 this.emptyNumChar 로 채운다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* `value` \<String or Number> 값

```js
var buf = new ABuffer(10);
buf.setSNumString(2, 4, -123);
buf.getString(2, 4); // '-123'
```

<br/>

### setString( offset, size, value )

버퍼의 특정 offset 에 문자열을 셋팅한다. size 를 기준으로 문자열을 셋팅하고 남은 빈자리는 this.emptyChar로 채운다. this.charset 이 셋팅되어져 있으면 인코딩 과정을 거친후 셋팅된다.

* `offset` \<Number> 위치
* `size` \<Number> size 가 1보다 작으면 value 의 길이만큼 셋팅된다.
* `value` \<String> 값

```js
var buf = new ABuffer(10);
buf.setCharset('euc-kr');
buf.setString(0, 4, '샘플');
buf.getString(0, 4);
```

<br/>

### setType( offset, size, value )

버퍼의 특정 offset 부터 size 만큼 value의 메모리 값을 셋팅한다. 부호가 음수인 경우 2의 보수법으로 처리한다.

* `offset` \<Number> 위치
* `size` \<Number> 길이
* `value` \<String or Number> 값

```js
var buf = new ABuffer(10);
buf.setType(0, 2, 10);
buf.getType(0, 2);
```

<br/>

### setWord( offset, value )

버퍼의 특정 offset 부터 2 byte 공간에 value의 메모리값을 셋팅한다. 부호가 음수인 경우 2의 보수법으로 처리한다.

* `offset` \<Number> 위치
* `value` \<String or Number> 값

```js
var buf = new ABuffer(10);
buf.setWord(2, 0xffff);
buf.getWord(2); // 65535
```

<br/>

### subArray( start, end )

this.buf[start] ~ this.buf[end-1] 까지를 포함한 버퍼 참조자를 리턴한다. 리턴된 버퍼객체는 인덱스를 0부터 접근하지만 참조자가 리턴되므로 버퍼 원본을 바라보고 있다.

* `start` \<String> 시작위치
* `end` \<String> 종료위치
* **Returns** \<Uint8Array>


```js
var buf = new ABuffer(10);
buf.addBinary(10, [0,1,2,3,4,5,6,7,8,9]);
buf.subArray(3, 6); // [3, 4, 5]
```

<br/>

### subDataArray()

this.buf[0] ~ this.buf[this.dataSize] 까지를 포함한 버퍼 참조자를 리턴한다. 리턴된 버퍼객체는 인덱스를 0부터 접근하지만 참조자가 리턴되므로 버퍼 원본을 바라보고 있다.

* **Returns** \<Uint8Array> this.buf 참조배열

<br/>

### getBase64String( offset, size )

offset 부터 size 만큼의 Uint8Array 를 base64 encoding 한 값을 얻는다.

* `offset` \<Number> 위치
* `size` \<Number> 길이

<br/>
<br/>
