TREE
### 트리

- 비선형 구조
- 원소들 간 1:n 관계를 가지는 자료 구조
- 노드 중 최상위 노드 - 루트

> **이진 트리** ⚡
> 
- 모든 노드들이 2개의 서브 트리를 가짐
- 각 노드는 자식 노드를 최대 2개 가짐

<aside>
💡 레벨 i에서의 노드 최대 개수 2^i
높이가 h인 이진 트리가 가질 수 있는 노드 최소 개수 → h+1개 최대 개수 → (2^h+1-1)

</aside>

> **포화 이진 트리**
> 
- 모든 레벨에 노드가 포화 상태로 차 있음
- 높이가 h일 때, 최대 노드 개수를 가짐
- 루트가 1번으로 모든 위치가 정해진 노드 번호를 가짐

> **완전 이진 트리**
> 
- 높이가 h이며 노드가 n개일 때, 노드 번호 1번부터 n번까지 빈 자리가 없는 이진 트리

> **순회**
> 
- 3가지의 기본적인 순회 방법
- **전위 순회** : 부모 노드 방문 후, 자식 노드를 좌, 우 순서로 방문
    
    ```python
    # 구현 방법
    1) 현재 노드 n을 방문하여 처리
    2) 현재 노드 n의 왼쪽 서브트리로 이동
    3) 현재 노드 n의 오른쪽 서브트리로 이동
    
    # 전위 순회
    def preorder_traverse(T):
    		if T:
    				visit(T)
    				preorder_traverse(T.left)
    				preorder_traverse(T.right)
    ```
    
- **중위 순회** : 왼쪽 자식, 부모 노드, 오른쪽 자식
    
    ```python
    # 구현 방법
    1) 현재 노드 n의 왼쪽 서브트리로 이동
    2) 현재 노드 n을 방문 처리
    3) 현재 노드 n의 오른쪽 서브리로 이동
    
    # 중위 순회
    def inorder_traverse(T):
    		if T:
    				inorder_traverse(T.left)
    				visit(T)
    				inorder_traverse(T,right)
    ```
    
- **후위 순회** : 자식 노드를 좌우 순서로 방문한 후, 부모 노드 방문
    
    ```python
    # 구현 방법
    1) 현재 노드 n의 왼쪽 서브트리로 이동
    2) 오른쪽 서브 트리로 이동
    3) 부모 노드로 이동
    
    # 후위 순회
    def outorder_traverse(T):
    		if T:
    				outorder_traverse(T,left)
    				outorder_traverse(T,right)
    				visit(T)			
    ```
    

> 이진 트리의 표현
> 
- 배열을 이용한 이진 트리 표현
- 이진 트리의 각 노드 번호를 부여

<aside>
💡 노드 번호의 성질
- 노드 번호가 i인 노드의 부모 번호 → i / 2
- 왼쪽 자식 노드 번호 → 2*i
- 오른쪽 자식 노드 번호 → 2*(i+1)

</aside>