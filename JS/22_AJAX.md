# AJAX

Asynchronous JavaScript And XML (비동기식 JavaScript와 XML)

비동기 통신 웹 개발기술

비동기 통신을 이용하면 화면 전체를 새로고침 하지 않아도 서버로 요청을 보내고, 데이터를 받아 화면의 일부분만 업데이트 가능

비동기 웹 통신을 위한 라이브러리 중 하나가 Axios

## AJAX 특징

- 페이지 전체를 reload(새로고침)를 하지 않고서도 수행되는 "비동기성"

- 서버의 응답에 따라 전체 페이지가 아닌 일부분만을 업데이트 할 수 있음

  1. 페이지 새로고침 없이 서버에 요청

  2. 서버로부터 응답(데이터)을 받아 작업을 수행

> ### XHR

  - XMLHttpRequest

  - AJAX 요청을 생성하는 JavaScript API

  - XHR의 메서드로 브라우저와 서버 간 네트워크 요청을 전송할 수 있음

  - Axios는 손쉽게 XHR을 보내고 응답 결과를 Promise 객체로 반환해주는 라이브러리