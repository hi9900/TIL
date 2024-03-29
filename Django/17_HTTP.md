# HTTP

Hyper Text Transfer Protocol

HTML 문서와 같은 리소스(resource, 자원)들을 가져올 수 있도록 하는 프로토콜(규칙, 약속)

웹 상에서 컨텐츠를 전송하기 위한 약속

웹에서 이루어지는 모든 데이터 교환의 기초가 됨

"클라이언트-서버 프로토콜" 이라고도 부름

클라이언트와 서버는 다음과 같은 개별적인 메시지 교환에 의해 통신

  - 요청(request)

    클라이언트에 의해 전송되는 메시지

  - 응답(response)

    서버에서 응답으로 전송되는 메시지

실제로는 브라우저와 요청을 처리하는 서버 사이에는 더 많은 기술 및 컴퓨터들이 존재한다.

## HTTP 특징

- **Stateless(무상태)**

  - 동일한 연결(connection)에서 연속적으로 수행되는 두 요청 사이에 링크가 없음

  - 즉, 응답을 마치고 연결을 끊는 순간 클라이언트와 서버 간의 통신이 끝나며 상태 정보가 유지되지 않음

- 이는 특정 페이지와 일관되게 상호작용하려는 사용자에게 문제가 될 수 있으며,

  (예를 들어 e-commerce에서 장바구니를 사용하는 경우)

  이를 해결하기 위해 쿠키와 세션을 사용해 서버 상태를 요청과 연결하도록 함

## HTTP Request Methods

- 리소스에 대한 행위(수행하고자 하는 동작)를 정의

- 즉, 리소스에 대해 수행할 원하는 작업을 나타내는 메서드 모음을 정의

- HTTP verbs라고도 함

### 대표 HTTP Request Methods

  1. GET

  - 서버에 리소스의 표현을 요청

  - GET을 사용하는 요청은 데이터만 검색해야 함

  2. POST

  - 데이터를 지정된 리소스에 제출

  - 서버의 상태를 변경

  3. PUT

  - 요청한 주소의 리소스를 수정

  4. DELETE

  - 지정된 리소스를 삭제

> ### 리소스(resource)

  - HTTP 요청의 대상을 리소스(resource, 자원)라고 함

## HTTP response status codes

- 특정 HTTP 요청이 성공적으로 완료되었는지 여부를 나타냄

- 응답은 5개의 그룹으로 나뉨

  1. Informational responses (100-199)

  2. Successful responses (200-299)

  3. Redirection messages (300-399)

  4. Client error responsses (400-499)

  5. Server error responses (500-599)