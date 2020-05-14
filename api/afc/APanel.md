# APanel
**Extends**: [`AContainer`](AContainer.html#AContainer)

패널의 역할은 윈도우와 같이 팝업의 기능은 없고 네비게이터에 들어갈 수 없으며 <br/>오로지 다른 컨테이너의 부분 컨테이너 역할만 할 수 있다. <br/>→ contaier split 시에 사용한다.<br/>open 함수를 호출하여 부모의 불특정 영역에 새로운 컨테이너를 배치할 수 있다.

<br/>

## Instance Methods

### init( context )

- `context` \<String> 컴포넌트 생성 정보

```js
var panel = new APanel();
panel.init();
```

<br/>
