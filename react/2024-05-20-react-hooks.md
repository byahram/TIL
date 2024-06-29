# React Hooks: useState(), useEffect(), useCallback(), useMemo()

<br>

## React Hooks란?

- <https://react.dev/reference/react/hooks>
- <https://k-developer.gitbook.io/dev/react/react-hook>

> 함수형 컴포넌트에서도 클래스형 컴포넌트의 기능을 사용할 수 있게 하는 기능이다.
>
> 훅을 통해 함수형 컴포넌트에서도 컴포넌트 상탯값을 관리할 수 있고, 컴포넌트의 생명 주기 함수를 이용할 수 있다.

#### < 클래스형 컴포넌트 vs 함수형 컴포넌트 비교 >

| Class Component   | Functional Component    |
| ----------------- | ----------------------- |
| 더 많은 기능 제공 | 더 적은 기능 제공       |
| 긴 코드 양        | 짧은 코드 양            |
| 더 복잡한 코드    | 더 심플한 코드 (가독성) |
| 더딘 성능         | 더 빠른 성능            |

<br>

## 기본 Hooks: useState(), useEffect()

### 1. useState()

- <https://react.dev/reference/react/useState>
- <https://ko.legacy.reactjs.org/docs/hooks-state.html>

```js
// useState Hook을 React에서 가져온다.
import React, { useState } from "react";

function Example() {
  // 새로운 state 변수를 선언하고, count라 부르겠습니다.
  // useState Hook을 이용하면 state 변수와 해당 state을 갱신할 수 있는 함수가 만들어진다.
  // useState의 인자 값으로 0을 넘겨주면 count 값을 0으로 초기화할 수 있다.
  const [count, setCount] = useState(0);

  // 사용자가 버튼을 클릭하면 setCount 함수를 호출하여 state 변수를 갱신한다.
  // count 변수를 Example 컴포넌트에 넘기며 해당 컴포넌트를 리렌더링한다.
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

```js
function ExampleWithManyStates() {
  // 여러 개의 state를 선언할 수 있다!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState("banana");
  const [todos, setTodos] = useState([{ text: "Learn Hooks" }]);
}
```

### 2. useEffect()

- <https://react.dev/reference/react/useEffect>
- <https://ko.legacy.reactjs.org/docs/hooks-effect.html>

> React 컴포넌트 안에서 데이터를 가져오거나 구독하고, DOM을 직접 조작하는 작업을 "side effects"라고 한다.
>
> useEffect는 함수 컴포넌트 내에서 이런 side effects를 수행할 수 있게 해준다.
>
> componentDidMount, componentDidUpdate나 componentWillUnmount와 같은 목적으로 제공되지만 useEffect라는 하나의 API로 통합된 것이다.

```js
import React, { useState, useEffect } from "react";

function Example() {
  const [count, setCount] = useState(0);

  // componentDidMount, componentDidUpdate와 같은 방식
  useEffect(() => {
    // 브라우저 API를 이용해 문서의 타이틀을 업데이트합니다
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

<br>

## 추가 Hooks: useCallback(), useMemo()

### 1. useCallback()

- <https://react.dev/reference/react/useCallback>
- <https://ko.legacy.reactjs.org/docs/hooks-reference.html#usecallback>

```js
const handleClick = useCallback(
  (id) => {
    let newTodoData = todoData.filter((data) => data.id !== id);
    setTodoData(newTodoData);
    localStorage.setItem("todoData", JSON.stringify(newTodoData));
  },
  [todoData]
);
```

컴포넌트가 렌더링 될 때 그 안에 있는 함수도 다시 만들게 된다.

useCallback 적용은 useCallback 안에 콜백함수와 의존성 배열을 순서대로 넣어주면 된다.

함수 내에서 참조하는 state, props가 있다면 의존성 배열에 추가하면 된다.

useCallback으로 인해 todoData가 변하지 않는다면 함수는 새로 생성되지 않는다.

새로 생성되지 않기에 메모리에 새로 할당되지 않고 동일 참조 값을 사용하고

의존성 배열에 아무것도 없다면 컴포넌트가 최초 렌더링 시에만 함수가 생성되며 그 이후에는 동일한 참조 값을 사용하는 함수가 된다.

### 2. useMemo()

- <https://react.dev/reference/react/useMemo>
- <https://ko.legacy.reactjs.org/docs/hooks-reference.html#usememo>

```js
function Component({ a, b }) {
  const result = useMemo(() => compute(a, b), [a, b]);
  return <div>{result}</div>;
}
```

Memoization이란 비용이 많이 드는 함수 호출의 결과를 저장하고 동일한 입력이 다시 발생할 때 캐시된 결과를 반환하여 컴퓨터 프로그램의 속도를 높이는 데 주로 사용되는 최적화 기술이다.

Component 내의 compute 함수가 만약 복잡한 연산을 수행하면 결과 값을 리턴하는데 오랜 시간이 걸리게 된다.

이럴 경우 컴포넌트가 계속 리렌더링 된다면 연산을 수행하는데 오랜 시간이 걸려서 성능에 안 좋은 영향을 미치게 되며 UI 지연 현상도 일어난다.

이러한 현상을 해결해주기 위해 사용하는 것이 useMemo이다.

compute 함수에 넘겨주는 a, b의 값이 이전과 동일하다면 컴포넌트가 리렌더링 되더라도 연산을 다시 하지 않고 이전 렌더링 때 저장해두었던 값을 재활용한다.

<br>
