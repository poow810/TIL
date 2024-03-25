start_3

### ORM

---

- 객체 지향 프로그래밍 언어를 통해 호환되지 않는 유형의 시스템 간 데이터를 변환하는 기술
- Django(python object) ↔ Database(sql)

### QuerySet API

---

- ORM에서 데이터를 검색, 정렬 및 그룹화를 위한 도구
- SQL이 아닌 python 코드를 통해 데이터를 변환하기 위한 API

> **구문**
> 

---

<aside>
💡 Article.objects. all()
(Model class)(manager)(API)

</aside>

### CRUD

---

> **Create**
> 
- save(), create()로 생성

> **Read**
> 
- filter → 항상 QuerySet을 반환
- get → 단일 데이터 조회
    - 해당 데이터가 없을 경우 DoesNotExist 예외 발생
    - 해당 데이터가 여러 개일 경우 MultipleObjectsReturned 예외 발생
    - 고유한 성질을 가진 pk로 조회하는 것이 가장 이상적

> **Update**
> 
- 조회를 통해 데이터를 가져와서 save()로 update해줌

> **Delete**
> 
- 조회를 통해 데이터를 가져와서 delete()
- save()가 필요 없음

### 참고

---

> Field lookups
> 
- 특정 레코드에 대한 조건을 설정하는 방법
- filter(), exclude(), get() 메서드 키워드 인자

```jsx
Article.objects.filter(content__contains="aaa")
# content에 "aaa"를 포함하고 있는 모든 데이터 조회
```