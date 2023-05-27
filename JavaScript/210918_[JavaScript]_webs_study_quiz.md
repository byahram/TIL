# 웹스스터디 210918 Quiz

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
    let i = 5, j = 4, k = 1, l, m;
    l = i > 5 || k != 0;
    m = j <= 4 && k < 1;
    document.write(l);
    document.write(m);
}
func();

/* <answer> truefalse */
```

### 02.
```javascript
/********** 2. **********/

function func() {
  let i = 10, j = 10, k = 30;
  i /= j;
  j -= i;
  k %= j;
  document.write(i);
  document.write(j);
  document.write(k);
}
func();

/* <answer> 193 */
```

### 03.
```javascript
/********** 3. 오답 **********/

function func() {
  for(i = 1; i <= 7; i++) {
    for(j = 1; j <= i; j++) {
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

### 04.
```javascript
/********** 4. **********/

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

### 05.
```javascript
/********** 5. **********/

function func() {
  let a = [];
  for(i = 1; i <= 5; i++) {
    a +=[i];
  }
  document.write(a);
}
func();

/* <answer> 12345*/
```

### 06.
```javascript
/********** 6. **********/

function func() {
  let a = [1, 2, 3, 4, 5, 6, 7, 8, 9], cnt = 0;
  
  for(i = 0; i < a.length; i++) {
    if(a[i] % 2 != 0) {
      cnt = cnt + 1;
    }
  }
  document.write(cnt);
}
func();

/* <answer> 5 */
```

### 07.
```javascript
/********** 7. **********/

function func(data, exp) {
  let result = 1;
  for(i = 0; i < exp; i++) {
    result = result * data;
  }
  document.write(result);
}
func(2, 5);

/* <answer> 32 */
```

### 08.
```javascript
/********** 8. **********/

function func(data, exp) {
  let a = [2, 3, 2, 4, 5, 6, 7, 2, 3, 3, 2];
  let value = 0;
  for(i = 0; i < a.length; i++) {
    if(a[i] == 2) {
      value++;
    }
  }
  document.write(value);
}
func();

/* <answer> 4 */
```

### 09.
```javascript
/********** 9. 오답 **********/

function func() {
  let i, j = 0;
  for(i = 0; i < 8; i++) {
    i += i;
  }
  document.write(i, "<br>");
  document.write(j, "<br>");
}
func();

/* <answer> 
    15
    0    */
```

### 10.
```javascript
/********** 10. 오답 **********/

function func() {
  let a = 12, b = 8, c = 2, d = 3;
  a /= b - c * d;
  
  document.write(a);
  document.write(b);
}
func();

/* <answer> 68 */
```

### 11.
```javascript
/********** 11. **********/

function func13() {
  let a, b, c, result;
  a = 10;
  b = 20;
  c = 30;
  result = a < b ? b : c;
  
  document.write(result);
}
func13();

/* <answer> 20 */
```

### 12.
```javascript
/********** 12. 오답 **********/

function func() {
  let a = 0, sum = 0;
  while(a < 10) {
    a++;
    if(a % 2 == 1) continue;
    document.write(a);
    sum += a;
  }
  document.write(sum);
}
func();

/* <answer> 24681030 */
```

### 13.
```javascript
/********** 13. 오답 **********/

function func() {
  let i = 0, sum = 0;
  while(1) {
    i++;
    if(i > 10) break;
    if(i % 5 == 0) continues;
    sum += i;
    document.write(i);
  }
  document.wirte(sum);
}
func();

/* <answer> 1234 */
```

### 14.
```javascript
/********** 14. **********/

function testAvg(arrData) {
  let sum = 0;
  for(let i = 0; i < arrSubject.length; i++) {
    sum += Number(arrSubject[i]);
  }
  let avg = sum / arrData.length;
  return avg;
}
let arrSubject = ["100", "90", "80", "70"];
let result = testAvg(arrSubject);

document.write(result);

func();

/* <answer> 85 */
```

### 15.
```javascript
/********** 15. **********/

function func() {
  let color = ["#311b92", "#1a237e", "#1b5e20", "#827717"];
  
  for(let i = 0; i < color.length; i++) {
    document.write(color[i]);
  }
}
func();

/* <answer> #311b92#1a237e#1b5e20#827717 */
```

### 16.
```javascript
/********** 16. 오답 **********/

function func(a, b, c) {
  let answer;
  if(a < b) answer = a;
  else answer = b;
  if(c < answer) answer = c;
  document.write(answer);
}
func(2, 5, 1);

/* <answer> 1 */
```

### 17.
```javascript
/********** 17. 오답 **********/

function func(n) {
  let answer;
  answer = Math.ceil(n/12);
  return answer;
}
document.write(func(178));

func();

/* <answer> 15 */
```

### 18.
```javascript
/********** 18. **********/

function func(s) {
  let answer = "";
  for(let x of s) {
    if(x == 'w') answer += '#';
    else answer += x;
  }
  return answer;
}

let str = "webstoryboy";
document.write(func(str));

/* <answer> #ebstoryboy */
```

### 19.
```javascript
/********** 19. **********/

function func(s, t) {
  let answer = 0;
  for(let x of s) {
    if(x === t) answer++;
  }
  return answer;
}
let str = "webstoryboy";
document.write(func(str, 'b'));

/* <answer> 2 */
```

### 20.
```javascript
/********** 20. **********/

function func(s) {
  let answer = "";
  for(let x of s) {
    if(x === x.toUpperCase()) {
      answer += x.toLowerCase();
    } else {
      answer += x.toUpperCase();
    }
  }
  return answer;
}
document.write(func("webStorBOY"));

/* <answer> WEBsTORboy */
```

<br>
