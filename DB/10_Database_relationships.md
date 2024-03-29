# 데이터베이스 관계

관계형 데이터베이스에서 외래키 속성을 사용해 모델 간 N:1 관계 설정하기

> ### RDB(관계형 데이터베이스)

데이터를 테이블, 행, 열 등으로 나누어 구조화하는 방식

RDB의 모든 테이블에는 행에서 고유하게 식별 가능한 기본 키라는 속성이 있으며, 외래 키를 사용하여 각 행에서 서로 다른 테이블 간의 관계를 만드는 데 사용할 수 있음

즉, 관계형 데이터베이스에서 한 테이블의 필드 중 다른 테이블의 행을 식별할 수 있는 키를 외래 키(foreign key, FK)라고 함

## RDB에서의 관계

### 1:1

  One-to-One relationships

  한 테이블의 레코드 하나가 다른 테이블의 레코드 단 한 개와 관련된 경우

### N:1

  Many-to-One relationships

  한 테이블의 0개 이상의 레코드가 다른 테이블의 레코드 한 개와 관련된 경우

  기준 테이블에 따라 1:N(One-to-Many relationships)라고도 함

### M:N

  Many-to-Many relationships

  한 테이블의 0개 이상의 레코드가 다른 테이블의 0개 이상의 레코드와 관련된 경우

  양쪽 모두에서 N:1 관계를 가짐

## Foreign Key

외래 키(외부 키)

관계형 데이터베이스에서 다른 테이블의 행을 식별할 수 있는 키

참조되는 테이블의 기본키(Primary Key)를 가리킴

참조하는 테이블의 행 1개의 값은 참조되는 측 테이블의 행 값에 대응됨

  때문에 참조하는 테이블의 행에는, 참조되는 테이블에 나타나지 않는 값을 포함할 수 없음

참조하는 테이블 행 여러개가, 참조되는 테이블의 동일한 행을 참조할 수 있음

### 특징

  키를 사용하여 부모 테이블의 유일한 값을 참조 (by 참조 무결성)

  외래 키의 값이 반드시 부모 테이블의 기본 키일 필요는 없지만, 유일한 값이어야 함

> ### [참고] 참조 무결성

  데이터베이스 관계 모델에서 관련된 2개의 테이블 간의 일관성을 말함

  외래 키가 선언된 테이블의 외래 키 속성(열)의 값은 그 테이블의 부모가 되는 테이블의 기본 키 값으로 존재해야 함