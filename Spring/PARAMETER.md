PARAMETER
# 매개 변수 이름 인식 문제
```
Name for argument of type [java.lang.String] not specified, and parameter name information not available via reflection. Ensure that the compiler uses the '-parameters' flag.
```
라는 오류 발생
- 스프링 부트 3.2부터 매개변수의 이름을 인식하지 못하는 문제이다.
<aside>
@RequestParam, @PathVariable, @Autowired, @ConfigurationProperties 같은 애노테이션 사용 시 발생한다.
</aside>
---

해결 방법
1. 애노테이션에 이름 생략하지 않고 넣기
- @RequestParam("username") String username

2. 컴파일 옵션 -parameters 추가
- settings -> Build, Excution, Deployment -> Compiler -> Java Compiler
- Additional command line parameters에 -parameters 추가
- out 폴더 삭제 후 재 실행

3. Gradle 사용하여 빌드 및 실행