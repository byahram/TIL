# Styled Component란?

- <https://styled-components.com/>

<br>

## Styled Component란?

Styled Component란 Css-in-JS라고 하는 JavaScript 파일 안에서 CSS를 처리할 수 있게 해주는 대표적인 라이브러리다.

<br>

## 설치 방법

```sh
#  with npm
$ npm install --save styled-components

#  with yarn
$ yarn add styled-components
```

<br>

## 1. Props 전달 1

```js
const Father = styled.div`
  display: flex;
`;

const Box = styled.div`
  background-color: ${(props) => props.bgColor};
  width: 100px;
  height: 100px;
`;

function App() {
  return (
    <Father>
      <Box bgColor="tomato" />
      <Box bgColor="teal" />
    </Father>
  );
}
```

<br>

## 2. Props 전달 2

```js
const Father = styled.div`
  display: flex;
`;

const Box = styled.div`
  background-color: ${(props) => props.bgColor};
  width: 100px;
  height: 100px;
`;

const Circle = styled(Box)`
  // Box의 모든 속성들을 가져온다
  /* background-color: ${(props) => props.bgColor};
  width: 100px;
  height: 100px; */
  border-radius: 50px;
`;

function App() {
  return (
    <Father>
      <Box bgColor="tomato" />
      <Circle bgColor="teal" />
    </Father>
  );
}
```

<br>

## 3. As

```js
const Father = styled.div`
  display: flex;
`;

const Btn = styled.button`
  color: white;
  background-color: tomato;
  border: 0;
  border-radius: 15px;
  padding: 2px 10px;
`;

function App() {
  return (
    <Father>
      <Btn>Log in</Btn>
      <Btn as="a" href="/">
        Log in 2
      </Btn>
    </Father>
  );
}
```

<br>

## 4. Attrs

```js
const Father = styled.div`
  display: flex;
  flex-direction: column;
`;

const Input = styled.input.attrs({ required: true, minLength: 10 })`
  background-color: tomato;
  width: 200px;
`;

function App() {
  return (
    <Father as="header">
      <Input />
      <Input />
      <Input />
      <Input />
      <Input />
      <Input />
    </Father>
  );
}
```

<br>

## 5. Animations

```js
const rotationAnimation = keyframes`
  /* from {
    transform: rotate(0deg);
    border-radius: 0;
  }
  to {
    transform: rotate()(360deg);
    border-radius: 100px;
  } */

  0%{
    transform: rotate(0deg);
    border-radius: 0px;
  }
  50%{
    border-radius: 100px;
  }
  100%{
    transform: rotate(360deg);
    border-radius: 0px;
  }
`;

const Wrapper = styled.div`
  display: flex;
`;

const Box = styled.div`
  width: 200px;
  height: 200px;
  background-color: tomato;
  display: flex;
  justify-content: center;
  align-items: center;
  animation: ${rotationAnimation} 1s linear infinite;
  span {
    font-size: 36px;
  }
`;

function App() {
  return (
    <Wrapper>
      <Box>
        <span>🤍</span>
      </Box>
    </Wrapper>
  );
}
```

<br>

## 6. Pseudo Selectors 1

```js
const Wrapper = styled.div`
  display: flex;
`;

const Box = styled.div`
  width: 200px;
  height: 200px;
  background-color: tomato;
  display: flex;
  justify-content: center;
  align-items: center;
  span {
    font-size: 36px;
    &:hover {
      font-size: 20px;
    }
    &:active {
      opacity: 0;
    }
  }
`;

function App() {
  return (
    <Wrapper>
      <Box>
        <span>🤍</span>
      </Box>
    </Wrapper>
  );
}
```

<br>

## 7. Pseudo Selectors 2

```js
const Emoji = styled.span`
  font-size: 36px;
`;

const Box = styled.div`
  width: 200px;
  height: 200px;
  background-color: tomato;
  display: flex;
  justify-content: center;
  align-items: center;
  ${Emoji}:hover {
    font-size: 70px;
  }
`;

function App() {
  return (
    <Wrapper>
      <Box>
        <Emoji>🤍</Emoji>
      </Box>
      <Emoji>🟦</Emoji>
    </Wrapper>
  );
}
```

<br>

## 예제) Styled Component를 이용한 UI 생성

```js
import styled from "styled-components";

export default function Banner() {
  return (
    <Container>
      <HomeContainer>
        <Iframe
          width="640"
          height="360"
          src={`https://www.youtube.com/embed/${movie.videos.results[0].key}?controls=0&autoplay=1&loop=1&mute=1&playlist=${movie.videos.results[0].key}`}
          title="YouTube video player"
          frameborder="0"
          allow="autoplay; fullscreen"
          allowfullscreen
        ></Iframe>
      </HomeContainer>
    </Container>
  );
}

const Iframe = styled.iframe`
  width: 100%;
  height: 100%;
  z-index: -1;
  opacity: 0.65;
  border: none;

  &::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
`;

const Container = styled.div`
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
  height: 100vh;
`;

const HomeContainer = styled.div`
  width: 100%;
  height: 100%;
`;
```

<br>
