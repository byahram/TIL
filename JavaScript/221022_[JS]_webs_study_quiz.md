# 웹스스터디 221022 Quiz

---
<p align="center">
<img width="50%" src="../assets/img/js.png">
</p>

---

<br>

### 01.
```javascript
/********** 1. **********/
const arr = [1, 1, 3, 3, 0, 1, 1];

function solution(arr) {
  return arr.filter((item, idx) => item !== arr[idx+1]);
}

document.write(solution(arr));

/* <answer> 1,3,0,1 */
```

### 02.
```javascript
/********** 2. **********/
const arr = "webstoryboy";

function solution(s) {
  const answer = '';
  return s.length % 2 == 1 ? s[s.length/2 | 0] : s.slice(s.length/2 - 1, s.length/2 + 1);
}

document.write(solution(arr));

/* <answer> o */
```

### 03.
```javascript
/********** 3. **********/
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

function solution(numbers) {
  var answer = 0;
  for(let i = 0; i < numbers.length; i++) {
    answer = answer + numbers[i];
  }
  answer = answer/numbers.length;
  return answer;
}

document.write(solution(arr));

/* <answer> 5.5 */
```

### 04.
```javascript
/********** 4. **********/
const string = "webstoryboy";

function solution(s) {
  let answer = '';
  for(let i = s.length - 1; i >= 0; i--) {
    answer = answer + s[i];
  }
  return answer;
}

document.write(solution(string));

/* <answer> yobyrotsbew */
```

### 05.
```javascript
/********** 5. **********/
const num = 10;

function solution(n) {
  let answer = '';
  
  for(i = 0; i < n; i++) {
    if(i % 2 == 0) {
      answer += "코";
    } else {
      answer += "딩";
    }
  }
  return answer;
}

document.write(solution(num));

/* <answer> 코딩코딩코딩코딩코딩 */
```

### 06.
```javascript
/********** 6. 오답 **********/
const num = "webstoryboy";

function solution(s) {
  let answer;
  let arr = [...s];
  
  if(arr.length % 2 == 0) {
    answer = arr.splice(arr.length/2-1, 2);
  } else {
    answer = arr.splice(Math.floor(arr.length/2), 1);
  }
  return answer.join("");
}

document.write(solution(num));

/* <answer> o */
```

### 07.
```javascript
/********** 7. **********/
const num = [5, 9, 7, 10];

function solution(arr, divisor) {
  var answer = [];
  
  for(i = 0; i < arr.length; i++) {
    if(arr[i] % divisor == 0) answer.push(arr[i]);
  }
  return answer;
}

document.write(solution(num, 5));

/* <answer> 5,10 */
```

### 08.
```javascript
/********** 8. 오답 **********/
const num = [5, 9, 7, 10];

function solution(arr) {
  let sm = arr[0], index = 0;
  
  for(i = 0; i < arr.length; i++) {
    if(arr[i] < sm) {
      sm = arr[i];
      index = i;
    }
  }
  arr.splice(index, 1);
  return arr;
}

document.write(solution(num));

/* <answer> 9,7,10 */
```

### 09.
```javascript
/********** 9. **********/
const num = "webstoryboy";

function solution(s) {
  let answer = s.split("");
  
  for(i = 0; i < answer.length - 4; i++) {
    answer[i] = "*";
  }
  return answer.join("");
}

document.write(solution(num));

/* <answer> *******yboy */
```

### 10.
```javascript
/********** 10. **********/
function solution(arr1, arr2) {
  let answer = [];
  arr1.sort();
  arr2.sort();
  let p1 = p2 = 0;
  
  while(p1 < arr1.length && p2 < arr2.length) {
    if(arr1[p1] == arr2[p2]) {
      answer.push((arr1[p1++]));
      p2++;
    }
    else if(arr1[p1] < arr2[p2]) p1++;
    else p2++;
  }
  return answer;
}

let a = [1, 3, 9, 5, 2];
let b = [3, 2, 5, 7, 8];

document.write(solution(a, b));

/* <answer> 2,3,5 */
```

<br>
