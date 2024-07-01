# React Typescript

- <https://www.typescriptlang.org/>

<br>

## 1. Typing the Props

### App.tsx

```js
function App() {
  return (
    <div className="App">
      <Circle bgColor="teal" />
      <Circle bgColor="tomato" />
    </div>
  );
}
```

### Circle.tsx

```js
import styled from "styled-components";

interface ContainerProps {
  bgColor: string;
}

const Container = styled.div <ContainerProps>`
  width: 200px;
  height: 200px;
  background-color: ${(props) => props.bgColor};
`;

interface CircleProps {
  bgColor: string;
}

function Circle({ bgColor }: CircleProps) {
  return <Container bgColor={bgColor} />;
}

export default Circle;
```

<br>

## 2. Optional Props

### App.tsx

```js
function App() {
  return (
    <div className="App">
      <Circle bgColor="teal" />
      <Circle bgColor="tomato" />
    </div>
  );
}
```

### Circle.tsx

```js
import styled from "styled-components";

interface ContainerProps {
  bgColor: string;
  borderColor: string;
}

const Container = styled.div <ContainerProps>`
  width: 200px;
  height: 200px;
  background-color: ${(props) => props.bgColor};
  border-radius: 100px;
  border: 3px solid ${(props) => props.borderColor};
`;

interface CircleProps {
  bgColor: string; // required
  borderColor?: string; // optional
}

function Circle({ bgColor, borderColor }: CircleProps) {
  // optional props에 default값 보내기 : borderColor prop이 없다면 bgColor 보내기
  return <Container bgColor={bgColor} borderColor={borderColor ?? bgColor} />;
}

export default Circle;
```

<br>

## Forms & State

### App.tsx

```js
import React, { useState } from "react";

function App() {
  const [value, setValue] = useState("");

  const onChange = (event: React.FormEvent<HTMLInputElement>) => {
    console.log(event.currentTarget.value);
    const {
      currentTarget: { value },
    } = event;
    setValue(value);
  };

  const onSubmit = (event: React.FormEvent<HTMLFormElement>) => {
    event.preventDefault();
    console.log("helo :: ", value);
  };

  return (
    <div>
      <form onSubmit={onSubmit}>
        <input
          value={value}
          onChange={onChange}
          type="text"
          placeholder="username"
        />
        <button>Log in</button>
      </form>
    </div>
  );
}

export default App;
```

<br>

## Themes

styled components 테마와 타입스크립트를 연결하는 방법

### tyled.d.ts

```js
import "styled-components";

// and extend them!
declare module "styled-component" {
  export interface DefaultTheme {
    bgColor: string;
    textColor: string;
    btnColor: string;
  }
}

```

### theme.ts

```js
import { DefaultTheme } from "styled-components";

export const lightTheme: DefaultTheme = {
  bgColor: "white",
  textColor: "black",
  btnColor: "tomato",
};

export const darkTheme: DefaultTheme = {
  bgColor: "black",
  textColor: "white",
  btnColor: "teal",
};
```

### index.tsx

```js
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import { ThemeProvider } from "styled-components";
import { darkTheme, lightTheme } from "./theme";

const root = ReactDOM.createRoot(
  document.getElementById("root") as HTMLElement
);
root.render(
  <React.StrictMode>
    <ThemeProvider theme={lightTheme}>
      <App />
    </ThemeProvider>
  </React.StrictMode>
);
```

### App.tsx

```js
import styled from "styled-components";

const Container = styled.div`
  background-color: ${(props) => props.theme.bgColor};
`;

const H1 = styled.h1`
  color: ${(props) => props.theme.textColor};
`;

function App() {
  return (
    <Container>
      <H1>protext</H1>
    </Container>
  );
}

export default App;
```

<br>
