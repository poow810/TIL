PROGRAMMING_OOP

## Programming

> 객체 지향 프로그래밍 - Object Oriented Programming
> 
- 데이터와 해당하는 메서드를 object로 관리하는 방식

> **클래스**
> 
- 타입을 표현하기 위한 방법
- 객체를 생성하는 설계도

> **객체**
> 
- 메모리에 할당된 정보
- property를 가지고 있음
- 타입에 따라 다루는 인스턴스가 달라짐

> **인스턴스와 클래스 간 공간**
> 

```python
class Person:

	name = "철수"
	
	def talk(self):
		print(self.name)

p1 = Person()
p1.talk() # 철수

p2.talk() # 철수
p2.name = "짱구"
p2.talk() # 짱구
p1.talk() # 철수

-> p2의 속성을 바꾸면 인스턴스 p2의 속성이 바뀐 것이지,
Person 클래스의 name 속성이 바뀐 것이 아니다.
```

### 메서드

> **인스턴스 메서드**
> 
- 클래스 내부의 기본 메서드
- 첫 번째 매개변수는 반드시 self(인스턴스 자신)

```python
class Person:
		
		def instance_method(self, arg1, arg2,...):
				pass
```

> **생성자 메서드**
> 
- 인스턴스 객체가 생성될 때 자동으로 호출되는 메서드
- 인스턴스 생성 시 초기값을 정해주며, 초기화

 

> **클래스 메서드**
> 
- 클래스 내부에서 동작하는 메서드
- @classmethod 데코레이터를 사용
- 첫 번째 인자는 클래스

```python
class Person:
		
		@classmethod
		def class_method(cls, arg1, ...):
				pass
```

> **스태틱 메서드**
> 
- 클래스, 인스턴스와 무관하게 동작
- 상호작용 없이 정적인 상태를 나타낼 때 사용

```python
class Person:

		@staticmethod
		def static_method(arg1, ...):
				pass
```