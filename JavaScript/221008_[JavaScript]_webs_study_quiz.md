# 웹스스터디 221008 Quiz

---
<p align="center">
<img width="50%" src="../assets/img/js.png">
</p>

---

<br>

### 01.
```javascript
/********** 1. **********/
function solution(a, b, c) {
    let answer="YES", max;
    let tot = a + b + c;
    
    if(a > b) max = a;
    else max = b;
     
    if(c > max) max = c;
    if(tot - max <= max) answer = "NO"
    
    return answer;
}
document.write(solution(13, 33, 17));

/* <answer> NO */
```

### 02.
```javascript
/********** 2. **********/
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

### 03.
```javascript
/********** 3. **********/
function solution(n) {
    let answer;
    answer = Math.ceil(n/12);
    return answer;
}
document.write(solution(178));

/* <answer> 15 */
```

### 04.
```javascript
/********** 4. **********/
function solution(n) {
    let answer=0;
    for(let i = 1; i <= n; i++) {
        answer = answer + i;
    }
    return answer;
}
document.write(solution(5));

/* <answer> 15 */
```

### 05.
```javascript
/********** 5. **********/
function solution(arr) {
    let answer = [];
    let sum = 0, min = 1000;
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
arr = [12, 77, 38, 41, 53, 92, 85];
document.write(solution(arr));

/* <answer> 256,41 */
```

### 06.
```javascript
/********** 6. **********/
function solution(day, arr) {
    let answer = 0;
    for(let x of arr) {
        if(x % 10 == day) answer++;
    }
    return answer;
}
arr = [25, 23, 11, 47, 53, 17, 33];
document.write(solution(3, arr));

/* <answer> 3 */
```

### 07.
```javascript
/********** 7. 오답 **********/
function solution(arr) {
    let answer = arr;
    let sum = answer.reduce((a,b) => a + b, 0);

    for(let i = 0; i < 8; i++) {
        for(let j = i+1; j < 9; j++) {
            if((sum - (answer[i] + answer[j])) == 100) {
                answer.splice(j, 1);
                answer.splice(i, 1);
            }
        }
    }
    return answer;
}
let arr=[20, 7, 23, 19, 10, 15, 25, 8, 13];
document.write(solution(arr));

/* <answer> 20,7,23,19,10,8,13 */
```

### 08.
```javascript
/********** 8. **********/
function solution(s) {
    let answer = "";
    for(let x of s) {
        if(x =='A') answer += "#";
        else answer += x;
    }
    return answer;
}
let str = "BANANA";
document.write(solution(str));

/* <answer> B#N#N# */
```

### 09.
```javascript
/********** 9. 오답 **********/
function solution(s) {
    let answer = s;
    answer = answer.replace(/a/g, "#");
}
let str="javascript";
document.write(solution(str));

/* <answer> undefined */
```

### 10.
```javascript
/********** 10. **********/
function solution(s, t) {
    let answer = s.split(t).length;
    return answer - 1;
}
let str = "javascript react vue";
document.write(solution(str, 'a'));

/* <answer> 3 */
```

### 11.
```javascript
/********** 11. **********/
function solution(s) {
    let answer = 0;
    for(let x of s) {
        if(x === x.toUpperCase()) answer++;
    }
    return answer;
}
let str = "KoreaTimeGood";
document.write(solution(str));

/* <answer> 3 */
```

### 12.
```javascript
/********** 12. **********/
function solution(s) {
    let answer = "";
    for(let x of s) {
        let num = x.charCodeAt();

        if(x === x.toLowerCase()) answer += x.toUpperCase();
        else answer += x;
    }
    return answer;
}
let str = "ItisTimeToStudy";
document.write(solution(str));

/* <answer> ITISTIMETOSTUDY */
```

### 13.
```javascript
/********** 13. **********/
function solution(s) {
    let answer = "";
    for(let x of s) {
        if(x === x.toUpperCase()) answer += x.toLowerCase();
        else answer += x.toUpperCase()
    }
    return answer;
}
document.write(solution("StuDY"));

/* <answer> sTUdy */ 
```

### 14.
```javascript
/********** 14. **********/
function solution(s) {
	// max = Number.MIN_SAFE_INTEGER; 정수값 표현 방식
    let answer = "", max = Number.MIN_SAFE_INTERGER;
    for(let x of s) {
        if(x.length > max) {
            max = x.length;
            answer = x;
        }
    }
    return answer;
}
let str = ["teacher", "time", "student", "beautiful", "good"];
document.write(solution(str));

/* <answer> beautiful */
```

### 15.
```javascript
/********** 15. 오답 **********/
//substring() 메서드는 string 객체의 시작 인덱스로 부터 종료 인덱스 전까지 문자열의 부분 문자열을 반환합니다.
function solution(s) {
    let answer;
    let mid = Math.floor(s.length / 2);

    if(s.length % 2) answer = s.substring(mid, mid + 1);
    else answer = s.substring(mid - 1, mid + 1);
    return answer;
}
document.write(solution("study"));

/* <answer> u */
```

### 16.
```javascript
/********** 16. 오답 **********/
function solution(s) {
    let answer = "";
    for(let i = 0; i < s.length; i++) {
        if(s.indexOf(s[i]) === i) answer += s[i];
    }
    return answer;
}
document.write(solution("ksekkset"));

/* <answer> kset */
```

### 17.
```javascript
/********** 17. 오답 **********/
function solution(s) {
    let answer;
    answer = s.filter(function(v, i) {
        return s.indexOf(v) === i;
    });
    return answer;
}
let str = ["good", "time", "good", "time", "student"];
document.write(solution(str));

/* <answer> good,time,student */
```

### 18.
```javascript
/********** 18. 오답 **********/
function solution(s) {
    let answer = "YES";
    stack = [];
    for(let x of s) {
        if(x ==='(') stack.push(x);
        else {
            if(stack.length === 0) return "NO";
            stack.pop();
        }
    }
    if(stack.length > 0) return "NO";
}
let a="(()(()))(()";
document.write(solution(a));

/* <answer> NO */
```

### 19.
```javascript
/********** 19. 오답 **********/
function solution(s) {
    let answer;
    let stack = [];
    for(let x of s) {
        if(x === ')') {
            while(stack.pop() !== '(');
        }
        else stack.push(x);
    }
    answer = stack.join("");
    return answer;
}
let str="(A(BC)D)EF(G(H)(IJ)K)LM(N)";
document.write(solution(str));

/* <answer> EFLM */
```

### 20.
```javascript
/********** 20. 오답 **********/
function solution(n, k) {
    let answer;
    let queue = Array.from({length : n}, (v,i) => i + 1);
    while(queue.length) {
        for(let i = 1; i < k; i++) queue.push(queue.shift());
        queue.shift();
        if(queue.length === 1) answer = queue.shift();
    }
    return answer;
}
document.write(solution(8,3));

/* <answer> 7 */
```

<br>
