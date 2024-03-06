HTML

# HTML/CSS


## HTML (Hypertext Markup Language)

> **구조**
> 
- <!DOCTYPE html>
    - 해당 문서가 html 문서라는 것을 표기
- <html></html>
    - 전체 페이지 콘텐츠를 포함
- <title></title>
    - 브라우저 탭 및 즐겨찾기 시 표시되는 제목

**HTML Attributes(속성)**

규칙 

- 요소 이름과 속성 사이에 공백
- 하나 이상의 속성들이 있는 경우, 속성 사이에 공백
- 열고 닫는 따옴표로 감싸야 함

> **body tag**
> 
- img 태그 → 컨테츠가 없어서 닫는 태그가 없음
- emphasis → 기울임 꼴
- strong → 굵게
- ol, li, ul → 리스트 형태
- br → 한 줄 띄어쓰기

## CSS

- 웹 페이지의 디자인과 레이아웃을 구성

```css
h1 {
	color : blue;
	font-size: 30px;
}
```

### CSS 적용 방법

1. 인라인(Inline) 스타일
    - HTML 요소 안에 style 속성 값으로 작성
    
2. 내부(Internal) 스타일 시트
    - head 태그 안에 style 태그 작성

1. 외부(External) 스타일 시트
    - 외부의 css 스타일 시트를 불러오는 것

### CSS Selectors

HTML 요소를 선택하여 스타일을 적용할 수 있도록 하는 선택자

```css
<style>
    * { # 모든 요소 선택
      color : red;
    }

    h2 {
      color : orange;
    }

    h3,
    h4 { # 공백을 기준으로 여러 가지 요소 선택
      color : blue; 
    }
    
    .green { # 클래스가 green인 모든 속성 선택
      color : green;
    }
		
		#purple { # 주어진 아이디 속성을 가진 요소 선택
							# 문서 내에서 같은 id 속성을 갖지 않는 것을 권장
      color : purple;
    }
  </style>
```

> **결합자**
> 
- 자손 결합자 (” “(space))
    - 첫 번째 자손 요소 선택
    - p span은 <p> 안에 있는 모든 <span> 선택
    
- 자식 결합자 (”>”)
    - 첫 번째 요소의 직계 자식만 선택
    - ul >li는 <ul> 안에 있는 모든 <li> 선택

### 명시도 specificity

- 결과적으로 적용할 css 선언을 결정하기 위한 로직

> **Cascade - 계단식**
> 

동일한 가중치를 가진 선택자라면, css에서 마지막에 나오는 선언이 사용됨

```css
h1 {
	color : red;
}
h1 {
	color : purple;
}
--> purple이 적용됨
```

> **명시도 순서**
> 
1. Importance → !important
2. Inline 스타일
3. 선택자 (id 선택자 > class 선택자 > 요소 선택자)
4. 소스 코드 선언 순서

---

### CSS 상속

- 부모 요소의 속성을 자식에게 상속하여 재사용성 높임

### 참고

- 인라인 스타일은 되도록 사용x
- 속성은 되도록 class만 사용
    - 여러 선택자를 사용한다면 우선순위 규칙에 따라 예기치 못한 스타일이 적용될 수 있어 유지보수가 어려움