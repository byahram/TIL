# 전개 연산자(Spread Operator)란?

<br>

## 전개 연산자란?

특정 객체 또는 배열의 값을 다른 객체, 배열로 복제하거나 옮길 때 사용한다.

<br>

## 배열 조합

```js
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [7, 8, 9];
const arrWrap = arr1.concat(arr2, arr3);

console.log(arrWrap); // [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

```js
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [7, 8, 9];
const arrWrap = [...arr1, ...arr2, ...arr3];

console.log(arrWrap); // [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

<br>

## 객체 조합

```js
const obj1 = {
  a: "A",
  b: "B",
};

const obj1 = {
  c: "C",
  d: "D",
};

const objWrap = { obj1, obj2 };
console.log(objWrap);

/*** 
객체 자체가 들어간다.
{
    obj1: {
        a: 'A',
        b: 'B'
    },
    obj2: {
        c: 'C',
        d: 'D'
    }
}
***/
```

```js
const obj1 = {
  a: "A",
  b: "B",
};

const obj1 = {
  c: "C",
  d: "D",
};

const objWrap = { ...obj1, ...obj2 };
console.log(objWrap);

/*** 
객체 자체가 아닌 각각의 값이 할당된다.
{
    a: 'A',
    b: 'B',
    c: 'C',
    d: 'D'
}
***/
```

<br>

## 기존 배열 보존

```js
const arr1 = [1, 2, 3];
const arr2 = arr1.reverse();

console.log(arr1);        // [3, 2, 1]
console.log(arr2);        // [3, 2, 1]

-> 원본 배열까지 역순으로 변경된다
```

```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1].reverse();

console.log(arr1);        // [1, 2, 3]
console.log(arr2);        // [3, 2, 1]

-> 원본 배열 유지
```

<br>
