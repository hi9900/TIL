# Websocket 통신 실습

## 개요

- 기본적으로 HTTP 통신은 클라이언트가 요청(Request)을 보내면 서버가 응답(Response)하는 구조이다.

  이로 인해 서버는 능동적으로 클라이언트에 먼저 데이터를 전송할 수 없다.

  따라서 클라이언트는 사버의 데이터를 얻기 위해 항상 요청을 먼저 해야하고, 서버는 이에 수동적으로 응답해주는 구조로 구성되어 있다.

- 이에 반해 WebSocket 통신은 클라이언트와 서버를 연결하고 실시간으로 통신이 가능하도록 하는 기술이다.

  앞서 설명한 HTTP와는 다르게 별도의 요청을 보내지 않고도 데이터를 수신할 수 있다.

  요청을 보낼 필요 없이 바로 메시지를 수신할 수 있다.

  지속적으로 업데이트되는 정보를 수신해야 하는 채팅이나 주식 보고서에 WebSocket 통신을 사용하는 이유이다.

  이 프로토콜은 정보를 동시에 송수신할 수 있으므로 정보 교환이 더 빨라진다.

- WebSocket에서 클라이언트와 서버 간의 연결은 둘 중 하나에 의해 종료되거나 시간 초과에 의해 닫힐 때까지 열린 상태로 유지된다.

  그리고 연결이 종료될 때까지 동일한 채널을 사용하여 통신이 수행된다.

  메시지는 양방향으로 교환되며, 데이터를 암호화할 수 있다.

- WebSocket 통신은 실시간 데이터 업데이트와 클라이언트 메시지를 보내는 기능이 필요로 할 때 주로 사용된다.

> WebSocket 통신 사용 사례

  - 교환 플랫폼

  - 게임 애플리케이션

  - 챗봇

  - 푸시 알림

  - 소셜 네트워크

  - 채팅 애플리케이션

  - IoT 애플리케이션

## 참고 자료

- 과제를 진행하기 위해 먼저 WebSocket 통신을 주고받을 서버와 클라이언트가 있어야 한다.

  Node.js와 Express.js 프레임워크를 사용하여 간단하고 빠르게 서버를 구현할 수 있다.

- Node.js는 JavaScript 언어로 Front-end 뿐만 아니라 Back-end 개발 환경을 구성할 수 있기 때문에 생산성이 높고 러닝 커브를 줄일 수 있다.

  빠르게 개발환경을 구성하여 개발을 해야하는 경우 매우 유용하다.

  이러한 이유로 Node.js를 이용하여 쉽게 서버를 구성할 수 있는 Express.js 프레임워크를 이용하여 실습을 할 수 있다.

- 참고자료: [Node.js](https://nodejs.org), [Express.js](https://expressjs.com), [ws(WebSocketLibrary)](https://www.npmjs.com/package/ws), [HTTP에서부터 WebSocket까지](https://url.kr/a3coyv)

## 기능/과제

### 1. Node.js의 Express.js 프레임워크를 이용하여 서버 구축

> ### Node.js의 Express.js 프레임워크 설치

1. Node.js 설치

  [사이트](https://nodejs.org/ko/download)에서 운영체제에 맞는 설치파일을 다운받아 설치(LTS 버전)

  `node -v`를 입력하여 다운받아 설치한 node.js 버전이 정상적으로 설치되었는지 확인

2. Express.js 설치

  npm을 이용해서 설치한다. 
  
  npm은 Node.js 패키지 매니저로 Node.js로 만들어진 모듈을 웹에서 받아서 설치하고 관리해주는 프로그램이다.

  과제를 진행할 폴더로 이동 후 `npm init` 명령을 실행한다.

  해당 명령어를 통해 앞으로 설치될 패키지를 관리할 package.json 파일을 생성한다.

  이후 `npm install express` 명령을 터미널에 입력하면 Express.js가 설치된다.

  정상적으로 설치되었다면, package.json 파일에 설치된 express.js 버전이 기록된다.

> ### Node.js의 Express.js 프레임워크를 이용한 서버 구동

- 간단한 클라이언트와 서버 코드를 작성하여 웹서버 구동 및 WebSocket 통신 구현을 위한 환경 구축

1. 클라이언트 코드 작성

  `front`라는 폴더를 생성 후 해당 폴더 내에 `index.html`파일을 작성

2. Node.js 서버 생성

  루트 디렉토리에 `index.js` 파일 생성 후 앞서 작성한 html 파일을 서빙

3. 서버 구동

  루트 디렉토리 터미널에서 `node index.js`를 실행하여 서버를 구동

  크롬 브라우저에서 `localhost:8000`으로 접속해 화면 확인

### 2. WebSocket을 이용하여 클라이언트에서 서버로 데이터 전송

> ### WebSocket 통신을 위해 ws 웹소켓 라이브러리 설치

- npm을 이용하여 ws 웹소켓 라이브러리 설치

  루트 디렉토리에서 `npm install ws` 명령어를 입력해 ws 라이브러리 설치 후 package.json 파일 확인

> ### ws 라이브러리를 이용하여 클라이언트에서 서버로 메시지 보내기

- index.js 파일에 ws 모듈을 불러온 후 포트 8001번을 통해서 접속할 수 있는 웹소켓 서버를 열어주도록 코드 추가

- 클라이언트에서 버튼을 만들고 버튼을 클릭했을 때 'Hello' 라는 메시지를 WebSocket 통신을 통해 서버로 보내도록 index.html 파일에 코드 추가

- 터미널에서 index.js를 실행하여 서버를 구동한 후 `localhost:8000`로 접속하면 '전송' 버튼을 확인할 수 있음

  해당 버튼을 클릭하면 'Hello' 라는 메시지가 WebSocket 통신을 통해 서버에 전달됨

  터미널에서 서버 로그를 확인하면 클라이언트로부터 'Hello'라는 메시지를 받았다는 로그를 확인할 수 있음

### 3. WebSocket을 이용한 채팅 기능 구현

> ### WebSocket 통신을 이용한 간단한 채팅 기능 구현

- 간단한 채팅 기능 구현을 위해서는 먼저 서버에 접속된 모든 클라이언트들에게 메시지를 전송할 수 있는 기능이 필요함

  일반적으로 이를 브로드캐스트라고 하는데, 이를 이용하여 다음과 같이 서버 접속 및 연결 해제 정보와 접속한 사용자 이름과 메시지를 모든 클라이언트에 전송하는 간단한 채팅 기능을 구현해볼 수 있음

  1. 서버에 새로운 유저가 접속하거나 연결을 해제하면 접속된 모든 클라이언트에 유저의 접속 및 해제 사실과 현재 접속되어 있는 전체 유저 수를 브로드캐스트 한다.

    - 새로운 유저 접속 시: `새로운 유저 접속 [현재: X명]`

    - 기존 유저 연결 해제 시: `유저 연결 해제 [현재: X명]`

  2. 사용자 이름과 메시지를 입력받아 전송 버튼을 클릭하면 접속되어 있는 모든 클라이언트에 사용자 이름과 메시지를 표시한다.

  [참고 블로그](https://hudi.blog/websocket-with-nodejs/)