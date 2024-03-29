## props를 통해 컴포넌트에게 값 전달

- props는 properties의 줄임말로, 어떠한 값을 컴포넌트에게 전달해줘야 할 때 사용한다.

### props의 기본 사용법

- 컴포넌트에게 전달되는 props는 파라미터를 통해 조회할 수 있다.

- props는 객체 형태로 전달되며, 만약 `name` 값을 조회하고 싶다면 `props.name`을 조회하면 된다.

### 여러개의 props, 비구조화 할당

- props 내부의 값을 조회할 때마다 `props.`을 입력하는 데,

  함수의 파라미터에서 비구조화 할당 (또는 구조 분해) 문법을 사용하면 코드를 좀 더 간결하게 작성할 수 있다.

### defaultProps로 기본값 설정

- 컴포넌트에 props를 지정하지 않았을 때 기본적으로 사용할 값을 설정하고 싶다면, 컴포넌트에 `defaultProps`라는 값을 설정하면 된다.

### props.children

- 컴포넌트 태그 사이에 넣은 값을 조회하고 싶을 땐, `props.children`을 조회하면 된다.