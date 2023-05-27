# Nomad Coder : Vanilla JS로 크롬 앱 만들기 #2

---
<p align="center">
<img width="50%" src="../assets/img/js.png">
</p>

---

<br>

## A clone of the productivity chrome app 'momentom' on Vanilla JS

<https://nomadcoders.co/javascript-for-beginners>

<https://github.com/byahram/2022-webs/tree/main/study/javascript/NomadCoderVanilaJS>

### 2-1 Your First JS Function
```javascript
function sayHello() {
    console.log("Hello!");
}
sayHello();        // Hello!


// with Arguments, Parametes
function sayHello(name) {
    console.log("Hello!", name);
}
sayHello("Nicolas");        // Hello! Nicolas


// with Arguments, Parametes
function sayHello(name, age) {
    console.log("Hello!", name, " you have ", age, " years of age." );
}
sayHello("Nicolas", 15);        // Hello! Nicolas you have 15 years of age.
```

### 2-1-1 More Function Fun
* ""
* ''
* `` (backtick)

```javascript
function sayHello(name, age) {
    console.log(`Hello ${name} you are ${age} years old`);
}
sayHello(); //    Hello Nicolas you are 15 years old


function sayHello(name, age) {
    return `Hello ${name} you are ${age} years old`;
}
const greetNicolase = sayHello("Nicolas", 14);
console.log(greetNicolas);        // Hello Nicolas you are 14 years old


const calculator = {
    plus: function(a, b) {
        return a + b;
    }
}
const plus = calculator.plus(5, 5);
console.log(plus);
```

### 2-2 JS DOM Functions
* DOM (Document Object Module) : HTML을 DOM객체로 바꿀 수 있다.
```javascript
<h1 id="title">This works!</h1>        // HTML
```

```javascript
const title = document.getElementById("title");
console.log(title);            // This works!    

title.innerHTML = "Hi! From JS";  
<h1 id="title">Hi! From JS</h1>
```

### 2-3 Modifying the DOM with JS
* JS로 document의 객체 등을 수정할 수 있다.
* querySelector은 노드의 첫번째 자식을 반환한다.
```javascript
<h1 id="title">This works!</h1>        // HTML
```

```javascript
const title = document.getElementById("title");

title.innerHTML = "Hi! From JS";
title.style.color = "red";
document.title = "I own you";

console.dir(document);

const title2 = document.querySelector("#title");
// id -> #
```

### 2-4 Events and Event Handlers
* Event: 웹사이트에서 발생하는 이벤트 (ex. click, resize, submit, input, change, before, printing...)
```javascript
function handleResize() {
    console.log("I have been resized");
}
window.addEventListener("resize", handleResize);        // call 'handleResize' function


function handleResize(event) {
    console.log(event);
}
window.addEventListener("resize", handleResize);


function handleClick() {
    title.style.color = "red";
}
const title = document.querySelector("#title");
title.addEventListener("click", handleClick);
```

### 2-5 조건문 : If, else, and, or
* && : two or more conditions should be true
  * true && true = true;
  * false && true = false;
  * true && false = false;
  * false && false = false;
* || : at least one condition should be true
  * true || true = true;
  * false || true = true;
  * true || false = true;
  * false || false = false;
```javascript
if(condition) {
    block;        // if condition is true
} else {
    block;        // if condition is false
}
```

```javascript
const age = prompt("How old are you");        // prompt는 더이상 사용하지 않는다.

if(age > 18) {
    console.log('you can drink');
} else {
    console.log("you cant");
}


if(age >= 18 && age <= 21) {
    console.log('you can drink but you should not');
} else if (age > 21) { 
    console.log("go ahead");
} else {
    console.log('TOO YOUNG');
}
```

### 2-6 DOM If else Function Practice
```javascript
const title = document.querySelector("#title");

const BASE_COLOR = "#34495e";
const OTHER_COLOR = "#7f8c8d";

function handleClick() {
    console.log(title.style.color);
    const currentColor = title.style.color;
    if(currentColor == BASE_COLOR) {
        title.style.color = OTHER_COLOR;
    } else {
        title.style.color = BASE_COLOR;
    }
}

function init() {
    title.style.color = BASE_COLOR;
    title.addEventListener("click", handleClick);
}

init();
```

<https://developer.mozilla.org/ko/docs/Web/Events>

```javascript
function handleOffLine() {
    console.log("bye bye");
}

function handleOnline() {
    console.log("Welcome back");
}

window.addEventListener("offline", handleOffLine);        // wift off
window.addEventListener("offline", handleOnline);        // wift on
```

### 2-7 DOM If else Function Practice part 2
* className gets and sets the value of the class attribute of the specified element
```javascript
const title = document.querySelector("#title");
const CLICKED_CLASS = "clicked";

function handleClick() {
    const currentClass = title.className;
    
    if(currentClass !== CLICKED_CLASS) {
        title.className = CLICKED_CLASS;
    } else {
        title.className = "";
    }
}

function init() {
    title.addEventListener("click", handleClick);
}
init();
```

```javascript
CONST hasClass = title.classList.contains(CLICKED_CLASS);
if(!hasClass) {
    title.classList.add(CLICKED_CLASS);
} else {
    title.classList.remove(CLICKED_CLASS);
}

// 위와 같은 코드와 같은 역할을 해주는 toggle
title.classList.toggle(CLICKED_CLASS);
```

<br>
