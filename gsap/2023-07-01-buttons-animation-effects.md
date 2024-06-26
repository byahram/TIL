# [범쌤] Part.01 GSAP Basic - Buttons Animation Effects

* <https://gsap.com/docs/v3/>
* [인프런 강의](https://www.inflearn.com/course/%EC%9B%B9-%EC%95%A0%EB%8B%88%EB%A7%A4%EC%9D%B4%EC%85%98-gsap-1/dashboard)

<br>

## 단일 메뉴 효과

#### 👉 참고 문서
* <https://developer.mozilla.org/ko/docs/Web/API/Document/querySelector>
* <https://developer.mozilla.org/ko/docs/Web/API/MouseEvent>

GSAP을 사용하여 paused된 애니메이션 객체(Tween or Timeline)를 생성합니다. 

Javascript의 Mouse Event를 사용해 (mouseenter, mouseleave) 애니메이션 객체에 `play()` 또는 `reverse()`를 적용합니다.

단일 대상의 색상이나 크기를 변경하는것과 같이 간단한 애니메이션을 적용하려면 CSS만 있어도 충분히 원하는 결과를 얻을 수 있습니다.

그러나 정확한 타이밍이 필요한 여러 객체들을 컨트롤 하거나 재생,되돌아가기,속도,가속도 설정과 같은 작업을 수행하기 위해선 GSAP의 애니메이션 코드가 훨씬 더 많은 유연성을 제공합니다.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="LYXjqVN" data-user="byahram" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/byahram/pen/LYXjqVN">
  GSAP3 - Menu Hover Effects (Single - Start)</a> by Ahram-Kim (<a href="https://codepen.io/byahram">@byahram</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br>

## 다중 메뉴 효과

#### 👉 참고 문서
* <https://developer.mozilla.org/ko/docs/Web/API/NodeList>
* <https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach>

forEach() 루프를 만들어 반복문 안에 있는 동안 각각의 타임라인에 play()와 reverse() 메서드를 마우스 이벤트를 통해 바인딩 한다.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="PoxKVzE" data-user="byahram" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/byahram/pen/PoxKVzE">
  GSAP3 - Menu Hover Effects (Multiple - Start)</a> by Ahram-Kim (<a href="https://codepen.io/byahram">@byahram</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br>

## Hover Pulse Animation

부드럽게 멈추거나 다시 반복되는 애니메이션의 대한 이슈는 GreenSock 포럼과 Stackoverflow에 자주 등장하는 주제이다.

이러한 문제를 해결하기 위해 아래의 다양한 방법들이 있다. 이러한 방법들을 이용하면 보다 쉽게 애니메이션 이슈 처리가 가능하다. (추후에 Advanced 과정)

* Callback with custom logic
* tweening progress() or totalProgress()
* overwrite modes

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="YzRxBNV" data-user="byahram" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/byahram/pen/YzRxBNV">
  GSAP3 - Hover Pulse Animation (Started)</a> by Ahram-Kim (<a href="https://codepen.io/byahram">@byahram</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br>
