# 예상 면접 질문 - REACT/VUE

---
<p align="center">
<img width="50%" src="../assets/img/interview.png">
</p>

---

<br>

### 리액트란?
<details>
  <summary>Click me</summary>

사용자 인터페이스를 만들기 위한 웹 프레임워크, SPA, 웹/앱(앱과 사용성이 동일한 웹)을 만들기 위해 사용.

</details>

<br>

### 리액트의 특징
<details>
  <summary>Click me</summary>

* Virtual DOM
* 단방향 데이터 바인딩
* JSX
* 컴포넌트 기반
* porps, state

</details>

<br>

### 리액트를 사용하는 이유
<details>
  <summary>Click me</summary>

* 앱으로 발행이 쉽다. 앱처럼 만들었으니까.
* 가장 큰 이유 - 사용자에게 긍정적 느낌을 줌. 빠른 느낌.
* 일반 사이트보다 비즈니스적으로 강점 - 구매 전환율이 실제로 늘었다고 함.
* 사용자와 상호작용 할 수 있는 동적인 UI를 쉽게 만들 수 있다.

</details>

<br>

### 리액트 장단점
<details>
  <summary>Click me</summary>

장점 : 
* React 공식 문서 가이드와 방대한 커뮤니티, 자료를 통해 쉽게 접하고 배울 수 있다.
* Controller, directive, template, model, view 처럼 로직을 분리하는 것이 아닌, Component 하나로 관리를 한다. (이게 view 역할을 담당)
* 성능이 뛰어난 가비지 컬랙터, 메모리 관리 기능을 지원한다.
* UI 수정과 재 사용성이 좋으며, 코드 가독성을 높일 수 있다.
* 다른 framework나 라이브러리와 병행해서 사용할 수 있다. 이는 개발이 이미 완료된 프로젝트에도 적절히 녹여낼 수 있는 확장성도 포함한다.

단점 :
* IE8 이하 버전은 지원하지 않는다.
* view 이외의 기능은 직접 구현하거나 라이브러리를 사용해서 구현해야 하기에 javascript 배경 지식이 필수 선행이다.
* 데이터 모델링, 라우팅, Ajax 등 기능 지원이 안된다.
* (치명적) 로딩 시간이 길다.
* 웹의 궁극적 지향점 과는 다소 동 떨어져 있다.a. 웹의 핵심: 모든 것을 streaming하며, 페이지들은 HTML 태그들을 내포하고 가벼운 response만 브라우징 한다.b. 리액트: 사이트에 필요한 자바스크립트를 처음에는 공백 페이지를 띄우며 다운로드 한다. 한번 다운로드 한 이후에는 다시 리소스를 다운하지 않아도 되지만, 처음 보이는 것이 없다는 것이 streaming 과의 차이이다.

</details>

<br>

### DOM
<details>
  <summary>Click me</summary>

* <https://velog.io/@solmii/TIL-DOM%EC%9D%B4%EB%9E%80>
* <https://dev-cini.tistory.com/10>
* <https://ko.reactjs.org/docs/dom-elements.html>
* 브라우저에서 다룰 HTML 문서를 파싱한 뒤, 요소들을 객체로 만들어 tree 형태로 구조화한 것.
* DOM(Document Object Model)은 웹 페이지를 이루는 태그들을 자바스크립트가 이용할 수 있게끔 브라우저가 트리구조로 만든 객체 모델을 의미한다.
* DOM(Document Object Model)을 영어 뜻풀이 그대로 하자면 문서 객체 모델을 의미한다.
* 문서 객체란 html, head, body와 같은 태그들을 javascript가 이용할 수 있는 (메모리에 보관할 수 있는) 객체를 의미한다.

</details>

<br>

### Virtual DOM
<details>
  <summary>Click me</summary>

* <https://velog.io/@mollog/React서의-가상돔-개념>
* <https://dev-cini.tistory.com/11>
* 가상의 DOM. DOM Tree 구조와 같은 구조체.
* DOM을 반복적으로 직접 조작하면 브라우저가 렌더링을 자주 하게 되고, 그만큼 PC 자원을 많이 소모하게 되는 문제를 해결하기 위한 기술.

</details>

<br>

### Virtual DOM 의 작동 원리
<details>
  <summary>Click me</summary>

* <https://weekwith.tistory.com/entry/React%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83-01-DOM%EA%B3%BC-Virtual-DOM-%EA%B7%B8%EB%A6%AC%EA%B3%A0-CDN>
* <https://velog.io/@zero_mountain/React-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EC%99%80-DOM-%EC%B2%98%EB%A6%AC-%EB%B9%84%EA%B5%90>
* UI 가상 표현을 메모리에 두고 재 조정 과정을 통해 실제 DOM과 동기화.

</details>

<br>

### 상태 관리 라이브러리
<details>
  <summary>Click me</summary>

리액트에서 사용하는 유동적인 데이터를 담는 변수인 State를 전역적으로 관리하는 툴을 말한다. 지역적인 state의 문제점 때문에 사용함.

</details>

<br>

### 왜 상태 관리 라이브러리가 필요할까?
<details>
  <summary>Click me</summary>

* 상태가 전역으로 다루어야 할 때가 생김.
* 여러 컴포넌트가 공통으로 사용할 상태를 공유할 시점에 복잡한 구조와 계층이 생성됨.
* context API가 있지만 아직 성능 적인 이슈가 존재함.

</details>

<br>

### Redux
<details>
  <summary>Click me</summary>

JavaScript 상태 관리 라이브러리며 상태를 예측 가능하게 만든다. 유지 보수가 좋다. 디버깅에 유리하다. 상태를 전역에서 줄 수 있음. 리덕스를 사용하면 상태값을 컴포넌트에 종속 시키지 않고, 상태 관리를 바깥에서 할 수 있게 해준다.

</details>

<br>

### npm
<details>
  <summary>Click me</summary>

* NPM은 (Node Package Manger)의 약자로 명령어로 자바스크립트 라이브러리를 설치하고 관리하는 패키지 매니저다.
* 자바스크립트 라이브러리를 관리해주는 도구이다.
* node.js에서의 앱스토어(패키지 다운로드 저장소)

</details>

<br>

### 함수형 vs 클래스형
<details>
  <summary>Click me</summary>

* 함수형 컴포넌트는 함수를 기반으로 작성 된 것으로 클래스형 컴포넌트에 비해 짧고 직관적으로 코드를 짤 수 있고 현재 대부분이 함수형 컴포넌트를 사용 중입니다.
* 클래스형 컴포넌트는 함수형 컴포넌트와 Hook이 등장하기 이전에 사용하던 컴포넌트이고 함수형 컴포넌트의 역할과 동일합니다. 차이점은 표현 방법이 더 명시적이고 state기능과 생명 주기 기능을 이용할 수 있습니다.
</details>

<br>

### Side-Effect
<details>
  <summary>Click me</summary>

함수가 실행되면서 함수 외부에 존재하는 값이나 상태를 변경 시키는 등의 행위, React에서는 Side-Effect 처리를 위해 useEffect()함수를 제공합니다.

</details>

<br>

### useState, useEffect
<details>
  <summary>Click me</summary>

* useState는 함수형 컴포넌트에서 상탯값을 관리하게 해줍니다.
* useEffect는 어떤 Effect를 발생 시키고 싶을 때 사용합니다. effect는 명령형 함수 또는 타이머, 로깅, 변형, sideEffect등 을 발생 시키는 함수 등을 말합니다.

</details>

<br>

### useEffect / useLayoutEffect의 차이점
<details>
  <summary>Click me</summary>

* useEffect : 비동기적으로 실행. render, print가 된 후 실행. 그래서 내부에 DOM에 영향을 주는 코드가 있을 시, 화면에 깜빡임.
* useLayoutEffect : 동기적으로 실행. render 된 후 실행, 이후에 paint 실행. pain가 되기 전에 실행하기 때문에 dom 조작 코드가 존재하더라도 깜빡이지 않음.

</details>

<br>

### webpack
<details>
  <summary>Click me</summary>

웹에서 사용되는 모든 자원(assets)을 번들링 해주는 도구이며 모듈 번들러(Module Bundler)이다. 모듈 번들링이란 웹 서비스를 구성하는 많은 자원들을 하나의 파일로 병합/압축하는 것을 모듈 번들링 이라고 한다. 웹팩은 파일들 간의 연관 관계를 파악하여 하나로 변환하고 최적화 한다. (=하나로 합친다는 관점)

</details>

<br>

### Router
<details>
  <summary>Click me</summary>

* <https://goddaehee.tistory.com/305?category=395445>
* Router는 신규 페이지를 불러오지 않는 상황에서 각각의 url에 따라 선택된 데이터를 하나의 페이지에서 렌더링 해주는 라이브러리 입니다. SPA의 경우 서버에서 사용자에게 제공하는 페이지는 한 종류이지만, 해당 페이지는 로딩 된 자바스크립트와 현재 사용자 브라우저의 주소에 따라 다양한 화면을 보여 줄 수 있습니다. 이 때 다른 주소에 다른 화면을 보여주는 것을 라우팅이 라고 합니다.
* 웹 사이트에서 전체 페이지를 한 페이지에 담아 자바스크립트를 이용해 화면을 바꿔가며 보여주는 방식. 리액트, 뷰, 앵귤러가 SPA 프레임워크.
* 라우팅이란 출발지에서 목적지까지의 경로를 결정하는 기능이다. 애플리케이션의 라우팅은 사용자가 태스크를 수행하기 위해 어떤 화면(view)에서 다른 화면으로 화면을 전환하는 내비게이션을 관리하기 위한 기능을 의미한다. 일반적으로 라우팅은 사용자가 요청한 URL 또는 이벤트를 해석하고 새로운 페이지로 전환하기 위해 필요한 데이터를 서버에 요청하고 페이지를 전환하는 위한 일련의 행위를 말한다.
* 브라우저가 화면을 전환하는 경우는 다음과 같다.
  1. 브라우저의 주소창에 URL을 입력하면 해당 페이지로 이동한다.
  2. 웹페이지의 링크(a 태그)를 클릭하면 해당 페이지로 이동한다.
  3. 브라우저의 뒤로가기 또는 앞으로가기 버튼을 클릭하면 사용자 방문 기록(history)의 뒤 또는 앞으로 이동한다. history 관리를 위해서는 각 페이지는 브라우저의 주소창에서 구별할 수 있는 유일한 URL을 소유해야 한다.

</details>

<br>

### SPA 장점과 단점
<details>
  <summary>Click me</summary>

<https://poiemaweb.com/js-spa>

SPA란 한 개의 페이지로 이루어진 애플리케이션이라는 의미이며 새로 고침 없이 변경 사항에 대해 서버에 요청을 보내고 변경된 부분의 데이터 만을 서버로부터 전달 받아 클라이언트가 렌더링 한다.

장점 :
* 단일 페이지 애플리케이션(Single Page Application, SPA)는 모던 웹의 패러다임이다. SPA는 기본적으로 단일 페이지로 구성되며 기존의 서버 사이드 렌더링과 비교할 때, 배포가 간단하며 네이티브 앱과 유사한 사용자 경험을 제공할 수 있다는 장점이 있다.

단점 : 
* **초기 구동 속도** : SPA는 웹 애플리케이션에 필요한 모든 정적 리소스를 최초 접근시 단 한번 다운로드하기 때문에 초기 구동 속도가 상대적으로 느리다. 하지만 SPA는 웹페이지보다는 애플리케이션에 적합한 기술이므로 트래픽 감소와 속도, 사용성, 반응성의 향상 등의 장점을 생각한다면 결정적인 단점이라고 할 수는 없다.
* **SEO(검색엔진 최적화) 이슈** : SPA는 일반적으로 서버 사이드 렌더링(SSR) 방식이 아닌 자바스크립트 기반 비동기 모델의 클라이언트 사이드 렌더링(CSR) 방식으로 동작한다. 클라이언트 사이드 렌더링(CSR)은 일반적으로 데이터 패치 요청을 통해 서버로부터 데이터를 응답받아 뷰를 동적으로 생성하는데 이때 브라우저 주소창의 URL이 변경되지 않는다. 이는 사용자 방문 history를 관리할 수 없음을 의미하며 SEO 이슈의 발생 원인이기도 하다. SPA의 SEO 이슈는 언제나 단점으로 부각되어 왔다. SPA는 정보 제공을 위한 웹페이지보다는 애플리케이션에 적합한 기술이므로 SEO 이슈는 심각한 문제로 취급할 수 없다고 생각할 수도 있지만 블로그와 같이 애플리케이션의 경우 SEO는 무시할 수 없는 중요한 의미를 갖는다. Angular나 React 등의 SPA 프레임워크는 서버 사이드 렌더링(SSR)을 지원하는 기능이 이미 존재하고 있고 크롬 등의 모던 브라우저는 SPA의 SEO 문제를 해결하고 있는 것으로 알려져 있다.


</details>

<br>

### 생명 주기 함수 (LifeCycle)
<details>
  <summary>Click me</summary>

컴포넌트는 생성부터 소멸 까지의 과정을 컴포넌트의 생명 주기(LifeCycle)라고 합니다. 컴포넌트는 생명 주기마다 함수를 가지고 있고 이 함수들을 이용하면 특정 시점에 원하는 동작을 하도록 만들 수 있습니다.

</details>

<br>

### 생명 주기 메서드
<details>
  <summary>Click me</summary>

<https://jongdai.tistory.com/74>

생명주기 마다 실행하는 특정 함수.

컴포넌트가 브라우저에 나타나고, 업데이트 되고, 사라지게 될 때 호출되는 메서드들
* 컴포넌트의 생성부터 소멸까지의 과정을 컴포넌트의 생명주기(Lifecycle)라고 한다. 컴포넌트는 생명주기마다 함수를 가지고 있는데 이 함수들을 이용하면 특정 시점에 원하는 동작을 하도록 만들 수 있다.
* 생명주기 함수는 render()함수를 포함하여 총 8종의 함수가 있다. 생명주기 함수는 리액트 엔진에서 자동으로 호출한다.

</details>

<br>

### 생명 주기 메서드 종류 
<details>
  <summary>Click me</summary>

* 생성 : 컴포넌트의 인스턴스 생성 ⇒ DOM에 삽입될 때 순서대로 호출.
  * **constructor()** : constuctor() 함수는 이름 그대로 '맨 처은에 생성될 때 한 번만 호출'되며, 상태(state 또는 객체 변수)를 선언할 때 사용된다. constructor() 함수를 정의할 때는 항상 super() 함수를 가장 위에 호출해야 한다. super()함수에는 프로퍼티와 생명 주기 상태 등을 초기화하는 중요한 과정을 포함하고 있다.
  * **getDerivedStateFromProps()**
  * **render()** : render() 함수는 데이터가 변경되어 새 화면을 그려야 할 때 자동으로 호출되는 함수이다. render() 함수가 변환하는 JSX를 화면에 그려준다.
  * **componentDidMount()** : componentDIdMount() 함수는 render() 함수가 JSX를 화면에 그린 이후에 호출되는 함수이다. 만약 컴포넌트가 화면에 모두 표현된 이후 해야 하는 작업들은 여기에 하면 된다.
* 업데이트 : props나 state가 변경되면 렌더(업데이트). 아래 순서대로 호출.
  * **getDerivedStateFromProps(props, state)** : getDerivedStateFromProps() 함수는 정적 함수이다. 따라서 함수 안에서 this.props나 this.state와 같은 방법으로 프로퍼티나 state값에 접근할 수 없다. 만약 각 값에 접근해야 하는 경우 반드시 인자로 전달된 props, state를 이용해야 한다.
  * **shouldComponentUpdate(nextProps, nextState)** : shouldComponentUpdate() 함수는 프로퍼티를 변경하거나 setState() 함수를 호출하여 state값을 변경하면 '화면을 새로 출력해야 하는지' 판단하는 함수이다. 이 함수는 화면을 새로 출력할지 말지 판단하며, 데이터 변화를 비교하는 작업을 포함하므로 리액트 성능에 영향을 많이 준다. 화면 변경을 위해 검증 작업을 해야 하는 경우 이 함수를 하용하면 된다.
  * **render()**
  * **getSnapshotBeforeUpdate(prevProps, prevState)** : getSnapshotBeforeUpdate() 함수는 컴포넌트의 변경된 내용이 가상 화면에 완성된 이후 호출된느 함수이다. 이 함수는 컴포넌트가 화면에 실제로 출력되기 전에 호출되므로 화면에 출력될 엘리먼트의 크기 또는 스크롤 위치 등의 DOM정보에 접근할 때 사용한다.
  * **componentDidUpdate(prevProps, prevState, snapshot)** : componentDidUpdate() 함수는 컴포넌트가 실제 화면에 출력된 이후 호출된는 함수이다. 이 함수는 부모 컴포넌트로부터 전달된 이전 프로퍼티와 이전 state값과 함께 getSnapshotBeforeUpdate() 함수에서 반환된 값(snapshot)을 인자로 전달 받는다. 이 값들을 이용하여 스크롤 위치를 옮기거나 커서를 이동시키는 등의 DOM 정보를 변경할 때 사용한다.
  * **shouldComponentUpdate()**
  * **getSnapshotBeforeUpdate()**
  * **componentDidUpdate()**
  * **componentWillUnmount()** : componentWillUnmount() 함수는 컴포넌트가 소멸되기 직전에 호출되는 함수이다. 보통 컴포넌트에서 감시하고 있는 작업들을 해제할 때 필요한 함수이다. 예를 들어 컴포넌트에 setInterval() 함수가 사용되었다면 이 함수에서 setInterval() 함수를 clearInterval() 함수로 해체해야 한다.
* 소멸 : 컴포넌트가 DOM에서 제거될 때 호출 - componentWillUnmount()

</details>

<br>

### 자바스크립트의 확장 문법
<details>
  <summary>Click me</summary>

* 브라우저에서 실행하기 전에 코드가 번들링 되는 과정에서 바벨을 사용하여 일반 자바스크립트 형태의 코드로 변환됩니다.
* JSX는 자바스크립트의 공식적인 문법이라고 할 수는 없습니다.
* 즉, 자바스크립트에서 HTML을 작성하듯이 비슷하게 작성할 수 있도록 해 주는 것이 JSX의 가장 큰 장점이자, 이를 사용하는 이유가 됩니다.

</details>

<br>

### Context API
<details>
  <summary>Click me</summary>

전역적인 상태 관리 수단.

일일이 데이터를 props로 넘겨주지 않아도 컴포넌트 트리 전체에 데이터 제공.

React에서 컴포넌트가 데이터를 다루는 방법. cf. props, state

</details>

<br>

### 리액트 훅
<details>
  <summary>Click me</summary>

Hook을 이용하여 기존 Class 바탕의 코드를 작성할 필요 없이 상태 값과 여러 React의 기능을 사용할 수 있다. 함수형 컴포넌트에 state를 제공해 상태 관련 로직의 재 사용을 이전보다 쉽게 만들어준다. 클래스형 컴포넌트의 문제점들을 해결하기 위해 나온 것.

</details>

<br>

### state vs props
<details>
  <summary>Click me</summary>

두 객체 모두 렌더링 결과물에 영향을 주는 정보를 갖고 있는데, 한 가지 중요한 방식에서 차이가 있습니다.

**props** : 부모 컴포넌트에서 자식 컴포넌트로 값을 전달해줄 때 사용, (함수 매개변수처럼) 컴포넌트에 전달
* 프로퍼티, props(properties의 줄임말) 라고 한다. - 상위 컴포넌트가 하위 컴포넌트에 값을 전달할때 사용한다.(단방향 데이터 흐름 갖는다.) - 프로퍼티는 수정할 수 없다는 특징이 있다.(자식입장에선 읽기 전용인 데이터이다.)
* <https://goddaehee.tistory.com/300?category=395445>

**state** : 컴포넌트 내에서만 값이 이동. 리액트 컴포넌트의 변경가능한 데이터, (함수 내에 선언된 변수처럼) 컴포넌트 안에서 관리
* 일반적으로 컴포넌트의 내부에서 변경 가능한 데이터를 관리해야할 때에 사용 한다.
* 프로퍼티(props)의 특징은 컴포넌트 내부에서 값을 바꿀 수 없다는 것이었다. 하지만 값을 바꿔야 하는 경우도 분명 존재하며, 이럴때 state라는 것을 사용한다.
* 값을 저장하거나 변경할 수 있는 객체로 보통 이벤트와 함께 사용된다.
* 컴포넌트에서 동적인 값을 상태(state)라고 부르며, 동적인 데이터를 다룰 때 사용된다 볼 수 있다.
* <https://goddaehee.tistory.com/301?category=395445>

</details>

<br>

### 왜 state를 직접 바꾸지 않고 useState를 사용해야 하나?
<details>
  <summary>Click me</summary>

컴포넌트는 this.state(현재)와 setState를 비교해서 업데이트가 필요한 경우에만 render 함수를 호출하는데, state를 직접 수정하게 되면 리액트가 render 함수를 호출하지 않아 상태 변경이 일어나도 렌더링이 일어나지 않을 수 있다.

</details>

<br>

### key props를 사용하는 이유는?
<details>
  <summary>Click me</summary>

react가 어떤 항목을 변경, 추가, 삭제할지 식별하는 것을 돕는다.

</details>

<br>

### async-await와 promise의 차이
<details>
  <summary>Click me</summary>

callback, promise, async-await 다 동기적으로 만들어주는 것.

</details>

<br>

### 컴포넌트
<details>
  <summary>Click me</summary>

* <https://goddaehee.tistory.com/299>
* 재 사용이 가능한 각각의 독립된 모듈
* 리액트로 만들어진 앱을 이루는 최소한의 단위
* 기존의 웹 프레임워크는 MVC방식으로 분리하여 관리하여 각 요소의 의존성이 높아 재활용이 어렵다는 단점이 있었다. 반면 컴포넌트는 MVC의 뷰를 독립적으로 구성하여 재사용을 할 수 있고 이를 통해 새로운 컴포넌트를 쉽게 만들 수 있다. - 컴포넌트는 데이터(props)를 입력받아 View(state) 상태에 따라 DOM Node를 출력하는 함수. - 컴포넌트 이름은 항상 대문자로 시작하도록 한다. (리액트는 소문자로 시작하는 컴포넌트를 DOM 태그로 취급하기 때문이다.)
* UI를 재사용 가능한 개별적인 여러 조각으로 나누고, 각 조각을 개별적으로 나누어 코딩한다.
* “props”라고 하는 임의의 입력을 받은 후, 화면에 어떻게 표시되는지를 기술하는 React 엘리먼트를 반환한다.
* props와 state 등의 특징들은 따로 정리 하도록 한다.

</details>

<br>

### 제어 컴포넌트 / 비제어 컴포넌트
<details>
  <summary>Click me</summary>

리액트로 폼을 다루는 방법.
* 제어 컴포넌트
  * : 사용자의 입력을 받는 컴포넌트에 event 객체를 이용해 setState() 로 값을 저장하는 방식. react에 의해 값이 제어되는 폼 엘리먼트.
* 비제어 컴포넌트ex) 버튼을 눌러 submit 할 때, 실행되는 함수 내에서 ref를 통해 form의 value에 접근.
  * : ref를 통해 폼 요소에 접근. 기존의 자스와 비슷하다.

</details>

<br>

### 컴포넌트를 어떻게 구조화 시키나
<details>
  <summary>Click me</summary>

기능 또는 경로 별로 그룹화 합니다.

</details>

<br>

### pure component란?
<details>
  <summary>Click me</summary>

react의 생명주기 메서드중 하나인 shouldComponentUpdate를 어떻게 쓰는가 하는 부분

</details>

<br>

### react-query란?
<details>
  <summary>Click me</summary>

리액트 라이브러리. 서버의 값을 클라이언트에 가져오거나, 캐싱, 값 업데이트, 에러 핸들링 등 비동기 과정을 더욱 편하게 해주는 데 사용.

</details>

<br>

### 리액트의 렌더링 성능 향상을 위해 어떻게 할까?
<details>
  <summary>Click me</summary>

<https://velog.io/@shin6403/React-%EB%A0%8C%EB%8D%94%EB%A7%81-%EC%84%B1%EB%8A%A5-%EC%B5%9C%EC%A0%81%ED%99%94%ED%95%98%EB%8A%94-7%EA%B0%80%EC%A7%80-%EB%B0%A9%EB%B2%95-Hooks-%EA%B8%B0%EC%A4%80>

</details>

<br>

### useMemo / useCallback
<details>
  <summary>Click me</summary>

**useMemo** : 메모이제이션 된 값을 반환.

</details>

<br>

### 메모이제이션
<details>
  <summary>Click me</summary>

컴퓨터 프로그램이 동일한 계산을 반복해야 할 때, 이전에 계산한 값을 메모리에 저장함으로써 동일한 계산의 반복 수행을 제거 ⇒ 프로그램 속도 빠르게 하는 기술.

</details>

<br>

### 리액트에서 메모이제이션을 어떤 방식으로 하는가?
<details>
  <summary>Click me</summary>

memo, useMemo, useCallback

</details>

<br>

### 리액트와 뷰의 차이
<details>
  <summary>Click me</summary>

Vue는 반드시 데이터 객체를 생성한 후에 data를 자유롭게 업데이트할 수 있고, React는 state 객체를 만들고 업데이트를 하려면 조금 더 많은 작업이 필요하다. React는 더 좋아지도록 별도의 작업(state를 조작하기 위한 작업)을 수행한다.

</details>

<br>
