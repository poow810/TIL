PYTHON_DATA2
### 비시퀀스 데이터 구조

> **set**
> 
- 원소가 중복되지 않음
- 순서가 존재하지 않음

| s.add(x) | 항목 x 추가 |
| --- | --- |
| s.clear() | 모든 항목 제거 |
| s.remove() | x제거. 없을 경우 Key error |
| s.pop() | 랜덤한 항목을 반환 및 제거 |
| s.discard(x) | 항목 x 제거 - 에러 발생 안함 |
| s.update(iterable) | 다른 iterable 요소 추가 = extend() |

- set의 집합 메서드

| set1.difference(set2) | set1에는 있지만 set2에는 없는 항목으로 set 생성 및 반환 | set1 - set2 |
| --- | --- | --- |
| set1.intersection(set2) | set1과 set2 모두 들어있는 set 생성 및 반환 | set1 + set2 |
| set1.issubset(set2) | set1의 항목이 모두 set2에 들어있으면 True 반환 | set1 <= set2 |
| set1.issuperset(set2) | set1이 set2의 항목을 모두 포함하면 True 반환 | set1 >= set2 |
| set1.union(set2) | set1 or set2에 들어있는 set 생성 및 반환 | set | set2 |

> **dictionary**
> 

| D.clear() | 모든 Key / Value 쌍 제거 |
| --- | --- |
| D.get(k) | Key의 value 반환(없다면 None) |
| D.get(k, v) | Key에 연결된 값을 반환, 없다면 기본 값으로 v 반환 |
| D.keys() | Key를 모은 객체 반환 |
| D.values() | value를 모은 객체 반환 |
| D.items() | Key / Value를 모은 객체 반환 |
| D.pop(k) | Key를 제거하고 연결된 value 반환 (없다면 오류) |
| D.pop(k, v) | Key를 제거하고 연결된 value 반환 (없다면 v 반환) |
| D.setdefault(k) | Key와 연결된 value 반환 |
| D.setdefault(k, v) | Key와 연결된 value 반환, k가 D의 key가 아니라면, key로 추가하고 연결된 v 반환 |
| D.update(other) | D와 other의 key가 동일한 것이 있다면, D의 value를 other의 value로 변경
other에 있는 key / value가 D에 없다면 추가 |

> **해시 테이블**
> 
- 해시 함수를 이용하여 변환
    
    → index로 하여금 key와 value를 저장
    

- 원리
    - 키를 해시 함수를 통해 해시 값으로 변환 → 해시 값을 인덱스로 활용

> **해시(Hash)**
> 
- 임의의 크기의 데이터를 고정된 크기의 값으로 변환하는 것
- 데이터 → 해시 값으로 변환하며, 해시 값은 정수

> s**et 요소 & dictionary의 키와 해시테이블 관계**
> 
- set 요소나 dictionary의 키는 해시 테이블을 이용하여 중복되지 않도록 저장
- 해시 값을 통해 해시 테이블에 저장 및 인덱싱
- 매우 빠른 탐색 속도
- Key값이 정수라면 해시 값은 정수 값
- 정수를 출력했을 때 나오는 순서는, 해시 테이블에 나열된 순서 → 정수는 고정 값이기 때문에

> **hashable**
> 
- hash() 함수의 인자로 전달해서 결과를 반환 받을 수 있는 객체
- 대부분 immutable한 data type은 hashable
- 튜플의 경우에선 내부의 리스트를 가지고 있는 tuple은 해시 불가능한 경우도 있음

> **hashable과 불변성 간의 관계**
> 
- 해시 테이블 키는 불변
