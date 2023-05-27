# 웹스스터디 221001 Quiz

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
  let i = 10, hap = 0;
  while(i > 1) {
    if(i % 3 == 1) {
      hap += i;
    }
    i--;
  }
  document.write(hap);
}
func();

/* <answer> 21 */
```

### 02.
```javascript
/********** 2. **********/
function func() {
  let a = [];
  for(i = 1; i <= 5; i++) {
    a += [i];
  }
  document.write(a[2]);
}
func();

/* <answer> 3 */
```

### 03.
```javascript
/********** 3. **********/
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

### 04.
```javascript
/********** 4. **********/
function func(data, exp) {
  let result = 1;
  for(i = 1; i < exp; i++) {
    result = result * i;
  }
  document.write(result + data);
}
func(1, 5);

/* <answer> 25 */
```

### 05.
```javascript
/********** 5. **********/
function func() {
  let a = [2, 3, 2, 4, 5, 6, 7, 2, 3, 3, 2];
  let value = 0;
  for(i = 0; i < a.length; i++) {
    if(a[i] != 2) {
      value++;
    }
  }
  document.write(value);
}
func();

/* <answer> 7 */
```

### 06.
```javascript
/********** 6. 오답 **********/
function func() {
  let i, j = 0;
  for(i = 0; i <= 8; i++) {
    j += i;
  }
  document.write(j + i);
}
func();

/* <answer> 45 */
```

### 07.
```javascript
/********** 7. **********/
function func() {
  let a = 12, b = 8, c = 2, d = 3;
  a /= b - c * d;
  document.write(a);
}
func();

/* <answer> 6 */
```

### 08.
```javascript
/********** 8. **********/
function func() {
  let a, b, c, result;
  a = 10;
  b = 20;
  c = 30;
  result = a < b ? b/a : c;
  document.write(result);
}
func();

/* <answer> 2 */
```

### 09.
```javascript
/********** 9. 오답 **********/
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
/********** 10. 오답 **********/
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
function test(arrData) {
  let result = 0;
  for(let i = 0; i < arrSubject.length; i++) {
    result += Number(arrSubject[i]);
  }
  let num = result;
  return num;
}
let arrSubject = ["100", "90", "80", "70"];
let result = test(arrSubject);
  
document.write(result);

/* <answer> 340 */
```

### 12.
```javascript
/********** 12. **********/
function func(a, b, c) {
  let answer;
  if(a < b) answer = a;
  else answer = b;
  
  if(c < answer) answer = c;
  document.write(answer);
}
func(2, 5, 10);

/* <answer> 2 */
```

### 13.
```javascript
/********** 13. **********/
function func(n) {
  let answer;
  answer = Math.floor(n / 12);
  return answer;
}
document.write(func(178));

/* <answer> 14 */
```

### 14.
```javascript
/********** 14. **********/
function func(s = "webstoryboy") {
  let answer = "";
  for(let x of s) {
    if(x != "w") answer += '#';
    else answer += x;
  }
  return answer;
}
let str = "webstoryboy";
document.write(func(str));

/* <answer> w########## */
```

### 15.
```javascript
/********** 15. 오답 **********/
function func(s, t) {
  let answer = 0;
  for(let x of s) {
    if(x !== t) answer++;
  }
  return answer;
}
let str = "wbestoryboy";
document.write(func(str, 't'));

/* <answer> 10 */
```

### 16.
```javascript
/********** 16. **********/
function func(s) {
  let answer = "";
  for(let x of s) {
    if( x === x.toUpperCase()) {
      answer += x.toLowerCase();
    } else {
      answer += x.toUpperCase();
    }
  }
  return answer;
}
document.write(func("webStorBOY10"));

/* <answer> WEBsTORboy10 */
```

### 17.
```javascript
/********** 17. **********/
function solution(n) {
  var answer = [];
  answer = n.toString().split("").reverse().map(val => parseInt(val));
  return answer;
}
document.write(solution(12345));

/* <answer> 5,4,3,2,1 */
```

### 18.
```javascript
/********** 18. 오답 **********/
function solution(arr, divisor) {
  var answer = [];
  const div = arr.filter(el => el % divisor == 0);
  answer = div.length > 0 ? div.sort( (a,b) => a - b) : [-1];
  
  return answer;
}
document.write(solution([1, 2, 3, 4, 5], 2));

/* <answer> 2, 4 */
```

### 19.
```javascript
/********** 19. **********/
function solution(numbers) {
  let answer = 0;
  for(let i = 0; i < 10; i++) {
    if(!numbers.includes(i)) {
      answer += i;
    }
  }
  return answer;
}
document.write(solution([1, 2, 3, 4, 6, 7, 8, 0]));

/* <answer> 14 */
```

### 20.
```javascript
/********** 20. 오답 **********/
function solution(n) {
  for(let i = 1; i < n; i++) {
    if(n % i === 1) return i;
  }
}
document.write(solution(10));

/* <answer> 3 */
```

<br>
