# Props와 State

<br>

## props란?

- 컴포넌트가 외부에서 받는 데이터 즉 부모로부터 자식 컴포넌트로 데이터를 넘겨줄 때 사용한다.
- 읽기 전용 데이터이므로 직접적으로 수정이 불가능하다.

```js
function ParentComponent() {
  return <ChildComponent prop1="value1" prop2="value2" />;
}

function ChildComponent(props) {
  return (
    <div>
      <p>Prop 1: {props.prop1}</p>
      <p>Prop 2: {props.prop2}</p>
    </div>
  );
}
```

<br>

## state란?

- Component 내부에서 관리하는 데이터로 변경이 가능한 값이다.

```js
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  incrementCount() {
    this.setState({ count: this.state.count + 1 });
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={() => this.incrementCount()}>Increment</button>
      </div>
    );
  }
}
```

<br>

## 참고하면 좋을 사이트

- <https://minjung-jeon.github.io/React-props-state/>
- <https://kindjjee.tistory.com/102>
- <https://goddaehee.tistory.com/300>
- <https://goddaehee.tistory.com/301?category=395445>
- <https://ko.legacy.reactjs.org/docs/components-and-props.html>

<br>
