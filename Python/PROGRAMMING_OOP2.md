PROGRAMMING_OOP2
### 상속

- 기존 클래스의 속성과 메소드를 물려받음

> **필요성**
> 
1. 코드 재사용
    - 기존의 클래스 속성과 메서드를 재사용

1. 계층 구조
    - 클래스 간 계층 구조를 표현할 수 있음

1. 유지 보수
    - 기존 클래스의 수정이 필요한 경우 해당 클래스만 수정하면 되기 때문에 최소한의 작업이 가능함

```python
class Person():

		def __init__(self, name, age):
				self.name = name
				self.age = age

		def talk(self):
				print(f"반갑습니다. {self.name}입니다.")

class Professor(Person):
		~

p1 = Professor('교수', 49)
p1.talk # 반갑습니다. 교수입니다.
```

> **오버라이딩**
> 
- 자식 클래스에서 부모 클래스의 메서드를 재정의해서 사용하고자 할 때 사용

```python
class Person():

		def __init__(self, name, age):
				self.name = name
				self.age = age

		def talk(self):
				print(f"반갑습니다. {self.name}입니다.")

class Professor(Person):
		
		def __init__(self, name, age):
				self.name = name
				self.age = age

		def talk(self):
				print("안녕하세요")  # 재정의 시 안녕하세요 출력
```

> **super 함수**
> 
- 자식 클래스에서 오버라이딩을 통해 재정의를 하고 싶지만, 부모 클래스의 속성도 사용하고자 할 때 사용

```python
class Person():

		def __init__(self, name, age):
				self.name = name
				self.age = age

		def talk(self):
				print(f"반갑습니다. {self.name}입니다.")

class Professor(Person):
		
		def __init__(self, name, age):
				self.name = name
				self.age = age

		def talk(self):
				super().talk()
				print("안녕하세요")  # 재정의 시 안녕하세요 출력
				
```

- super().메서드 이름(매개 변수)로 정의함

> **다중 상속**
> 
- 둘 이상의 상속을 받는 것
- 중복된 속성, 메서드가 있을 시 상속 순서 결정

> **MRO**
> 
- 메서드 결정 순서
- 해당 인스턴스의 클래스가 어떤 부모 클래스를 가지는지 확인
- 부모 클래스가 여러 번 액세스 되지 않도록 순서를 보존
- 메서드 호출 순서를 예측할 수 있음

### 에러와 예외

> **문법 에러 예시**
> 

```python
while # invalid syntax (문법 오류)
5 = 3 # assign to literal (잘못된 할당)
print('hello # EOL while scanning string literal (End of Line)
print( # unexpected EOF while parsing (End of File)
```

> **예외**
> 

```python
10/0 # ZeroDivisionError : 나누기 또는 모듈로 연산의 두 번째
		 # 인자가 0일 때 발생

print(name_error) # NameError : is not defined 정의 x

'2' + 2 # TypeError 타입 불일치

sum() # TypeError 인자 누락

sum(1, 2, 3) # TypeError 인자 초과

random.sample(1, 2) # TypeError 인자 타입 불일치

int('1.5') # ValueError
range(3).index(6) # ValueError
# 연산에는 문제가 없지만 부적절한 값을 가진 인자를 받음

empty_list = []
empty_list[2] # IndexError : list index out of range

person = {'name': 'Alice'}
person['age'] # KeyError: 'age' 해당 키 존재하지 않음

import haha # ModuleNotFoundError - 모듈을 찾을 수 없음
from random import haha # ImportError - 임포트 이름 없음

while True:
		continue # KeyboardInterrupt - 사용자에 의해 종료(ctrl+c, delete)

for i in range(10):
print(i)     # IndetationError : 잘못된 들여쓰기
```

### 예외 처리

> **try - except 구조**
> 
- try 블럭 안에는 예외 발생할 수 있는 코드
- except 블럭 안에는 예외가 발생했을 때 처리 방법