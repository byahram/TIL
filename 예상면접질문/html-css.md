# 예상 면접 질문 - HTML/CSS

---
<p align="center">
<img width="50%" src="../assets/img/interview.png">
</p>

---

<br>

### 웹 표준, 웹 접근성이란?
* '웹 표준'이란 웹에서 표준적으로 사용되는 기술이나 규칙입니다. 표준안 단체인 W3C가 권고한 표준안에 따른 규칙이다.
  * 장점은 개발 및 운영의 효율성 제고 즉 소스의 통일화로 수정 및 운영 관리가 용이하다. 접근성이 향상된다. 유지 보수에 들어가는 시간이 단축되고 로딩 속도가 향상된다. 스크린 리더기 등 보조 공학 기기 사용자들이 조금 더 정확한 정보를 얻을 수 있다. 검색 봇을 통한 효율적 노출과 같은 검색 엔진 최적화가 가능하다. 웹 표준은 접근성, 사생활 보호, 보안, 국제화의 측면에서 고려해야 한다.

* '웹 접근성'은 몸이 불편한 사람이라도 정보를 이용하는데 불편함이 없도록 하는 것이 목적에 있기 때문에 만약 시각 장애인이 사이트를 이용할 경우 텍스트는 리더기로 읽어줄 수 있지만 이미지는 읽을 수가 없다 그래서 이미지에 텍스트를 붙여준다. (신체적 차이나 장애 여부와 상관없이 누구나 원활하게 웹페이지를 이용할 수 있어야 한다는 것)

<br>

### 반응형은 무엇으로 작업하는가?
레이아웃을 잡을 때 display: flex 혹은 grid로 잡아주고 vh, %, vw, vmin, vmax 등 상대 단위를 이용하여 작업해 줍니다. 그 후 미디어 쿼리를 이용하여 세부 적인 작업을 해준다.

<br>

### 레거시 코드
유산, 산물이 된 코드라서 해석하며 더 이상 쓰기 힘들거나 화나게 만드는 코드를 일컫는다.

<br>

### IR 효과
IR 기법은 이미지의 대체 텍스트를 제공하기 위한 CSS 기법으로 .ir_pm, .ir_wa, .ir_so가 있다.
* .ir_pm : 의미 있는 이미지의 대체 텍스트를 제공하는 경우
* .ir_wa : 의미 있는 이미지의 대체 텍스트로 이미지가 없어도 대체 텍스트를 보여주고자 할 때 사용
* .ir_so : 대체 텍스트가 아닌 접근성을 위한 숨김 텍스트를 제공할 때 사용

<br>

### 스프라이트 효과
이미지 스프라이트(image sprite)란 여러 개의 이미지를 하나의 이미지로 합쳐서 관리하는 이미지를 의미한다. 이러한 방식을 사용하는 이유는 웹 사이트의 로딩 시간을 줄이기 위해서다.

<br>

### 시멘틱 태그
사용 이유 :
* HTML 소스 코드만 보고도 어느 부분인지 쉽게 알 수 있기 때문인데 스크린 리더기 등 몸이 불편한 사람도 사이트의 구조를 소리로 구분할 수 있게 해준다.
* 태그들의 의미가 분명하다면 검색 엔진 입장에서 구분하기가 쉬워진다.
* 코드 가독성 및 유지 보수가 쉬워진다.

종류 :
* \<header> : 사이트의 로고나 이름 등에 사용
* \<nav> : 웹페이지의 메뉴를 만들 때 사용
* \<main> : 메인 컨텐츠를 나타내는데 사용
* \<section> : 제목 별로 나눌 수 있는 문서의 컨텐츠 영역을 구성하는 요소
* \<article> : 개별 컨텐츠를 나타내는 요소
* \<aside> : 좌우측의 사이드 영역 부분
* \<footer> : 사이트의 바닥 부분, 회사 주소나 연락처 등에 사용
* \<hgroup> : 제목과 부제목을 묶어서 나타내는 요소
* \<article>과 \<section>의 차이 : article 태그는 section과 다르게 독립적으로 존재할 수 있고 재 사용 할 수 있다. 즉 article이 좀 더 구체적이다.

<br>

### CSS 우선 순위
* 속성 값 뒤에 !important를 붙인 속성
* HTML에서 style을 직접 지정한 속성
* #id로 지정한 속성
* .클래스, :추상 클래스로 지정한 속성
* 태그 이름으로 지정한 속성
* 상위 객체에 의해 상속된 속성

<br>

### position 속성
HTML 문서 상에서 요소가 배치되는 방식을 결정한다.
* position: static - 기본값
* position: relative - 요소를 원래 위치에서 벗어나게 배치 할 수 있다.
* position: absolute
* position: fixed - 화면을 위아래로 스크롤 하더라도 브라우저 화면을 특정 부분에 고정되어 움직이지 않는다.
* position: sticky - fixed가 브라우저 화면의 절대 위치를 사용하는 반면 sticky는 부모 태그의 절대 위치값을 사용한다.

<br>

### block, inline-block inline 차이
* **inline** : text 크기 만큼만 공간을 점유하고 줄바꿈을 하지 않는다.
* **block** : 무조건 한 줄을 점유하고 있고 다음 태그는 무조건 줄바꿈이 적용된다.
* **inline-block** : inline과 block 속성의 특징을 둘 다 가지고 있는 속성으로 기본적인 특징은 inline 속성과 비슷한데 (줄바꿈 x, 동일한 라인에 작성 가능) inline 속성에서 할 수 없었던 width/height 변경 및 line-height를 적용할 수 있다.

<br>

### data 속성
HTML5부터 데이터 속성이라는 개념이 추가 됐고 HTML 요소의 'data-'로 시작하는 속성이다. 특정한 데이터를 DOM 요소에 저장해두기 위함이 목적이다.

<br>

### 크로스 브라우징 
최대한 많은 종류의 웹 브라우저에서 정상적으로 작동하는 웹페이지를 만드는 방법론 중 하나이다.

<br>

### SEO, 최적화 방법
웹사이트가 유기적인(무료) 검색 방식을 통해 검색 엔진에서 상위에 노출될 수 있도록 최적화 하는 과정을 말한다.
* HTML 문법에 맞게 작성 \<strong>, \<em> 태그를 통해 강조하고 싶은 키워드에 사용하고 \<title> 태그에도 제목을 기재하는 방법이 있다.
* 메타 태그 이용 메타 키워드나 메타 디스크립션에 내용을 기재한다.
* 이미지에 Alt 속성을 넣는 방법도 있다.

<br>

### id & class 차이
여러가지 스타일링을 한꺼번에 적용해야 할 때는 클래스(class)를 사용하고, 한 가지만 적용하고 싶다면 아이디(id)를 사용 하면 된다.

<br>

### css, sass, scss 차이점
<https://velog.io/@yon3115/css-sass는-무엇이며-차이점은>

<br>
