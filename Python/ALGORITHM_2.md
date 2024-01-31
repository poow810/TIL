ALGORITHM_2
### 2차원 배열

```python
# 2차원 배열 선언
N = int(input())
arr = [list(map(int, input().split())) for _ in range(N)] # ? col, 3 row
```

> **행 우선순회**
> 

```python
for i in range(n):    # row를 우선으로 순회함
 		for j in range(m):
				arr[i][j]
```

> **열 우선순회**
> 

```python
for i in range(n):    # col을 우선으로 순회함
		for j in range(m):
				arr[j][j]
```

> **지그재그 순회**
> 

```python
for i in range(n):
		for j in range(m):
				arr[i][j + (m-1-2*j) * (i%2)]
# 행이 짝수인 애들은 오른쪽 방향
# 행이 홀수인 애들은 왼쪽 방향으로 진행함 i를 짝수 홀수로 구분
```

> **전치 행렬**
> 

```python
for i in range(3):
		for j in range(3):
				if i < j:
						arr[i][j], arr[j][i] = arr[j][i], arr[i][j]
# 대각선을 기준으로 위치를 바꿈

for i in range(3):
		for j in range(3):
				if i == j:
						arr[i][j] -> # 대각선 상에 위치한 좌표
```

### 부분집합

- 집합의 원소가 n개일 때, 공집합을 포함한 부분집합의 개수 → **2^n개**

원소 4개❓ → 2^4 = 16 가지 **# *원소 개수마다 for문 (4중 for문)***

> **비트 연산자**
> 
- & - 비트 단위로 AND 연산 ***# i &(1<<j) : i의 j번째 비트가 1인지 아닌지 검사***
- | - 비트 단위로 OR 연산
- << - 피연산자의 비트 열을 왼쪽으로 이동 ***# 원소가 n개일 경우 모든 부분집합의 개수***
- >> - 피연산자의 비트 열을 오른쪽으로 이동

```python
# 부분집합 생성
N = 5
arr = [1, 2, 3, 4, 5]
add = 0

# bit -> i = [b4, b3, b2, b1, b0]
for i in range(1<<N):  # 2^n - 1
		for j in range(N): # 비트의 개수만큼
			 if i&(1<<j):    # i의 j번 비트가 1인 경우
					add += arr[j]  # 부분집합의 합
					print(arr[j], end=" ")
		print()
```