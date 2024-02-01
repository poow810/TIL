ALGORITHM_3
### 검색

원하는 항목을 찾는 작업

- 순차 검색
- 이진 검색
- 해쉬

> **순차 검색**
> 

일렬로 되어 있는 자료를 순서대로 검색

**최악의 경우**에는 자료를 끝까지 탐색해야 하기 때문에 비효율적

**📋 검색 과정**

- 첫 번째 원소부터 순서대로 대상과 키 값이 맞는지 비교
- 찾으면 인덱스를 반환

```python
lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for i in range(len(lst)):
		if x == lst[i]: # x = 찾고자 하는 값
				return i    # i는 해당 값의 인덱스
```

```python
# 자료가 정렬되어 있지 않을 때
def sequential_search(a, n, key)
		i <- 0
		while i < n and a[i] != key:
					i <- i + 1
		if i < n : 
				return i
		else:
				return -1  

# 자료가 정렬되어 있을 때 -> 해당 값까지만 찾고 key값보다 크다면 break
def sequentialSearch2(a, n, key)
			i <- 0
			while i < n and a[i] < key:
						i <- i + 1
			if i < n and a[i] == key:
						return i

			else:
						return -1
```

> **이진 검색**
> 
- 조건 : 자료가 정렬되어 있어야 함

**📋 검색 과정**

- 중앙 원소 설정
- 중앙 원소 값과 목표 값을 비교
- 목표 값이 중앙 원소 값보다 작으면 왼쪽에 대해서, 크거나 같다면 오른쪽 탐색

> **이진 검색 구현**
> 
- 검색 시작점과 종료점을 이용하여 반복 수행
- 자료의 삽입이나 삭제가 발생했을 때, 배열의 상태를 항상 정렬 상태로 유지

```python
def binarySearch(a, N, key):
		start = 0
		end = N - 1
		while start <= end:
					middle = (start + end)//2
					if a[middle] == key: # 검색 성공
							return True
					elif a[middle] > key:
							end = middle-1
					else:
							start = middle + 1
		return False # 검색 실패		
```

> **선택 정렬 - O(N^2)**
> 
- 주어진 자료들 중 가장 작은 값의 원소부터 차례대로 위치를 교환

**📋 정렬 과정**

- 리스트에서 최솟값을 찾음
- 리스트 맨 앞에 위치한 값과 교환

```python
def selectionSort(a, N):
		for i in range(N-1):
				min_idx = i
				for j in range(i+1, N):
						if a[min_idx] > a[j]:
								min_idx = j
				a[i], a[min_idx] = a[min_idx], a[i]
```

> **셀렉션 알고리즘**
> 
- 최대, 최솟값, 원하는 위치의 있는 원소를 찾기 위한 알고리즘
- 탐색 구간을 원하는 구간으로 조정하여, 전부 탐색하지 않도록 한다