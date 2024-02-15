ALGO_QUEUE
### 큐의 특성

- 선입선출 구조 → 가장 먼저 들어온 데이터가 가장 먼저 삭제

```python
# queue 생성
queue = [0] * N
front, rear = -1, -1

# 삽입 로직 - enQueue
# 마지막 원소 뒤에 새로운 원소 삽입
1) rear 값을 하나 증가
2) rear 위치에 값 저장
def enQueue(item):
		global rear
		rear += 1
		Queue[rear] = item

# 삭제 로직 - deQueue
# front를 증가 시키고, 그 위치를 반환
def deQueue():
		front += 1
		return queue[front]

# empty, full 확인
def isEmpty():
		return front == rear

def isFull():
		return rear == len(queue)-1

```

> 원형 큐
> 
- 선형 큐는 삽입 삭제가 여러 번 이루어지면, 앞 부분 공간을 포화상태로 인식하여 더 이상 수행하지 않음

→ 1차원 배열이지만, 처음과 끝이 연결되어 있어 원형으로 이룬다 가정

```python
# 초기 공백 상태
front = rear = 0

# 인덱스 순환
front와 rear가 n-1을 가르킨 후, 배열의 처음 인덱스로 이동해야함
-> 연산자 mod
-> rear = (rear + 1) % n / front = (front + 1) % n

# front 변수 
항상 front가 있는 자리는 사용하지 않고 빈자리로 둔다

# empty, full 검사
def isEmpty():
		return front == rear

def isFull():
		return (rear+1) % len(Q) == front

# 삽입
def enQueue(item):
		global rear
		rear = (rear + 1) % len(Q)
		Q[rear] = item

# 삭제
def deQueue():
		global front
		front = (front+1) % len(Q)
		return Q[front]
```

### 📝 Linked List에서 가르키는 주소 값이 바뀌면?

- 해당 주소의 값이 동적할당영역(heap)에 저장되어 있다가 주소 값을 더이상 참조하지 않으면 garbage 컬렉터에 의해서 사용하지 않는 메모리는 자동 삭제

### 우선순위 큐

- 우선순위를 가진 항목들을 저장하는 큐
- 우선순위가 높은 순서대로 추출