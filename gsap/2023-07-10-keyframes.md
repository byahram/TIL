# [범쌤] Part.01 GSAP Basic - Keyframes

* <https://gsap.com/docs/v3/>
* [인프런 강의](https://www.inflearn.com/course/%EC%9B%B9-%EC%95%A0%EB%8B%88%EB%A7%A4%EC%9D%B4%EC%85%98-gsap-1/dashboard)

<br>

## 키프레임 파헤치기 chapter 1

#### 👉 참고 문서
* <https://codepen.io/GreenSock/pen/kQPqJo>
* <https://greensock.com/css-workflow/>

### 👉 CSS Animation VS Javascript Animation
* <https://codepen.io/GreenSock/pen/DmgOQx>
* <https://css-tricks.com/myth-busting-css-animations-vs-javascript/>
* easeEach 를 사용하면 각 프레임 구간 마다 가속도를 재설정 할 수 있다.
  * CSS keyframes의 default ease값은 “power1.inOut” 이고 GSAP keyframes의 default ease값은 “power1.out”이다.
  * <https://codepen.io/GreenSock/pen/GRvLaQe/941b82d684b7fbf5303304d671e15ce2>
  * <https://www.figma.com/file/ajcEcCYdIHOVxB1Bj9PULZ/GSAP-keyfames?type=design&node-id=0-1&mode=design>

```javascript
const tl = gsap.timeline();

tl.to('.among',{
    keyframes:{
      "0%":{y:0},
      "25%":{y:0},
      "50%":{rotation:360,y:-100,ease:'sine.out'},
      "75%":{y:0,ease:'sine.in'},
      "100%":{x:500}
    },
  duration:2,
  stagger:0.2,
})
```

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="yLQEbVe" data-user="byahram" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/byahram/pen/yLQEbVe">
  GSAP3 - keyframes (1)</a> by Ahram-Kim (<a href="https://codepen.io/byahram">@byahram</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br>

## 키프레임 파헤치기 chapter 2

GSAP의 키프레임을 사용하면 단일 트윈을 이용하므로 여러 속성에 애니메이션을 한번에 적용 할 수 있으며, 중첩된 타임라인 없이 복잡한 애니메이션을 보다 빠르고 쉽게 정의할 수 있다.

### 👉 실습 예제 Challenges 1 (scale and rotation)

```javascript
console.log(gsap.version) // 3.9 +

const tl = gsap.timeline();
tl.to('.among',{
  keyframes:{
    '0%':{scale:1},
    '10%':{scale:0.5},
    '70%':{scale:3,rotation:360},
    '100%':{scale:1},
  },
  duration:1.5
})

GSDevTools.create();
```

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjeZNWO" data-user="byahram" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/byahram/pen/JjeZNWO">
  GSAP3 - keyframes (Challenges 1)</a> by Ahram-Kim (<a href="https://codepen.io/byahram">@byahram</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

### 👉 실습 예제 Challenges 2 (Wrap Around)

```javascript
console.log(gsap.version) // need 3.9+

const tl = gsap.timeline()
//add keyframe animation here
tl.to(".among", {
	keyframes:{
    "30%":{x:420},
    "50%":{scale:2},
    "60%":{x:0},
    "70%":{scale:1},
    "100%":{x:420},
	},
	duration: 3
})

GSDevTools.create();
```

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="oNQyWyM" data-user="byahram" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/byahram/pen/oNQyWyM">
  GSAP3 - keyframes (Challenges 2)</a> by Ahram-Kim (<a href="https://codepen.io/byahram">@byahram</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br>
