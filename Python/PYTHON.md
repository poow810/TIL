PYTHON
### Sequence Types

- 여러 개의 값들을 **순서대로 나열**하여 **저장하는 자료형**(str, list, tuple, range)
- **특징**
    - **순서** → 크기 순이 아닌 **시간의 순서**로 저장 ****(정렬 x)
    - **인덱싱** → 각 값들이 고유한 index 번호를 가지고 있음. index를 통해 **특정 위치의 값을 선택** 가능
    - **슬라이싱** → 인덱스 범위를 조절해 **부분적인 값 추출** 가능
    - **길이** → len() 함수를 사용하여 **저장된 값의 개수**를 구할 수 있음
    - **반복** → 반복문을 사용하여 **저장된 값들을 반복적으로 처리 가능**

> **str - 문자열**
> 
- 문자들의 순서가 있는 **immutable**한 sequence type
- 문자열은 단일 문자나 여러 문자의 조합으로 구성

**⭐ Escape sequence**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/abf254f6-50fe-4a95-aaab-bf44470fc177/4d69d19b-e30e-41dc-9506-d42c43263eff/Untitled.png)

- f-string
    
    ```python
    bugs = 'roaches'
    area = 'living room'
    print(f'{bugs} {area}')
    ```
    
- 문자열의 sequence 특징
    
    ```python
    my_string = "hello"
    print(my_string[1]) -> e
    print(my_string[2:4] -> ll
    print(len(my_string) -> 5
    ```
    
- 슬라이싱
    
    ```python
    my_string = "hello"
    print(my_string[:1]) -> h
    print(my_string[2:4]) -> ll
    print(my_string[-1]) -> o
    
    **my_string[시작:끝:구간]**
    ```
    
    - 특정 인덱스 범위 내의 데이터를 잘라서 가져옴

> **list**
> 
- 값을 순서대로 저장하는 **mutable한 sequence type**
- 0개 이상의 객체 목록을 저장함
- []로 표기
- 어떠한 자료형이나 저장 가능

> **tuple**
> 
- 값을 순서대로 저장하는 **immutable한 sequence type**
- 값을 수정하지 않아야 하는 구조에 사용(다수의 값을 전달, 그룹화, 다중 할당 → 파이썬 내부 동작)
- ()로 표기
- 요소를 하나 가진 튜플을 표기해줄 때는 (value, ) 라고 표기

<aside>
💡 튜플을 변경하려고 하면 **TypeError 발생
TypeError : ’tuple’ object does not support item assignment**

</aside>

> **range**
> 
- 연속된 정수 sequence을 생성하는 **immutable한 data type**
- range(N) → 0부터 N-1까지의 숫자 sequence

### NonSequence Types

> **dict**
> 
- **순서, 중복**이 없으며 **key-value 쌍**으로 이루어진 **mutable**한 자료형
- **key는 immutable**한 자료만 사용 가능
- **value는 어떠한 data type**도 사용 가능
- 중복 시 나중에 넣은 값이 처리됨

```python
# key를 통해 value 접근
dict[key] -> value 반환

# 값 변경이 가능
```

> **set**
> 
- 순서, 중복이 없으며 **mutable한 data type**
- {}로 표기함

```python
set1 = {1, 2, 3} -> {1, 2, 3} # set는 순서가 없음. 인덱싱 불가
set2 = {1, 1, 1} -> {1} # set는 중복이 안됨
set3 = {3, 5, 6}

set1 | set3 -> {1, 2, 5, 6} # 중복되는 value는 제거
set1 - set3 -> {1, 2} 
set1 & set3 -> {3} # 교집합은 set 연산 시에만 가능
```

> **None**
> 
- 값이 없다는 것을 표현하는 data type

```python
value = None -> # None 반환
```

> **Boolean**
> 
- True, False를 표현하는 data type
- 조건문이나 반복문에 주로 사용

```python
3 > 1 -> # True
30 < 25 -> # False
bool([]) -> # 빈 리스트는 False
```

### Collection → sequence, nonsequence를 모두 포함

- 여러 개의 자료들을 처리할 수 있는 자료 구조

| Collection | 변경 가능 여부 | 순서 여부 |
| --- | --- | --- |
| str | X | O |
| list | O | O |
| tuple | X | O |
| set | O | X |
| dict | O | X |

---

### Type Conversion

> **암시적 형변환**
> 
- 파이썬이 자동으로 형변환 하는 것
- Boolean Type과 Numeric Type에서 가능

```python
10 + 10.0 -> 20.0
True + 3 -> 4 # True는 1, False는 0으로 처리함
```

> **명시적 형변환**
> 
- 직접 형변환하는 것
- str → integer는 형식을 맞춰야 하지만, integer → str은 모두 가능함

```python
int(3.5) -> 3 # 소수점 버림
int('3.5') -> VauleError 발생 # invalid literal for int() with base 10: '3.5'
```

---

### 연산자

> **산술 연산자 & 복합 연산자**
> 

![산술 연산자](https://prod-files-secure.s3.us-west-2.amazonaws.com/abf254f6-50fe-4a95-aaab-bf44470fc177/d594a373-70ae-4f24-8e82-928e3b3bc95a/Untitled.png)

산술 연산자

![복합 연산자](https://prod-files-secure.s3.us-west-2.amazonaws.com/abf254f6-50fe-4a95-aaab-bf44470fc177/46c7eb40-1111-4187-bb2f-ededfb8700e4/Untitled.png)

복합 연산자

> **비교 연산자 & 논리 연산자**
> 

![비교 연산자 → 모두 boolean 타입 반환](https://prod-files-secure.s3.us-west-2.amazonaws.com/abf254f6-50fe-4a95-aaab-bf44470fc177/d0b495d3-11d2-45b1-bacb-5c641dd753c6/Untitled.png)

비교 연산자 → 모두 boolean 타입 반환

**is 비교 연산자**❓

- 메모리 내 같은 객체를 참조하는지 확인(주소 확인)
- ==과는 다른 연산자

```python
1 is 1.0 -> False # SyntaxWarning 발생
```

![논리 연산자](https://prod-files-secure.s3.us-west-2.amazonaws.com/abf254f6-50fe-4a95-aaab-bf44470fc177/68778558-1550-4866-9bfe-0861e55a486e/Untitled.png)

논리 연산자

> **단축평가**
> 
- 논리 연산 중 두 번째 피연산자를 평가하지 않고 결과가 결정되는 것
- 불필요한 연산 제거, 실행 최적화

```python
words = 'ac'
('a' and 'b') in words -> False
('b' and 'a') in words-> True

3 and 0 -> 0
0 and 3 -> 0 # 0이 암시적 형변환으로 False가 발생함
0 and 0 -> 0 # 단축평가
```

> **멤버십 연산자 (in, not in)**
> 
- 특정 값이 sequence나 다른 collection에 속하는지 확인

> **시퀀스형 연산자**
> 
- +와 *는 sequence간 연산에서 산술 연산자일 때와 다른 역할
- +는 결합, *는 반복의 의미

> **연산자 우선순위**
> 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/abf254f6-50fe-4a95-aaab-bf44470fc177/d23b468b-fddb-4a2a-898b-4ba62d825c2d/Untitled.png)

### **과제 하면서 추가로 배운 점**

> **깊은 복사 vs 얕은 복사**
> 

```python
list1을 list2에 백업하고, list1을 바꿔 두 리스트를 비교하여
boolean type으로 반환하는 요구사항
list1 = [[a], [b], [c]]
list2 = list1
list1[2] = [d]
-> 얕은 복사로 인해 list1을 변경하면 list2까지 변경되어 백업
의미가 없어진 상황

=> 깊은 복사를 사용
import copy
list1 = [[a], [b], [c]]
list2 = copy.deepcopy(list1)
b는 새로운 객체로 copy 되었기 때문에, a를 변경해도 b는 변하지 않음

=> 리스트 내부에 immutable한 객체가 있다면, 얕은 복사여도 a가 변할 때 b가 변하지 않음
mutable 변수 내부, mutable이 있는 경우에만 해당
```

---