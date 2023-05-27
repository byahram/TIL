# 드림코딩 : 자바스크립트 입문 기본 강의

---
<p align="center">
<img width="50%" src="../assets/img/js.png">
</p>

---

<br>

## 00. 자바스크립트 함수 기본편
```javascript
// 함수 선언
function doSomething() {
    console.log('hello');
}

function doSomething(add) {
    console.log(add);
    const result = add(2, 3);
    console.log(result);                    // 5
}

function add(a, b) {
    const sum = a + b;
    return sum;
}
```

```javascript
// 함수 호출
doSomething();                  // hello
doSomething(add);                   
/**add(a, b) {
 *      const sum = a + b;
 *      return sum;
 * }
 */
doSomething(add());                 // NaN

const result = add(1, 2);
console.log(result);                    // 3
```

<br>

## 01. 변수 | primitive 타입과 object의 차이점
### primitive
```javascript
// primitive - number, string, boolean, null, undefined
let number = 2;
let num = '2';
console.log(number);
console.log(number2);

number2 = 3;
console.log(number);
console.log(number2);
```
### object
```javascript
//object
let obj = {            // 새 할당 X
    name: 'ellie',
    age: 5,
};
console.log(obj.name);                // ellie

let obj2 = obj;
console.log(obj2.name);                // ellie

obj.name = 'james';
console.log('-----');
console.log(obj.name);                // james
console.log(obj2.name);                // james
```

<br>

## 02. 함수 | 함수 정의, 호출, 그리고 콜백함수
```javascript
const num = 1;
const num2 = 2;
const result = num + num2;
console.log(result);                // 3

const num3 = 1;
const num4 = 2;
const result2 = num3 + num4;        // 지저분하다 -> 함수생

// 함수 
function add(a, b) {
    return a + b;
}

const sum = add(3, 4);
console.log(sum);            // 7
```

```javascript
function add(num1, num2) {
    return num1 + num2;
}

const doSomething = add;
const result = doSomething(2, 3);
console.log(result);        // 5
const result2 = add(2, 3);
console.log(result2);        // 5
```

```javascript
function add(num1, num2) {
    return num1 + num2;
}

function surprise(operator) {
    const result = operator(2, 3);        // add(2, 3); 같음
    console.log(result);
}
surprise(add);            // 5
```

```javascript
function divide(num1, num2) {
    return num1 / num2;
}
function surprise(operator) {
    const result = operator(2, 3);        // divide(2, 3); 같음
    console.log(result);
}
surprise(divide);
```

<br>

## 03. 연산자 | boolean의 모든것 && 연산자
```javascript
// false : 0, -0, '', undefined, NaN, null
// true : -1, 'hello'


if(true) {
    console.log('true!');            // true!
} else {
    console.log('false!');
}


let num;    // undefined
if(num) {
    console.log('true!');            
} else {
    console.log('false!');        // false!
}
```

<br>

## 04. 클래스 | 클래스 예제와 콜백함수 최종 정리
```javascript
class Counter {
    constructor() {
        this.counter = 0;
    }
    
    increase() {
        this.counter++;
        console.log(this.counter);
        
        if(this.counter % 5 === 0) {
            console.log('yo');
        }
    }
}

const coolCounter = new Counter();
coolCounter.increase();        // 1
coolCounter.increase();        // 2
coolCounter.increase();        // 3
coolCounter.increase();        // 4
coolCounter.increase();        // 5 yo
```

```javascript
class Counter {
    constructor() {
        this.counter = 0;
    }
    
    increase(runIf5Times) {
        this.counter++;
        console.log(this.counter);
        
        if(this.counter % 5 === 0) {
            runIf5Times(this.counter);
        }
    }
}

function coolCounter = new Counter();

function printSomething(num) {
    console.log(`yo! ${num}`);
}
function alertNum(num) {
    alert(`Wow! ${num}`);
}

coolCounter.increase(printSomething);        // 1
coolCounter.increase(printSomething);        // 2
coolCounter.increase(printSomething);        // 3
coolCounter.increase(printSomething);        // 4
coolCounter.increase(printSomething);        // yo! 5

coolCounter.increase(printSomething);        // 6
coolCounter.increase(printSomething);        // 7
coolCounter.increase(printSomething);        // 8
coolCounter.increase(printSomething);        // 9
coolCounter.increase(alertNum);        // alert 창 popup
```

```javascript
class Counter {
    constructor(runEveryFiveTimes) {
        this.counter = 0;
        this.callback = runEveryFiveTimes;
    }
    
    increase(runIf5Times) {
        this.counter++;
        console.log(this.counter);
        
        if(this.counter % 5 === 0) {
            this.callback(this.counter);
        }
    }
}

const coolCounter = new Counter(printSomething);

function printSomething(num) {
    console.log(`yo! ${num}`);
}
function alertNum(num) {
    alert(`Wow! ${num}`);
}

const printCounter = new Counter(printSomething);
const alertCounter = new Counter(alertNum);
```

<br>

## 05. 자바스크립트 최신 문법(ES6, ES11)
es6 - <https://github.com/byahram/2022-webs/blob/main/study/javascript/BasicJavaScriptByDreamCoding/es6-11/es6.js>

es11 - <https://github.com/byahram/2022-webs/blob/main/study/javascript/BasicJavaScriptByDreamCoding/es6-11/es11.js>


<br>

## 06. 자바스크립트 프로처럼 쓰는 팁 예제들
<https://github.com/byahram/2022-webs/tree/main/study/javascript/BasicJavaScriptByDreamCoding/pro-tips>

<br>
