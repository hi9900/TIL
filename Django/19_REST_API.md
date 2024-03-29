# REST API

## API

- Application Programming Interface

- 애플리케이션과 프로그래밍으로 소통하는 방법

  개발자가 복잡한 기능을 보다 쉽게 만들 수 있도록 프로그래밍 언어로 제공되는 구성

- API를 제공하는 애플리케이션과 다른 소프트웨어 및 하드웨어 등의 것들 사이의 간단한 계약(인터페이스)이라고 볼 수 있음

- API는 복잡한 코드를 추상화하여 대신 사용할 수 있는 몇 가지 더 쉬운 구문을 제공

## Web API

- 웹 서버 또는 웹 브라우저를 위한 API

- 현재 웹 개발은 모든 것을 하나부터 열까지 직접 개발하기보다 여러 Open API를 활용하는 추세

- 대표적인 Third Party Open API 서비스 목록

  - Youtube API, Naver Papago API, Kakao Map API

- API는 다양한 타입의 데이터를 응답

  - HTML, XML, JSON 등

> ### Open API

  - 개발자라면 누구나 사용할 수 있도록 공개된 API

  - 개발자에게 사유 응용 소프트웨어나 웹 서비스의 프로그래밍적 권한을 제공

---

## REST

- Representational State Transfer

- API Server를 개발하기 위한 일종의 소프트웨어 설계 방법론

- 소프트웨어 아키텍쳐 디자인 제약 모음 (a group of software architecture design constraints)

- REST 원리를 따르는 시스템을 RESTful 하다고 부름

- REST의 기본 아이디어는 리소스 즉, 자원

  - 자원을 정의하고 자원에 대한 주소를 지정하는 전반적인 방법을 서술

### REST에서 자원을 정의하고 주소를 지정하는 방법

1. 자원의 식별

  - URI

2. 자원의 행위

  - HTTP Method

3. 자원의 표현

  - 자원과 행위를 통해 궁극적으로 표현되는 (추상화된) 결과물

  - JSON으로 표현된 데이터를 제공

### JSON

- JSON is a lightweight data-interchange format

- JavaScript의 표기법을 따른 단순 문자열

- 파이썬의 dictionary, 자바스크립트의 object처럼 C 계열의 언어가 갖고 있는 자료구조로 쉽게 변환할 수 있는 key-value 형태의 구조를 갖고 있음

  그렇다고 JSON이 파이썬의 dictionary와 같지 않음

- 사람이 읽고 쓰기 쉽고, 기계가 파싱(해석&분석)하고 만들어내기 쉽기 때문에 현재 API에서 가장 많이 사용하는 데이터 타입

---

## REST 정리

- 자원을 정의하고 자원에 대한 주소를 지정하는 방법의 모음

1. 자원을 식별 - URI

2. 자원에 대한 행위 - HTTP Methods

3. 자원을 표현 - JSON

- 설계 방법론은 지키지 않았을 때 잃는 것보다 지켰을 때 얻는 것이 훨씬 많음

  단, 설계 방법론을 지키지 않더라도 동작 여부에 큰 영향을 미치지는 않음

  말 그대로 방법론일 뿐이며 규칙이나 규약은 아님