# LocalizeManager

스파이더젠으로 만든 프로젝트를 여러지역의 언어로 지원하기 위한 라이브러리이다. 자세한 사용 방법은 [이곳](../../guide/07.%20다국어%20지원%20기능(Localizing).md)을 참조한다.

<br/>

## Class Variables

### LocalizeManager.LANGUAGE

현재 언어를 가지고 있는 변수이다. 브라우저의 언어설정에 의해 자동으로 설정된다. 브라우저의 설정에 상관없이 바꾸고 싶다면 직접 언어코드를 변수에 넣으면 된다.

```js
//국가별 표준 언어 코드값을 넣는다.
LocalizeManager.LANGUAGE = 'ko';
LocalizeManager.LANGUAGE = 'ch';
```

## Instance Variables

<br/>

## Class Methods

### LocalizeManager.getLocalizedStr( key )

현재 설정된 언어 맵에서 매개변수 key에 매핑되는 값을 반환하는 함수이다.

- `key` \<String> 

```js
console.log(LocalizeManager.LANGUAGE);
// -> ko
//현재 설정된 언어값이 한국어(ko) 라고 가정했을 때
LocalizeManager.getLocalizedStr('sun');
//맵에서 키값인 sun에 맵핑된 한국어 값을 가져와서 리턴한다.
```

<br/>

## Instance Methods

<br/>