# 04_advanced_function_and_env



# Python 04

## 내장함수(Built-in Functions)

### map

`map(function, iterable)`

- 순회 가능한 데이터구조(iterable)의 모든 요소에 함수(function)적용하고, 그 결과를 map object로 반환
- 알고리즘 문제 풀이 시 input 값들을 숫자로 바로 활용하고 싶을 때 활용

### filter

`filter(function, iterable)`

- 순회 가능한 데이터구조(iterable)의 모든 요소에 함수(function)적용하고, 그 결과가 True인 것들을 filter object로 반환

### zip

`zip(*iteables)`

- 복수의 iterable을 모아 튜플을 원소로 하는 zip object를 반환

## lambda 함수

`lambda [parameter] : 표현식`

- 람다함수
  - 표현식을 계산한 결과값을 반환하는 함수로, 이름이 없는 함수여서 익명 함수라고도 불림
- 특징
  - return문을 가질 수 없음
  - 간편 조건문 외 조건문이나 반복문을 가질 수 없음
- 장점
  - 함수를 정의해서 사용하는 것보다 간결하게 사용 가능
  - def를 사용할 수 없는 곳에서도 사용가능

## 재귀함수(recursive function)

- 자기 자신을 호출하는 함수
- 무한한 호출을 목표로 하는 것이 아니며, 알고리즘 설계 및 구현에서 유용하게 활용
  - 알고리즘 중 재귀 함수로 로직을 표현하기 쉬운 경우가 있음(점화식)
  - 변수의 사용이 줄어들며, 코드의 가독성이 높아짐
- 1개 이상의 base case(종료되는 상황)가 존재하고, 수렴하도록 작성

> 재귀함수 주의사항

- 재귀 함수는 base case에 도달할 때까지 함수를 호출함
- 메모리 스택이 넘치게 되면(stack overflow) 프로그램이 동작하지 않게 됨
- 파이썬에는 최대 재귀 깊이(maximum recursion depth)가 1000번으로, 호출 횟수가 이를 넘어가게 되면 `Recursion Error` 발생

> 반복문과 재귀함수

- 알고리즘 자체가 재귀적인 표현이 자연스러운 경우 재귀함수를 사용
- 재귀 호출은 변수 사용을 줄여줄 수 있음
- 재귀 호출은 입력값이 커질수록 연산 속도가 오래 걸림

## 패킹/언패킹(Packing/Unpacking)

- 패킹/언패킹 연산자(Packing/Unpacking Operator) `*`
  - 모든 시퀀스형(리스트, 튜플 등)은 패킹/언패킹 연산자 `*`를 사용하여 객체의 패킹 또는 언패킹이 가능
- 패킹
  - 대입문의 좌변 변수에 위치
  - 우변의 객체 수가 좌변의 변수 수보다 많을 경우 객체를 순서대로 대입
  - 나머지 항목들은 모두 별 기호로 표시된 변수에 리스트로 대입
- 언패킹
  - argument 이름이 `*`로 시작하는 경우, argument unpacking이라 함
    - `*`패킹의 경우,리스트로 대입
    - `*`언패킹의 경우 튜플 형태로 대입

> 별표`*` 연산자가 곱셈을 의미하는지 Packing/Unpacking 연산자인지 구분

- Packing/Unpacking 연산자 `*`
  - `*`가 대입식의 좌측에 위치하는 경우
  - `*`가 단항 연산자로 사용되는 경우
    - 단항 연산자: 하나의 항을 대상으로 연산이 이루어지는 연산자
- 산술 연산자 `*`
  - `*`가 이항 연산자로 사용되는 경우
    - 이항 연산자: 두 개의 항을 대상으로 연산이 이루어지는 연산자

### 함수 가변 입력

- 정해지지 않은 여러 개의 Arguments 처리

### 가변 인자(`*args`)

- 여러 개의 Positional Argument를 하나의 필수 parameter로 받아서 사용
- 가변인자의 사용
  - 몇 개의 Positional Argument를 받을 지 모르는 함수를 정의할 때 유용
  - 가변 인자가 가져갈 개수는 특정할 수 없음
- Asterisk(`*`)와 가변 인자
  - `*`는 시퀀스 언패킹 연산자라고도 불리며, 말 그대로 시퀀스를 풀어헤치는 연산자
  - 주로 튜플이나 리스크를 언패킹하는 데 사용
  - `*`를 활용하여 가변 인자를 만들 수 있음

> 가변 인자를 이해하기 위해서 패킹, 언패킹 이해
> 
> - 패킹: 여러 개의 데이터를 묶어서 변수에 할당하는 것
> - 언패킹: 시퀀스 속의 요소들을 여러 개의 변수에 나누어 할당하는 것
> - 언패킹 시 변수의 개수와 할당하고자 하는 요소의 개수가 동일해야 함
> - 언패킹 시 왼쪽의 변수에 asterisk(`*`)를 붙이면, 할당하고 남은 요소를 리스크에 담을 수 있음

### 가변 키워드 인자(`**kwargs`)

- 몇 개의 키워드 인자를 받을 지 모르는 함수를 정의할 때 유용
- `**kwargs`는 **딕셔너리로 묶여 처리**되며, parameter에 `**`를 붙여 표현
- 가변 키워드 인자는 가변 인자보다 뒤에 적음

## 모듈(module)과 패키지

- 모듈(module):
  - 특정 기능을 하는 코드를 파이썬 파일(.py) 단위로 작성한 것
- 패키지(package):
  - 특정 기능과 관련된 여러 모듈의 집합
  - 패키지 안에는 또 다른 서브 패키지를 포함

### 라이브러리

- 파이썬에 기본적으로 설치 된 모듈과 내장 함수
  
  - [http://docs.python/org/ko/3/library/index.html](http://docs.python/org/ko/3/library/index.html)

- 라이브러리(library):
  
  - 다양한 패키지를 하나의 묶음으로

- 파이썬 패키지 관리자 `pip`:
  
  - PyPI(Python Package Index)에 저장된 외부 패키지들을 설치하도록 도와주는 패키지 관리 시스템
  
  - 패키지 설치:
    
    - 최신 버전/ 특정 버전/ 최소 버전을 명시하여 설치할 수 있음
    - 이미 설치되어 있는 경우 이미 설치되어 있음을 알리고 아무것도 하지 않음
  
  - 파이썬 패키지 관리자(pip) 명령어
    
    - 패키지 삭제: `$ pip uninstall SomePackage`
    
    - 패키지 목록 및 특정 패키지 정보:
      
        `$ pip list`
      
        `$ pip show SomePackage`
    
    - 패키지 관리하기
      
      - 아래 명령어들을 통해 패키지 목록을 관리하고 설치할 수 있음
      
      - 일반적으로 패키지를 기록하는 파일의 이름은 requirments.txt로 정의함
        
          `$ pip freeze > requirements.txt`
        
          `$ pip install -r requirements.txt`
    
    - PyTorch 깃헙 참조

## 모듈과 패키지 활용하기

### 패키지

- 패키지는 여러 모듈/ 하위 패키지로 구조화
  - 활용 예시: package.module
- 모든 폴더에는 `__init__.py`를 만들어 패키지로 인식
  - python 3.3부터는 파일이 없어도 되지만, 하위버전 호환 및 프레임워크 등에서의 동작을 위해 파일을 생성하는 것을 권장

### 가상환경

- 파이썬 표준 라이브러리가 아닌 외부 패키지와 모듈을 사용하는 경우 모두 pip를 통해 설치해야 함

- 복수의 프로젝트를 하는 경우 버전이 상이할 수 있음

- 이러한 경우 가상환경을 만들어 프로젝트 별로 독립적인 패키지를 관리할 수 있음

- 가상환경을 만들고 관리하는데 사용하는 모듈(Python 3.5부터)

- 특정 디렉토리에 가상환경을 만들고, 고유한 파이썬 패키지 집합을 가질 수 있음
  
  - 특정 폴더에 가상환경(패키지 집합 폴더 등)이 있고
  - 실행환경(bash 등)에서 가상환경을 활성화시켜
  - 해당 폴더에 있는 패키지를 관리/사용함

- 가상환경 명령어
  
  - 가상환경 생성
    
    - 가상환경을 생성하면, 해당 디렉토리에 별도의 파이썬 패키지가 설치됨
      
        `$ python -m venv <폴더명>`
      
        `$ python -m venv venv`
  
  - 가상환경 활성화/비활성화
    
    - 윈도우 bash: `$ source venv/Scripts/activate`
    
    - `<venv>` 는 가상환경을 포함하는 디렉토리의 경로
    
    - 가상환경 비활성화는 `$ deactivate`명령어를 사용
    
    - pip list 파일로 빼내기, 목록들을 저장
      
        `$ pip freeze > requirements.txt`
    
    - txt 목록 읽고 모두 설치
      
        `$ pip install -r requirements`