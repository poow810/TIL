TREE2
### 이진 탐색 트리

> **오름차순 정렬 - 중위 순회**
> 
- 트리를 중위 순회하면 오름차순으로 정렬할 수 있음
- 탐색 키 값이 루트 노드의 키 값보다 작다면 left, 크다면 right, 같다면 root

> 힙(heap)
> 
- 완전 이진 트리에서 키 값이 가장 큰 노드나 가장 작은 노드를 찾기 위함

```python
# 최대 힙
def enq(n):
		global last
		# 마지막 노드 추가(완전 이진 트리 유지)
		last += 1
		h[last] = n
		# 부모 > 자식
		c = last
		p = c//2
		
		while p >= 1 and h[p] < h[c]: # 부모가 자식보다 작으면 교환
				h[p], h[c] = h[c], h[p]
				c = p
				p =c // 2

N = 10          # 필요한 노드 수
h = [0]*(N+1)   # 최대 힙
last = 0        # 힙의 마지막 노드 번호

# 삭제
def deq():
		global last
		temp = h[1] # 최대 heap 임시 보관
		h[1] = h[last]
		last- -= 1
		p = 1
		c = p * 2
		
		while c <= last:
				if c + 1 <= last and h[c] < h[c+1]:
						c += 1
				if h[p] < h[c]:
						h[p], h[c] = h[c], h[p]
						p = c
						c = p * 2
				else:
						break
		return temp
		
```