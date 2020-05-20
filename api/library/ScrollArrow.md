# ScrollArrow
**Extends**:

스크롤 표현 클래스

<br/>

## Properties


### bottomClassName \<String>

아래 방향 화살표 CSS 클래스

<br/>

### checkAlready \<Boolean>

현재 스크롤 가능 여부를 판단하여 스크롤 화살표를 표현했는지 여부를 나타낸다.

<br/>

### leftClassName \<String>

왼쪽 방향 화살표 CSS 클래스

<br/>

### rightClassName \<String>

오른쪽 방향 화살표 CSS 클래스

<br/>

### scrlDir \<String>

스크롤 방향을 나타낸다. 방향에는 'vertical'과 'horizontal'이 있다.

<br/>

### scrlElement \<HTML Object>

스크롤을 감지할 엘리먼트

<br/>

### topClassName \<String>

위 방향 화살표 CSS 클래스

<br/>
<br/>

## Instance Methods

### apply( scrlElement )

스크롤을 감지할 엘리먼트를 지정하고, setArrow 함수로 설정한 스크롤 방향에 맞게 화살표가 표현되도록 적용한다.

- `scrlElement` \<HTML Object> 스크롤을 감지할 엘리먼트

<br/>

### autoDisappear()

스크롤 화살표를 서서히 사라지게 한다.

<br/>

### isMoreScrollBottom()

현재 스크롤 위치에서 아래쪽으로 더 스크롤 할 수 있는지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isMoreScrollLeft()

현재 스크롤 위치에서 왼쪽으로 더 스크롤 할 수 있는지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isMoreScrollRight()

현재 스크롤 위치에서 오른쪽으로 더 스크롤 할 수 있는지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### isMoreScrollTop()

현재 스크롤 위치에서 위쪽으로 더 스크롤 할 수 있는지 여부를 반환한다.

- **Returns** \<Boolean>

<br/>

### onScrollFirst()

첫번째(위쪽 또는 왼쪽) 화살표를 숨기고 두번째(아래쪽 또는 오른쪽) 화살표를 보여준다.

<br/>

### onScrollSecond()

첫번째(위쪽 또는 왼쪽) 화살표를 보여주고 두번째(아래쪽 또는 오른쪽) 화살표를 숨긴다.

<br/>

### scrollHoriProc()

수평방향 화살표가 표현되도록 처리한다.

<br/>

### scrollVertProc()

수직방향 화살표가 표현되도록 처리한다.

<br/>

### setArrow( dir, arrow1, arrow2 )

스크롤 화살표의 방향과 수직인 경우 위아래 화살표 jQuery 객체를 수평인 경우 좌우 화살표 jQuery 객체를 지정한다. 화살표 jQuery 객체를 지정하지 않으면 기본 화살표를 생성한다.

- `dir` \<String> 스크롤 방향. 'vertical' 또는 'horizontal'
- `arrow1` \<jQuery Object> 위쪽 또는 왼쪽 화살표 jQuery 객체 또는 null
- `arrow2` \<jQuery Object> 아래쪽 또는 오른쪽 화살표 jQuery 객체 또는 null

<br/>

### visibleCheckHori()

수평 방향의 현재 스크롤 가능 상태에 맞게 스크롤 화살표를 표현한다. 예를 들어 오른쪽으로 스크롤이 가능한 경우 오른쪽쪽 스크롤 화살표를 보여주고 서서히 사라지게 한다.

<br/>

### visibleCheckVert()

수직 방향의 현재 스크롤 가능 상태에 맞게 스크롤 화살표를 표현한다. 예를 들어 아래로 스크롤이 가능한 경우 아래쪽 스크롤 화살표를 보여주고 서서히 사라지게 한다.

<br/>
<br/>
