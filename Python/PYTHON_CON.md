PYTHON_CON
### 모듈

- 변수와 함수의 모음으로 특정한 기능을 동작

> 모듈 예시 - math
> 
- pi(파이 값) 변수나 sqrt(제곱근) 함수

<aside>
💡 **모듈 활용하기
- import로 모듈 가져오기
- import 모듈 / from 모듈 import 함수 명**

</aside>

> 주의 사항
> 
- 서로 다른 모듈이 같은 이름의 함수를 제공 → 마지막에 import된 함수 적용

---

### 제어문

- 코드의 흐름을 제어하는 문장
- 조건에 따라 실행하는 코드 블록을 제어

> **조건문**
> 

```python
if 표현식:      # 가장 먼저 실행
		코드 블록
elif 표현식:    # if가 아니면 elif 검증
		코드 블록
else:           # 모두 아니면 실행
		코드 블록
```

> **반복문**
> 
- 주어진 코드 블록을 여러 번 반복

> **for**
> 
- 조건식만큼 반복

> **while**
> 
- 조건식이 False가 될 때까지 반복문이 반복

> enumerate
> 

```python
for index, fruit in enumerate(fruits):
	print(f'인덱스 {index} : {fruit}')
```