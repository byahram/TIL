# 웹스스터디 210925 Quiz

---
<p align="center">
<img width="50%" src="../assets/img/js.png">
</p>

---

<br>

### 01.
```javascript
/********** 1. **********/
const arr = [100, 200, 300, 400, 500];

let max;
for(let i = 0; i < arr.length; i++) {
  if(arr[i] > arr[0]) {
    max = arr[i];
  }
}

document.write(max);

/* <answer> 500 */
```

### 02.
```javascript
/********** 2. **********/
function solution(arr) {
  let answer = [];
  
  for(let i = 0; i < arr.length; i++) {
    if(arr[i] > 5) {
      answer.push(arr[i]);
    }
  }
  return answer;
}

let arr = [7, 3, 9, 5, 6, 12];
document.write(solution(arr));

/* <answer> 7,9,6,12 */
```

### 03.
```javascript
/********** 3. **********/
let arr = [130, 135, 148, 140, 145, 150, 150, 153];

function solution(arr) {
  let answer = 1, max = arr[0];
  for(let i = 1; i < arr.length; i++) {
    if(arr[i] > max) {
      answer++;
      max = arr[i];
    }
  }
  document.write(answer + " / ");
  document.write(max);
}
solution(arr);

/* <answer> 5 / 153 */
```

### 04.
```javascript
/********** 4. **********/
function solution(s) {
  let answer = "";
  
  for(let i = 0; i < s.length; i++) {
    if(s.indexOf(s[i]) === 3) {
      answer = s[i];
    }
  }
  document.write(answer);
}
solution("webstoryboy");

/* <answer> s */
```

### 05.
```javascript
/********** 5. 오답 **********/
let str = ["good", "time", "good", "time", "student"];

function solution(s) {
  let answer;
  
  answer = s.filter(function(v, i) {
    document.write(i);
  });
}

solution(str);

/* <answer> 01234 */
```

### 06.
```javascript
/********** 6. 오답 **********/
function solution(s) {
  let answer;
  let mid = Math.floor(s.length/2);
  
  if(s.length % 2 === 1) {
    answer = s.substring(mid, mid+1);
  } else {
    answer = s.substring(mid-1, mid+1);
  }
  return answer;
}
document.write(solution("webstoryboy"));

/* <answer> o */
```

### 07.
```javascript
/********** 7. **********/
let str = ["teacher", "time", "student", "beautiful", "good"];

function solution(s) {
  let answer = "";
  let max = 0;
  
  for(let x of s) {
    if(x.length > max) {
      max = x.length;
      answer = x;
    }
  }
  return answer;
}
document.write(solution(str));

/* <answer> beautiful */
```

### 08.
```javascript
/********** 8. **********/
function solution(s, t) {
  let answer = 10;
  
  for(let x of s) {
    if(x === t) answer--;
  }
  return answer;
}
let str = "COMPUTERPROGRAMMING";
document.write(solution(str, 'R'));

/* <answer> 7 */
```

### 09.
```javascript
/********** 9. 오답 **********/
let arr = [20, 7, 23];

function solution(arr) {
  let answer = arr;
  let sum = answer.reduce((a, b) => a+b, 0);
  return sum;
}
document.write(solution(arr));

/* <answer> 50 */
```

### 10.
```javascript
/********** 10. **********/
arr = [25, 23, 13, 47, 53, 17, 33];

function solution(day, arr) {
  let answer = 0;
  
  for(let x of arr) {
    if(x % 10 == day) answer++;
  }
  return answer;
}
document.write(solution(3, arr));

/* <answer> 4 */
```

### 11.
```javascript
/********** 11. **********/
arr = [12, 77, 38, 41, 53, 92, 85];

function solution(arr) {
  let answer = [];
  let sum = 0, min = 10000;
  
  for(let x of arr) {
    if(x % 2 === 1) {
      sum += x;
      if(x < min) min = x;
    }
  }
  answer.push(sum);
  answer.push(min);
  return answer;
}
document.write(solution(arr));

/* <answer> 256,41 */
```

### 12.
```javascript
/********** 12. **********/
let arr = [5, 7, 1, 3, 2, 9, 11];

function solution(arr) {
  let answer, min = 100;
  
  for(let i = 0; i < arr.length; i++) {
    if(arr[i] < min) {
      min = arr[i];
    }
  }
  answer = min;
  return answer;
}
document.write(solution(arr));

/* <answer> 1 */
```

### 13.
```javascript
/********** 13. **********/
function solution(n) {
  let answer = 0;
  
  for(let i = 1; i <= n; i++) {
    answer = answer + i;
  }
  return answer;
}
document.write(solution(10));

/* <answer> 55 */
```

### 14.
```javascript
/********** 14. **********/
function solution() {
  let arr = [7, 3, 9, 5, 6, 12];
  
  for(let i = 1; i < arr.length; i++) {
    if(arr[i] > arr[i-1]) {
      document.write(arr[i]);
    }
  }
}
solution();

/* <answer> 9612 */
```

### 15.
```javascript
/********** 15. 오답 **********/
let str = "g0en2T0s8eSoft";

function solution(str) {
  let answer = "";
  
  for(let x of str) {
    if(x == 0 || x == 8) {
      answer++;
    }
  }
  return answer;
}
document.write(solution(str));

/* <answer> 3 */
```

### 16.
```javascript
/********** 16. **********/
let str = "teachermode";

function solution(s, t) {
  let answer = [];
  let p = 1000;
  
  for(let x of s) {
    if(x === t) {
      answer.push(p);
    }
  }
  return answer;
}
document.write(solution(str, 'e'));

/* <answer> 1000,1000,1000 */
```

### 17.
```javascript
/********** 17. **********/
function solution(s) {
  let answer = "";
  let cnt = 1;
  s = s + " ";
  
  for(let i = 0; i < s.length - 1; i++) {
    if(s[i] === s[i+1]) {
      cnt++;
    } else {
      answer += s[i];
      if(cnt > 1) {
        answer += String(cnt);
      }
      cnt = 1;
    }
  }
  return answer;
}
let str = "KKHSSSSSSSE";
document.write(solution(str));

/* <answer> K2HS7E */
```

### 18.
```javascript
/********** 18. **********/
let str = "ABCD";

function solution(s) {
  let answer;
  let stack = [];
  
  for(let x of s) {
    if(x === 'C') {
      stack.pop();
    } else {
      stack.push(x);
    }
  }
  answer = stack.join('');
  return answer;
}
document.write(solution(str));

/* <answer> AD */
```

### 19.
```javascript
/********** 19. **********/
function func() {
  let a = [1, 2, 3, 4, 5, 6, 7, 8, 9], cnt = 0;
  
  for(i = 0; i < a.length; i++) {
    if(a[i] % 2 == 0) {
      cnt = cnt + 1;
    } 
  }
  document .write(cnt);
}
func();

/* <answer> 4 */
```

### 20.
```javascript
/********** 20. **********/
function solution() {
  for(let i = 0; i < 5; i++) {
    for(let j = 0; j <= i; j++) {
      document.write('*');
    }
    document.write('<br>');
  }
}
solution();

/* <answer>
    *
    **
    ***
    ****
    *****     */
```

<br>
