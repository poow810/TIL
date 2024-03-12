start_1

### Client

---

서비스를 요청하는 주체(웹 브라우저)

### Server

---

클라이언트의 요청에 응답하는 주체(컴퓨터)

<aside>
💡 파이썬은 패키지를 여러 개 가질 수 없음
—> 가상 환경을 여러 가지 생성

</aside>

### 가상 환경

---

```bash
$ python -m venv venv

$ source venv/Scripts/activate # 가상 환경 실행

$ python manage.py runserver # 장고 서버 실행

$ django-admin startproject todo_list_project # 프로젝트 생성
$ python manage.py startapp articles # 앱 생성

```

**앱 생성 후 등록❗**

```bash
INSTALLED_APPS = [
		'articles', 
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]

# 여기에다가 생성한 articles 등록
```

### 디자인 패턴

> **MVC 디자인 패턴**
> 

---

Model, View, Controller의 구성요소로 데이터와 사용자 인터페이스, 비즈니스 로직을 분리함

> **MTV 디자인 패턴**
> 

---

장고에서 애플리케이션을 구조화한 패턴

### 요청과 응답

> **URLs**
> 

---

```bash
urlpatterns = [
		path(path, class.함수)
]
```

해당 경로로 요청이 왔을 때, 해당 클래스에서 동작할 함수를 호출