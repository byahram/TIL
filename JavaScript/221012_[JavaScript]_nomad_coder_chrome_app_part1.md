# Nomad Coder : Vanilla JS로 크롬 앱 만들기 #1

---
<p align="center">
<img width="50%" src="../assets/img/js.png">
</p>

---

<br>

## A clone of the productivity chrome app 'momentom' on Vanilla JS

<https://nomadcoders.co/javascript-for-beginners>

<https://github.com/byahram/2022-webs/tree/main/study/javascript/NomadCoderVanilaJS>

### 1-1 Why JS?
자바스크립은 바꿀 수도 없고 업데이트하지도 못하므 우리가 원하는 것으로 교체할 수 없다. 그러나 JavaScript은 웹에서 쓸 수 있는 하나뿐인 언어이기 때문에 웹이 빠르게 발전할 때 JavaScript도 같이 빨리 발전한다.

왜 프론트엔드에서 자바스크립을 사용할까? 만들고 다른 언어로 변경하지 않기 문이다. 전 세계에 있는 컴퓨터들이 자바스크립을 쓰기 시작했다. 모든 컴퓨터에는 브라우저가 있고 브라우저는 JavaScript 돌아가 즉 모든 컴퓨터는 JavaScript 이해하는 이유이다.

### 1-2 Super Powers of JS
<https://threejs.org/>

### 1-3 ES5, ES6, ES... WTF!?!?!

### 1-4 VanillaJS
<http://vanilla-js.com/>

### 1-5 Hello World with JavaScript

### 1-6 Your First JS Variable(변수!)
* 변수를 생성하고
* 생성한 변수를 Initialize하고
* 그 후에 사용
```javascript
let a = 221;        // a란 변수를 생성하고 221으로 Initialize
let b = a - 5;        // a 변수 사용
```

### 1-7 let, const, var
* let
  * 중복 선언이 불가능하다. - 이미 존재하는 변수와 같은 이름의 변수를 또 선언하면 에러가 난다.
  * 값의 재할당이 가능한 변수
  * 변수 선언시 초기값을 주지 않아도 된다.
  * 블럭 레벨 스코프 - 함수 내부는 물론, if문이나 for문 등의 코드 블럭 {...}에서 선언된 변수도 지역 변수로 취급한다.
* const
  * 중복 선언이 불가능하다. - 이미 존재하는 변수와 같은 이름의 변수를 또 선언하면 에러가 난다.
  * 값의 재할당이 불가능한 상수
  * 반드시 초기값을 할당해야 한다.
  * 블럭 레벨 스코프 - 함수 내부는 물론, if문이나 for문 등의 코드 블럭 {...}에서 선언된 변수도 지역 변수로 취급한다.
* var
  * 중복 선언이 가능하다. - 이미 선언되어있는 이름과 같은 이름으로 변수를 또 선언해도 에러가 나지 않는다.
  * 값의 재할당이 가능한 변수
  * 변수 선언시 초기 값을 주지 않아도 된다.
  * 함수 레벨 스코프 - 함수 내부에 선언된 변수만 지역변수로 한정하며, 나머지는 모두 전역변수로 간주한다.
* 함수 레벨 스코프 var의 경우 버그 발생과 메모리 누수의 위험 등이 있기 때문에 var말고 let, const를 사용하는 것이 좋다.

### 1-8 Data Types on JS
* //, /**/ - comments
* 변수는 const로 필요할때만 let으로
* " " - string
* true = 1 / false = 0

### 1-9 Organizing Data with Arrays
```javascript
const monday = "Mon";
const tue = "Tue";
const wed = "Wed";
const thu = "Thu";
const fri = "Fri";

const daysOfWeek = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"];

console.log(daysOfWeek);        // ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'];
console.log(daysOfWeek[2]);        // Wed
```

### 1-10 Organizing Data with Objects
```javascript
const nicoInfo = ["Nicolas", "55", true, "Seoul"];        // Array
console.log(nicoInfo);

// Objects
const nicoInfo = {
    name: "Nico",
    age: 33,
    gender: "Male",
    isHandsome: true,
    favMovies: ["Along the gods", "LOTR", "Oldboy"];
    favFood: [
        {    
            name: "Kimchi", fatty: false
        }, 
        {
            name: "Cheese burger", 
            fatty: true
        }
    ]
}
console.log(nicoInfo.gender);        // Male

nicoInfo.gender = "Female"
console.log(nicoInfo.gender);        // Female


console.log(nicoInfo);
/* { name: 'Nico',
  age: 33,
  gender: 'Male',
  isHandsome: true,
  favMovies: ['Along the gods', 'LOTR', 'Oldboy'];
  favFood: [{ name: 'Kimchi', fatty: false }, 
            { name: 'Cheese burger', fatty: true } ]
} */

console.log(nicoInfo.favFood[0].fatty);        // false
```

<br>
