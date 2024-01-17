PYTHON_FUNC
### 함수

- 특정한 기능을 사용하기 위해 구현해 놓은 코드 모음
- 코드의 가독성이 좋아지며, 재사용성, 유지 보수가 용이함

```python
def function(param):
		
		~ 로 정의

if __name__ == '__main__':
		function(argument)  # main 함수에서 호출하여 사용한다
```

> **내장 함수**
> 
- 파이썬이 제공하는 함수

> **함수 호출**
> 
- 함수를 실행하기 위해 함수의 이름을 호출하는 것
- 함수 반환 명령어 return 이후 함수는 종료

---

### 매개변수와 인자

> **Positional Argument 위치 인자 ( param )**
> 
- 함수 호출 시 위치에 따라서 전달됨
- 반드시 전달되어야 함

> **Default Argument Values 기본 인자**
> 
- 함수를 정의할 때, 기본 값을 할당
- 인자가 넘어오지 않는다면, 기본 값이 매개변수로 전달

> **Keyword Arguments 키워드 인자 ( keyword = “”)**
> 
- 인자의 이름과 함께 value를 전달
- 인자의 순서에 상관없이 해당 이름 값에 전달

❌ 위치 인자는 키워드 인자 뒤에 쓸 수 없음

> **Arbitrary Argument Lists 임의의 인자 목록 (*args)**
> 
- 인자가 정해지지 않았을 때 처리
- 매개변수 앞에 ‘*’를 붙여 사용, 인자들을 tuple로 처리함

> **Arbitrary Keyword Argument Lists 임의의 키워드 인자 목록(**kwargs)**
> 
- 정해지지 않은 키워드 인자를 처리
- ‘**’를 붙여 사용, dictionary로 전달 받은 인자를 처리

> **함수 인자 권장 작성순서**
> 
- 위치 → 기본 → 가변 → 가변 키워드

```python
def func(pos1, pos2, age=30, *args, **kwargs)
	print(pos1, pos2, age, args, kwargs)

func(1, 2, 3, 4, 5) -> 1 2 3 (4 5) {}
func(1, 2, 3, a=100, b=200) -> 1 2 3 () {'a':100, 'b':200}
```

---

### 함수와 Scope

> **Python의 Scope**
> 
- function 내부는 local scope로 지역 변수로 선언됨. global scope로 전역 변수로 선언하고자 한다면
    
    →  global 명령어로 전역 변수 설정
    

> **변수 수명 주기**
> 
- 변수의 선언 위치나 scope에 따라서 수명이 결정

1) **built-in scope** : 실행부터 영원히 유지

2) **global scope** : 모듈이 호출된 시점 이후나 인터프리터가 끝날 때까지 유지

3) **local scope** : 함수가 호출되면서 생성, 종료되면서 사라짐

> **이름 검색 규칙**
> 
1. Local scope : 지역 범위
2. Enclosed scope : 지역 범위 한 단계 위
3. Global scope : 최상단에 위치
4. Built-in scope : 모든 것을 담고 있음
- 작은 영역부터 바깥으로 찾아나감
- 함수 내에서는 바깥 변수로 접근은 가능하지만 수정은 불가능

> **LEGB Rule 예시**
> 
- sum이라는 이름을 global scope에서 사용 → 기존 내장함수 sum 사용 불가

```python
sum = 5
print(sum(range(3))) -> # TypeError : 'int' object is not callable
```

---

### 재귀 함수

- 함수 내부에서 그 함수를 또 다시 호출하는 함수
- 변수 사용이 줄고, 가독성이 향상
- 함수의 종료 시점이 존재하도록 해야 함

---

### 유용한 내장 함수

- map과 zip 함수

> **map(function, iterable)**
> 
- 순회 가능한 데이터 구조의 모든 요소에 함수를 적용 → map object로 반환

> **zip(*iterables) → 가변인지**
> 
- 임의의 iterable을 모아 튜플을 원소로 하는 zip object로 변환

> **lambda 함수 → lambda 매개변수 : 표현식**
> 
- 일회성 함수
- addition = lambda x, y : x + y

### Packing & Unpacking

> **Packing**
> 
- 여러 개의 변수를 하나로 묶는 것
- 변수에 담긴 값 → 튜플로 표기

```python
'*'을 활용한 패킹
1) 
num = [1, 2, 3, 4, 5]
a, *b, c = num
b = [2, 3, 4]

2) print 함수에서 임의의 가변 인자를 작성할 수 있는 이유
-> 인자 개수에 상관 없이 튜플 하나로 패킹되어 내부 처리
print()에는 기본 인자로 end='\n'이 주어져 있기 때문에, 바꿀 수 있음
```

> **Unpacking**
> 
- 패킹된 변수 값을 분할하는 것
- 객체 요소를 개별 변수에 할당

> **‘*’을 활용한 언패킹**
> 

```python
num = ['a', 'b', 'c']
print(*num) -> # a b c
```
---