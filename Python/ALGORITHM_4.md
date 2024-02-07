ALGORITHM_4
### 스택

- 스택 자료는 선형 구조

> **스택 구현**
> 

```python
**# 스택에 원소 추가**
def push(x):
		return stack.append(x)

**#** **스택에서 원소 추출**
def pop():
		if stack:
		    return stack.pop()
		else:
		    return -1
		

**# 스택의 길이**
def size():
		return len(stack)

**# 스택이 비어있는가**
def empty():
		if stack:
				return 0
		else:
				return 1

**# 스택의 가장 최근 값**
def top():
		if stack:
				return stack[-1]
		else:
				return -1

##!! 항상 stack이 비어있는지 조건문을 통해 체크하는 것이 중요함
## pop 같은 경우 스택이 비어있다면 에러가 발생함
```

> **스택의 응용 - Function call**
> 
- 함수 호출과 복귀 수행 순서를 관리
- 가장 마지막에 호출된 함수 → 가장 먼저 완료
- 함수 수행에 필요한 변수 등의 정보를 stack frame에 저장 및 system stack에 삽입

<aside>
💡 재귀 함수에서의 스택의 top 개념은 전체 동작 함수의 level 개념.
몇 개의 level을 지나야 모든 함수가 실행 완료되는지 파악할 수 있음

# ex ) 7번의 재귀가 필요함 → level이 7을 종료 조건으로 설정

</aside>

> **Memorization**
> 
- 함수 호출의 깊이가 깊어질수록 중복 호출이 많아짐
    
    → Memorization을 통해 이전에 계산한 값을 메모리에 저장해 다시 계산되지 않도록 함
    
    → Dynamic programming의 핵심 기법
    

```python
# Memorization을 적용한 기법
def fibo(n):
		global memo
		if n >= 2 and memo[n] == 0:
				memo[n] = fibo(n-1) + fibo(n-2)
		return memo[n]

memo = [0] * (n + 1)
memo[0] = 0
memo[1] = 1
```