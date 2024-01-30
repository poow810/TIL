ALGORITHM_1
### 정렬

> 카운팅 정렬
> 
- 항목들의 순서를 결정, 각 항목이 몇 개씩 있는지 작업
- 정수나 정수로 표현 가능한 자료형에서 사용
- 시간복잡도 → O(n+k)

```python
lst = [4, 1, 1, 2, 3, 5, 4, 5, 2]
count = [0]*(max(lst)+1)

for i in range(len(lst)):
    count[lst[i]] += 1

--> [0, 2, 2, 1, 2, 2]
```

**🌟 누적합**

```python
# 정렬된 집합에서 각 항목의 앞의 위치한 항목의 개수를 반영
# 해당 인덱스까지의 누적합을 구한다.
```

> 실습
> 

```python
N = 6
K = 9
data = [7, 2, 4, 5, 1, 3]
counts = [0] *(k+1)

for x in data: # 배열에 기록
		counts[x] += 1

for i in range(1, K+1):
		counts[i] = counts[i+1] + counts[i]

for J in range(N-1, -1, -1): # 
		count[[data[j]] -= 1
		temp[counts[data[i]]] = data[j]

```

> **브루트 포스**
> 
- 모든 경우의 수를 나열
- 경우의 수가 적을 때 사용