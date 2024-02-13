ALGORITHM_5
# 7일차 스택
### 계산기

> 중위표기식 → 후위표기식 변환 방법
> 
- 수식을 우선순위에 따라 다시 표기
- 연산자를 괄호 바깥쪽으로 뺌
- 괄호를 없앰

<aside>
💡 (6+5*(2-8)/2)
2-8, 5*~, ~/2, 6+~순

후위표기식으로 변환
1. 토큰 가져오기
2. 스택 연산 push() → 토큰이 연산자면 스택 top과 비교해 높으면 push, 여는 괄호 push
3. top 변경 → 스택에 쌓여 있는 마지막 값

</aside>

> **과정**
> 

스택 = [6, 5, 2, 8, 2]

연산자 스택 = [(, +, *, (, -]

📌 **특정 조건**

- 닫는 괄호는 여는 괄호가 나올 때까지 모두 연산자 스택에서 pop
- 연산자는 자신보다 낮은 연산자를 만날 때까지 pop
- 자신보다 낮은 연산자를 만나면 push

📌 **계산**

- 모든 연산자들을 꺼내면 피연산자에서 두 번 pop하여 계산

### 백트래킹

- 해를 찾는 도중, 막히면 되돌아가서 다시 해를 찾는 기법
- 최적화 문제에서 자주 사용함
- 깊이 우선 탐색으로 진행하지만, 각 노드가 유망한지 점검

> **부분 집합**
> 
- 공집합과 자기 자신을 포함한 모든 부분 집합 → powerset

```python
# 부분 집합
# powerset
def backtrack(a, k, input():
		global MAXCANDIDATES
		c = [0] * MAXCANDIDATES

		if k == input :
				process_solution(a, k)
		else:
				k += 1
				ncandidates = construct_candidates(a, k, input, c)
				for i in range(ncanidates):
						a[k] = c[i]
						backtrack(a, k, input)

# 순열
def backtrack(a, k, input():
		global MAXCANDIDATES
		c = [0] * MAXCANDIDATES

		if k == input :
				for i in range(1, k+1):
						print(a[i], end=" ")
				print()
		else:
				k += 1
				ncandidates = construct_candidates(a, k, input, c)
				for i in range(ncanidates):
						a[k] = c[i]
						backtrack(a, k, input)
```