# 추상 데이터 타입(abstract data type)

## 1. 스택(stack)

- 배열의 끝에서만 데이터를 접근할 수 있는 선형 자료구조

- 배열 인덱스 접근이 제한되며, 후입선출(LIFO; Last in, First out)구조이다.

- 시간복잡도는 모두 O(1)

```markdown
- push: 스택의 맨 끝(맨 위)에 항목을 삽입한다.
- pop: 스택 맨 끝 항목을 반환하는 동시에 제거한다.
- top/peek: 스택 맨 끝 항목을 조회한다.
- empty: 스택이 비어있는 지 확인한다.
- size: 스택 크기를 확인한다.
```

- python에서는 리스트의 `append()`와 `pop()` aptjemfh 스택을 구현할 수 있다.

  파이썬으로 스택 구현: `stack.py`

  노드(객체)의 컨테이너로 스택 구현: `stack_with_node.py`

## 2. 큐(queue)

- 먼저 들어온 데이터가 먼저 나가는 선입선출(FIFO; First in, First out)구조

- 배열의 인덱스 접근이 제한됨

- 시간복잡도는 모두 O(1)

```markdown
- enqueue: 큐 뒤쪽에 항목을 삽입한다.
- dequeue: 큐 앞쪽의 항목을 반환하고, 제거한다.
- peek/front: 큐 앞쪽의 항목을 조회한다.
- empty: 큐가 비어있는 지 확인한다.
- size: 큐의 크기를 확인한다.
```

파이썬으로 큐 구현: `queue.py`<br>
리스트의 `insert()`메서드를 사용했다. 이는 모든 요소가 메모리에서 이동될 수 있으므로 비효율적(O(n))

두 개의 스택(두 개의 리스트)을 사용한 효율적인 큐 구현: `queue_from_two_stacks.py`

노드(객체)의 컨테이너로 큐 구현: `linked_queue.py`

## 3. 데크(deque)

- 스택과 큐의 결합체: 양쪽 끝에서 항목의 조회, 삽입, 삭제가 가능하다.

앞에서 구현한 큐(`queue.py`)를 바탕으로 데크 구현: `deque.py`

 파이썬의 `collections` 패키지의 `deque` 모듈을 사용하면 `insert()` 메서드를 사용하지 않아도 된다.

 `from collections import deque`s

  deque 모듈을 사용하면 `q = deque(maxlen=4)` 와 같이 데크의 크기를 지정할 수 있음

  `rotate(n)` 메서드는 n이 양수이면 오른쪽으로, 음수이면 왼쪽으로 n만큼 시프트

deque 모듈은 동적 배열이 아닌 이중 연결 리스트를 기반으로 한다.

## 4. 힙

- 각 노드가 하위 노드보다 작은(또는 큰) 이진트리

- 균형 트리의 모양이 수정될 때, 다시 이를 균형 트리로 만드는 시간복잡도는 O(log n)

- 힙은 일반적으로 리스트에서 가장 작은(또는 가장 큰) 요소에 반복적으로 접근하는 프로그램에 유용하다

- 최소(또는 최대) 힙을 사용하면 가장 작은(또는 가장 큰) 요소를 처리하는 시간 복잡도는 O(1)이고, 그 외의 조회, 추가, 수정을 처리하는 시간 복잡도는 O(log n)이다.

### heapq 모듈

- heapq 모듈은 효율적으로 시퀀스를 힙으로 유지하면서 항목을 삽입하고 제거하는 함수를 제공한다.
