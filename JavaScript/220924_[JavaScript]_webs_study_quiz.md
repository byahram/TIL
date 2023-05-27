# 웹스스터디 220924 Quiz

---
<p align="center">
<img width="50%" src="../assets/img/js.png">
</p>

---

<br>

### 01.
```javascript
/********** 1. **********/
function func() {
  for(i=1; i<=7; i++) {
    for(j=1; j<=i; j++) {
      document.write(j);
    }
    document.write("<br>");
  }
}
func();

/* <answer> 
1
12
123
1234
12345
123456
1234567 */
```

### 02.
```javascript
/********** 2. **********/
function func() {
  let i = 10, hap = 0;
  while(i > 1) {
    i--;
    if(i % 3 == 1) {
      hap += i;
    }
  }
  document.write(hap);
}
func();

/* <answer> 12 */
```

### 03.
```javascript
/********** 3. **********/
function func() {
  let a = [];
  
  for(i = 1; i <= 15; i+=4) {
    a += [i];
  }
  document.write(a);
}
func();

/* <answer> 15913 */
```

### 04.
```javascript
/********** 4. **********/
function func() {
  let a = [1, 2, 3, 4, 5, 6, 7, 8, 9], cnt = 0;
  
  for(i = 0; i < a.length; i++) {
    if(a[i] % 2 == 0) {
      cnt = cnt + 1;
    }
  }
  document.write(cnt);
}
func();

/* <answer> 4 */
```

### 05.
```javascript
/********** 5. **********/
function func(data, exp) {
  let result = 1;
  for(i = 0; i < exp; i++) {
    result = result * data;
  }
  document.write(result);
}
func(3, 3);

/* <answer> 27 */
```

### 06.
```javascript
/********** 6. **********/
function func() {
  let a = [2, 3, 2, 4, 5, 6, 7, 2, 3, 3, 2];
  let value = 0;
  for(i = 0; i < a.length; i++) {
    if(a[i] == 7) {
      value++;
    }
  }
  document.write(value);
}
func();

/* <answer> 1 */
```

### 07.
```javascript
/********** 7. **********/
function func() {
  let i, j = 0;
  for(i = 0; i < 5; i++) {
    j += i;
  }
  document.write(i);
  document.write(j);
}
func();

/* <answer> 510 */
```

### 08.
```javascript
/********** 8. **********/
function func() {
  let a = 12, b = 8, c = 2, d = 3;
  a /= b - c * d;
  
  document.write(a);
  document.write(a*b);
}
func();

/* <answer> 648 */
```

### 09.
```javascript
/********** 9. **********/
function func() {
  let a = 0, sum = 0;
  while(a < 10) {
    a++;
    if(a % 2 == 1) continue;
    sum += a;
  }
  document.write(sum);
}
func();

/* <answer> 30 */
```

### 10.
```javascript
/********** 10. **********/
function func() {
  let i = 0, sum = 0;
  while(0) {
  	i++;
  	if(i > 10) break;
  	if(i % 5 == 0) continue;
  	sum += i;
  }
  document.write(sum);
}
func();

/* <answer> 0 */
```

### 11.
```javascript
/********** 11. **********/
function solution(data) {
  var answer = data;
  answer = answer.toLowerCase();
  return answer;
}
document.write(solution("Javascript"));

/* <answer> javascript */
```

### 12.
```javascript
/********** 12. **********/
function solution(a, b, c) {
  let answer;
  
  if(a < b) answer = a;
  else answer = b;
  
  if(c < answer) answer = c;
  
  return answer;
}
document.write(solution(2, 5, 1));

/* <answer> 1 */
```

### 13.
```javascript
/********** 13. **********/
function func() {
  function funA() {
    document.write("함수A가 실행되었습니다.");
  }
  funA();
  function funcB() {
    document.write("함수B가 실행되었습니다.");
  }
}
func();

/* <answer> 함수A가 실행되었습니다. */
```

### 14.
```javascript
/********** 14. **********/
function func(str="함수가 실행되었습니다.") {
  document.write(str);
}
func();

/* <answer> 함수가 실행되었습니다. */
```

### 15.
```javascript
/********** 15. **********/
const objA = { 
  a: 100,
  b: 200
}
const objB = {
  c: "javascript",
  d: "jquery"
}
const spread = {...objA, ...objB}

document.write(spread.c);

/* <answer> javascript */
```

### 16.
```javascript
/********** 16. **********/
let num = 0;
while(num < 20000) {
  num++;
  document.write(num);
  if(num == 10) {
    break;
  }
}

/* <answer> 12345678910 */
```

### 17.
```javascript
/********** 17. **********/
for(let i = 0; i < 5; i++) {
  for(let j = 0; j < 5; j++) {
    document.write("*");
  }
  document.write("<br>");
}

/* <answer> 
*****
*****
*****
*****
***** */
```

### 18.
```javascript
/********** 18. **********/
function solution(a, b) {
  let num = a > b;
  return num;
}
document.write(solution(5, 9));

/* <answer> false */
```

### 19.
```javascript
/********** 19. **********/
function solution(a, b) {
  return (a + b) * ((a > b ? a - b : b - a) + 1) / 2;
}
document.write(solution(5, 9));

/* <answer> 35 */
```

### 20.
```javascript
/********** 20. **********/
function solution(text) {
  return text.split("").join("/").replace("s", "site");
}
document.write(solution("webs"));

/* <answer> w/e/b/site */
```

<br>
