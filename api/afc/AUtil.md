# AUtil
> **Extends**

유용한 기능들 모아둔 클래스

<br/>

## Class Methods

### AUtil.OppositeColor( r, g, b )

반대색상을 가져온다.

* `r` \<Number> Red
* `g` \<Number> Green
* `b` \<Number> Blue
* **Returns** \<Array> [R, G, B]

```js
AUtil.OppositeColor(255, 0, 0); //[0, 255, 255];
```

<br/>

### AUtil.RgbToHsl( r, g, b )

rgb 값을 hsl 로 변경한다.

* `r` \<Number> Red
* `g` \<Number> Green
* `b` \<Number> Blue
* **Returns** \<Array> [h(색상), s(채도), l(명도)] 

```js
AUtil.RgbToHsl(255, 0, 0); //[0, 1, 0.5];
```

<br/>

### AUtil.autoShrink( ele, info )

info 의 최대 글자수, 기본 글자크기, 단위값으로 엘리먼트의 글자수에 맞게 글자크기를 조절한다.

* `ele` \<HTMLElement> 엘리먼트
* `info` \<Object> {maxChar:15, fontSize:24, unit:'px'}

```js
var ele = this.lbl.element;
AUtil.autoShrink(ele, {maxChar:15, fontSize:24, unit:'px'});
```

<br/>

### AUtil.extractExtName( path )

경로에서 확장자를 추출한다.

* `path` \<String> 경로
* **Returns** \<String> 확장자

```js
AUtil.extractExtName('C:/path1/path2/path3/filename.ext');
//ext
```

<br/>

### AUtil.extractFileName( path, split )

경로에서 파일명을 추출한다.

* `path` \<String> 경로
* `split` \<String> 분리 기호
* **Returns** \<String> 파일명

```js
AUtil.extractFileName('C:/path1/path2/path3/filename.ext', '/');
//filename.ext
```

<br/>

### AUtil.extractFileNameExceptExt( path, split )

경로에서 확장자를 제외한 파일명을 추출한다.

* `path` \<String> 경로
* `split` \<String> 분리 기호
* **Returns** \<String> 확장자를 제외한 파일명

```js
AUtil.extractFileNameExceptExt('C:/path1/path2/path3/filename.ext', '/');
//filename
```

<br/>

### AUtil.extractLoc( path, split )

경로에서 파일명을 제외한 경로을 추출한다.

* `path` \<String> 경로
* `split` \<String> 분리 기호
* **Returns** \<String> 파일명 제외 경로

```js
AUtil.extractLoc('C:/path1/path2/path3/filename.ext', '/');
//C:/path1/path2/path3/
```

<br/>

### AUtil.filePathExceptExt( fileName )

경로에서 확장자를 제외한 경로를 추출한다.

* `fileName` \<String> 경로
* **Returns** \<String> 확장자 제외 경로

```js
AUtil.filePathExceptExt('C:/path1/path2/path3/filename.ext', '/');
//C:/path1/path2/path3/filename
```

<br/>

### AUtil.findNextByTagName( curDom, tagName )

curDom 기준으로 태그명에 해당하는 가장 가까운 다음 엘리먼트를 가져온다.

* `curDom` \<HTMLElement> 엘리먼트
* `tagName` \<String> 태그명
* **Returns** \<HTMLElement> 다음 엘리먼트

```js
var curDom = this.lbl.element;
AUtil.findNextByTagName(curDom, 'DIV');
```

<br/>

### AUtil.findPrevByTagName( curDom, tagName )

curDom 기준으로 태그명에 해당하는 가장 가까운 이전 엘리먼트를 가져온다.

* `curDom` \<HTMLElement> 엘리먼트
* `tagName` \<String> 태그명
* **Returns** \<HTMLElement> 이전 엘리먼트

```js
var curDom = this.lbl.element;
AUtil.findPrevByTagName(curDom, 'DIV');
```

<br/>

### AUtil.formatDate( dateStr )

200518 -> 20:05:18

* `dateStr` \<String> 날짜 표현 문자열
* **Returns** \<String> 날짜

<br/>

### AUtil.isExistFile( fileUrl )

경로에 파일의 존재유무를 가져온다.

* `fileUrl` \<String>> 파일경로
* **Returns** \<Boolean> 파일 존재유무

<br/>

### AUtil.makeNumString( size, value )

value 를 size 만큼의 길이의 숫자형태 문자열로 변경한다. 모자라는 부분은 앞부분에 "0" 으로 채운다.

* `size` \<Number> 길이
* `value` \<String> 값
* **Returns** \<String> 숫자형태 문자열

```js
var value = '12345';
AUtil.makeNumString(10, value); //'0000012345'
```

<br/>

### AUtil.makeStack( targetDom )

targetDom 에 빈 div 엘리먼트를 생성하여 추가한다.
<br/> undo, redo 같은 기능에서 엘리먼트를 잠시 옮겨놓을 때 사용한다.

* `targetDom` \<jQueryObject> div 엘리먼트 추가할 jQuery 객체
* **Returns** \<jQueryObject> div jQuery 객체

```js
var undoStack = AUtil.makeStack(this.view.$ele);
var redoStack = AUtil.makeStack(this.view.$ele);
undoStack.append(this.newLbl.$ele);
```
<br/>

### AUtil.optionHelper( obj, option, noOverwrite )

obj.option 변수 객체에 option 객체의 정보를 덮어쓴다.
<br/>noOverwrite 가 true 이면, 기존의 값이 존재할 경우 덮어쓰지 않는다.

* `obj` \<String>> 옵션 정보를 객체
* `option` \<Object> 옵션 객체
* `noOverwrite` \<Boolean>> 덮어쓰기 유무

```js
var obj = { option: { option2: 'noOverwrite' }};
var option = {option1: true, option2: false, option3: 'optiondata'};
AUtil.optionHelper(obj, option, true);
```

<br/>

### AUtil.randInt( min, max )

min 과 max 사이의 정수값을 가져온다.

* `min` \<Number> 최소값
* `max` \<Number> 최대값
* **Returns** \<Number> 두 값 사이의 랜덤 정수

```js

```

<br/>

### AUtil.readTextFile( filePathName )

파일 내용을 가져온다.

* `filePathName` \<String>> 파일경로
* **Returns** \<String> 파일 내용

```js

```

<br/>

### AUtil.shuffle( arr )

배열의 요소들의 위치 무작위로 섞는다.

* `arr` \<Array> 배열

```js

```

<br/>
<br/>

# CallBackDone
> **Extends**

## Class Method

### CallbackDone.begin()

콜백함수를 여러 프로세스가 완료된 후에 호출되게 하는 기능
<br/>특정 프로세스가 시작되었을 떄 호출한다.
<br/>[기능 사용방법은 여기를 참고](#-CallbackDone.waitAll-endCallback-)

<br/>

### CallbackDone.end()

콜백함수를 여러 프로세스가 완료된 후에 호출되게 하는 기능
<br/>특정 프로세스가 완료되었을 떄 호출한다.
<br/>[기능 사용방법은 여기를 참고](#-CallbackDone.waitAll-endCallback-)

<br/>

### CallbackDone.waitAll( endCallback )

콜백함수를 여러 프로세스가 완료된 후에 호출되게 하는 기능
<br/>여러 프로세스를 동작하기 전에 종료콜백을 지정한다.

```js
CallbackDone.waitAll(function(){ console.log('all process done'); });

CallbackDone.begin();
CallbackDone.begin();
CallbackDone.begin();

var i=0;
var interval = setInterval(function(){ console.log((++i)+'s later'); }, 1000);
setTimeout(function(){ clearInterval(interval); CallbackDone.end(); }, 5000);
setTimeout(function(){ CallbackDone.end(); }, 3000);
setTimeout(function(){ CallbackDone.end(); }, 4000);

//5s later, all process done
```

<br/>

# AHistoryInfo
> **Extends**

## Instance Method

### canGoNext()

다음 히스토리가 있는지 체크한다.

* **Returns** \<Boolean> 다음 히스토리 유무

<br/>

### canGoPrev()

이전 히스토리가 있는지 체크한다.

* **Returns** \<Boolean> 이전 히스토리 유무

<br/>

### clearHistory()

히스토리 정보를 초기화한다.

```js
var hisInfo = new AHistoryInfo();
hisInfo.clearHistory();
```

<br/>

### nextInfo()

다음 히스토리 정보를 가져온다.

* **Returns** \<All> 다음 히스토리 정보

<br/>

### prevInfo()

이전 히스토리 정보를 가져온다.

* **Returns** \<All> 이전 히스토리 정보

<br/>

### pushInfo( info )

히스토리를 저장한다.

* `info` \<All> 히스토리 관련 정보

```js
var hisInfo = new AHistoryInfo();
hisInfo.pushInfo('first history');
hisInfo.pushInfo('second history');
hisInfo.prevInfo(); //first history
hisInfo.nextInfo(); //second history
```

<br/>

