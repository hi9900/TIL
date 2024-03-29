# Vue State Management

## State Management(상태 관리)

- 상태(State): 현재에 대한 정보(data)

- Web Application에서의 상태: 현재 App이 가지고 있는 Data로 표현

  - 여러개의 component를 조합해서 하나의 App을 만들고 있음

  - 각 component는 독립적이기 때문에 각각의 상태(state)를 가짐

- 여러 개의 component가 같은 상태(data)를 유지할 필요가 있음

- 상태 관리(State Management) 필요

## Pass Props & Emit Event

- 각 컴포넌트는 독립적으로 데이터를 관리

- 같은 데이터를 공유하고 있으므로, 각 컴포넌트가 동일한 상태를 유지하고 있음

- 데이터의 흐름을 직관적으로 파악 가능

- 그러나, component의 중첩이 깊어지면 데이터 전달이 쉽지 않음

- 공통의 상태를 유지해야 하는 component가 많아지면 데이터 전달 구조가 복잡해짐

## Centralized Store

- 중앙 저장소(store)에 데이터를 모아서 상태 관리

- 각 component는 중앙 저장소의 데이터를 사용

- component의 계층에 상관없이 중앙 저장소에 접근해서 데이터를 얻거나 변경할 수 있음

- 중앙 저장소의 데이터가 변경되면 각각의 component는 해당 데이터의 변화에 반응하여 새로 변경된 데이터를 반영함

- 규모가 크거나 컴포넌트 중첩이 깊은 프로젝트의 관리가 매우 편리

## Vuex

- "state management pattern + Library" for vue.js

  (상태 관리 패턴 + 라이브러리)

- 중앙 저장소를 통해 상태 관리를 할 수 있도록하는 라이브러리

- 데이터가 예측 가능한 방식으로만 변경될 수 있도록 하는 규칙을 설정하며, Vue의 반응성을 효율적으로 사용하는 상태 관리 기능을 제공

- Vue의 공식 도구로써 다양한 기능을 제공
