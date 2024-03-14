start_2
### Django Template Language(DTL)

---

Template에서 조건이나 반복, 변수같은 프로그래밍 기능을 제공

1. Variable
    - render 함수의 세 번째 인자로 딕셔너리 데이터 사용
    - key에 해당하는 문자열이 template에서 사용 가능한 변수명
    - dot(’.’)을 이용하여 변수 속성 접근 가능
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/abf254f6-50fe-4a95-aaab-bf44470fc177/d9ddcd94-e9c4-4e04-8978-740637e18e2c/Untitled.png)
    

1. Filters
    - 표시할 변수를 수정할 때 사용 (변수 | 필터)
    - 필터로는 인자도 받을 수 있음
    
2. Tag
    - 반복 or 논리 수행
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/abf254f6-50fe-4a95-aaab-bf44470fc177/d62e89a3-ff9e-4892-bee0-50f93dad18ed/Untitled.png)
    

### 템플릿 상속

---

페이지의 공통 요소를 포함, 하위 템플릿을 재정의할 수 있는 skeleton 템플릿을 작성

```html
{% extends "p.html" %} # 부모 html을 상속 받음

{% block content %}
	# 자식 html이 
	# 바꿀 수 있는 content들
{% endblock content %}	
```

### HTML form (요청과 응답)

---

HTML form 요소를 통해 사용자와 애플리케이션 간 상호작용

**⚡ 로그인 폼**

```html
<form action="#" method="GET">
	<div>
		<label for = "name">아이디 : </label>
		<input type ="text" id="name">
	</div>
	<div>
		<label for ="password">패스워드 : </label>
		<input type ="password" name="password" id="password">
	</div>
	<input type ="submit" value ="로그인">
</form>
```

→ 사용자로부터 받은 데이터를 서버로 전송하는 역할

> **Action & method**
> 

---

데이터를 어디로 요청? 무슨 방식으로?

- action
    - 데이터가 전송될 URL
- method
    - 데이터 전송 방식(GET, POST)