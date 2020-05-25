# TabKeyController

AContainer단위로 탭 이동을 하게 만드는 라이브러리. 아래의 함수들은 모두 내부에서 자동으로 호출되므로 직접 호출할 필요는 없다.

<br/>

## Class Variables

<br/>

## Instance Variables

### componentMap \<Array>

컴포넌트를 배열로 가지고 있다. HTML문서의 Dom Tree의 방식처럼 저장되므로 Depth가 존재한다.

<br/>

### tabIndexArr \<Array>

TabIndex를 빠르게 검색하기 위한 배열

<br/>

## Class Methods

<br/>

## Instance Methods

### init( rootView, noFocus )

AContainer가 처음 init 될때 자동으로 호출된다. 특정상황에서는 init시 포커스되지 않게 할수 있다. (ex. AWindow가 열릴 때 포커스를 주지않는 옵션)

- `rootView` \<AView> AContainer의 rootView
- `noFocus` \<String> init시점에 포커스 여부.

<br/>

### findNextTab( comp, isShift)

다음 탭이 가능한 컴포넌트를 찾는다. 없으면 탭이 가능한 첫번째 컴포넌트로 포커스를 이동한다.

- `comp` \<AComponent> 현재 컴포넌트
- `isShift` \<Boolean> 쉬프트키 눌림 여부

<br/>

### addCompMap( acomp, owner )

뷰에서 호출한다. 탭키컨트롤러 배열로 컴포넌트맵을 만든다.

- `acomp` \<AComponent> 컴포넌트
- `owner` \<AComponent> owner 컴포넌트

<br/>

### saveOwnerMap( owner )

동적로드된 경우에는 정보들을 따로 모아두고 있는데 모아 뒀던 탭인덱스 배열을 처리하는 함수이다.

- `owner` \<AComponent> owner 컴포넌트

<br/>

### makeTabIndexArr()

트리탐색은 for문이 겹쳐서 매번 탭마다 부하를 주기때문에 이를 줄이기 위해 빠른탐색 배열을 최초1회 만들어둔다.

<br/>
