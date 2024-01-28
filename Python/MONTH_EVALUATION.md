MONTH_EVALUATION
## 월말 평가
> style guide
> 
- 한 줄의 길이는 79자 제한

> Numeric Types
> 
- 유한 정밀도 : 컴퓨터 메모리 용량은 한정. 한 숫자를 표현할 때 무한대로 표현되기 때문에, 가장 실수와 가까운 값으로 표현
- 실수 연산 시 이렇게 무한대 수의 근삿값 표기로 인한 Floating point rounding error가 발생
    
    → 해결 방안 : math 모듈 사용
    

> Sequence Types
> 
- 특징 - 순서, 인덱싱, 슬라이싱, 길이, 반복

### Data Structure

> Sequence data structure  - 문자열
> 
- 문자열 조회

```python
string = "string"
print(string.find("i")) # 3 해당 인자의 위치 반환, 없다면 -1 반환
print(string.index("i")) # 3 해당 인자의 위치 반환, 없다면 오류 발생
print(string.isalpha()) # True 알파벳인지 아닌지 -> 유니코드 상
print(string.isupper()) # False 모두 대문자인지 아닌지
print(string.islower()) # True 모두 소문자인지 아닌지
```

- 문자열 조작

```python
print(string.replace("s", "a")) # astring old를 new로 바꿔서 반환
print(string.strip("s")) # 특정 문자열 제거
print(string.split("t")) # 특정 문자 기준으로 나눠서 리스트에 담음
print("join".join(string)) # 구분자로 iterable한 데이터를 합침 s~t~r~i~n~g
print(string.capitalize()) # 가장 첫 번째 글자 대문자로 변경
print(string.title()) # 문자열 띄어쓰기 기준. 각 단어의 첫 글자는 대문자, 나머지는 소문자
print(string.upper()) # 문자열 모두 대문자
print(string.lower()) # 문자열 모두 소문자
print(string.swapcase()) # 대<->소문자 변경
```

> Sequence data structure - list
> 
- 값 추가 및 삭제

```python
lst = [1, 2, 3, 4, 5]
lst2 = [7,8,9]
lst.append(6)   # 마지막에 항목 x 추가 
lst.extend(lst2) # iterable data의 모든 항목들을 리스트 마지막에 추가
lst.insert(3, 10) # (index, x) index자리에 x 삽입
lst.remove(3) # 리스트에서 가장 첫 번째 x 제거, 없을 시 ValueError
lst.pop() # 리스트 가장 오른쪽 항목 반환 및 제거
lst.pop(4) # 해당 인덱스 항목 반환 및 제거
lst.clear() # 리스트 모든 항목 삭제
```

- 탐색 및 정렬

```python

```

> Nonsequence data structure - set
> 
- set 메서드

```python
lst = [1, 2, 3, 4, 5, 6]
lst_set = set(lst)
print(lst_set)
lst_set.add(7)
lst_set.remove(3) # 해당 항목이 없다면 Key error
print(lst_set.pop()) # set = [1, 2, 4, 5, 6, 7] 이었는데,
print(lst_set.pop()) # 1, 2, 4, 5, 6, 7 순으로 pop
print(lst_set.pop()) # random하지 않음
print(lst_set.pop()) # 임의의 순서가 있음
print(lst_set.pop())
print(lst_set.pop())
print(lst_set)
lst_set.add(3)
print(lst_set.remove(3)) # 얘도 Key error 나긴 하는데?

lst2 = [1, 3, 5]
lst_set.update(lst2)
print(lst_set)
```

- 집합 메서드

```python
set1.difference(set2) -> set1에는 있지만, set2에는 없는 것을 새로운 set 생성 후 반환
set1.intersection(set2) -> set1, set2에 모두 들어 있는 항목 새로운 set 생성 후 반환
set1.issubset(set2) -> set1 항목이 모두 set2에 들어있다면, True 반환
set1.issuperset(set2) -> set1이 set2를 모두 포함한다면, True 반환
set1.union(set2) -> set or set2 둘 다의 원소를 합하여 새로운 set 생성 후 반환

---> subset은 앞이 부분 집합, superset은 뒤가 부분 집합 
```

> Nonsequence data structure - dictionary
> 
- 딕셔너리 메서드

```python
dic = {
    "key1" : 1,
    "key2" : 2,
    "key3" : 3,
    "key4" : 4,
    "key5" : 5
}
# dic.clear() # dictionary 모두 제거

print(dic.get("key1")) # key1에 해당하는 value 반환
print(dic.get("key2", 5)) # key2에 해당하는 value 반환, 없으면 기본값 5 반환
print(dic.keys()) # 딕셔너리의 모든 key 반환
print(dic.values()) # 딕셔너리의 모든 value 반환
print(dic.items()) # 모든 key, value의 튜플 형태 반환
print(dic.pop("key1")) # key를 제거하고 해당하는 value 반환
print(dic.pop("key2", 5)) # key를 제거하고, value 반환, 없다면 5(defalut) 반환  
dic.setdefault("key1") # key1 값 반환, 없다면 value와 함께 딕셔너리에 추가
dic.setdefault("key2", 5) # key2 값 반환, 없다면 defalut value와 함께 딕셔너리에 추가
dic.update("other") # other의 각 키에 대해 d에 있다면 key의 value를 other의 값으로 대체, 없다면 key / value 추가
```

> **Hash Table**
> 
- 해시 함수를 사용하여 변환한 값을 index로 key와 value를 저장하는 구조
- key ——>(해시함수)—→ 해시 값

> **해시(Hash)란?**
> 
- 임의의 데이터를 고정된 크기의 값으로 변환하는 것
- 데이터를 고유한 값으로 식별하기 때문에, 데이터의 ‘지문’ 이라고 불림
- 해시 값은 정수로 표현됨

> **set의 요소 & 딕셔너리 키 —> 해시 테이블과의 관계?**
> 
- set의 요소는 해시 값으로 변환되어 저장, 딕셔너리의 키 또한 변환되어 해시 테이블에 저장
    
    → 중복 값을 허용하지 않으면서, 매우 빠른 탐색 속도를 제공
    

**🔍 알아두어야 할 해시 함수**

```python
print(hash(1)) # 정수는 실행 시마다 똑같음
print(hash(1)) # 똑같이 1 출력
print(hash('1')) # 문자열은 실행 시마다
print(hash('1')) # 다르게 출력됨
```

왜 그럴까❓

- 파이썬에서의 정수는 그 값 자체로 해시 값임
- 문자열은 해시 함수를 통해 해시 값으로 변경되며, 가변적인 길이를 가지며 문자열에 포함된 각 문자들의 유니코드 등 여러 가지 요소를 기반으로 해시 값을 계산함
    
    → 매 번 다르다
    
    → 이 다르다는 뜻이 ‘1’과 ‘1’이 다르다는 것이 아니라, 같은 문자열을 해시 값으로 만들 때마다의 해당 해시 값이 서로 다르다는 뜻
    

> **hashable과 immutable의 관계**
> 
- 해시 테이블 키 → immutable
- immutable 객체는 변하지 않으므로, 동일한 값에 대해 같은 해시 값을 가짐

❗hashable과 immutable 하다는 같지 않다

> **hashable 객체가 필요한 이유?**
> 
- 해시 테이블 기반 자료 구조 사용 (set, dictionary)
- 중복 값 방지 및 빠른 검색
- 불변성을 통한 동일한 해시 값
- 안정성과 예측 가능성 유지