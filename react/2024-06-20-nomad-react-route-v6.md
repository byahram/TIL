# React Router v6

<br>

## React Router Dom이란?

React Router DOM을 사용하면 웹 앱에서 동적 라우팅을 구현할 수 있다. 라우팅이 실행 중인 앱 외부의 구성에서 처리되는 기존 라우팅 아키텍처와 달리 React Router DOM은 앱 및 플랫폼의 요구 사항에 따라 컴포넌트 기반 라우팅을 용이하게 한다.

<br>

## React Router Dom 설치하기

```sh
# NPM
$ npm install react-router-dom --save

# YARN
$ yarn add react-router-dom
```

<br>

## 1. BrowserRouter

### Ex1

```js
// main.tsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import { BrowserRouter } from "react-router-dom";

ReactDOM.createRoot(document.getElementById("root")!).render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
);


// App.tsx
import Router from "./Router";

function App() {
  return <Router />;
}

export default App;


// Router.tsx
import { BrowserRouter, Route, Routes } from "react-router-dom";
import Header from "./components/Header";
import Home from "./screens/Home";
import About from "./screens/About";

function Router() {
  return (
    <BrowserRouter>
      <Header />
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}

export default Router;


// About.tsx
function About() {
  return <h1>About</h1>;
}

export default About;


// Home.tsx
function Home() {
  return <h1>Home</h1>;
}

export default Home;


// Header.tsx
import { Link } from "react-router-dom";

function Header() {
  return (
    <header>
      <ul>
        <li>
          <Link to={"/"}>Home</Link>
        </li>
        <li>
          <Link to={"/about"}>About</Link>
        </li>
      </ul>
    </header>
  );
}

export default Header;
```

<br>

## 2. createBrowserRouter

```js
// index.tsx
import React from "react";
import ReactDOM from "react-dom/client";
import { RouterProvider } from "react-router-dom";
import router from "./Router";

const root = ReactDOM.createRoot(
  document.getElementById("root") as HTMLElement
);
root.render(
  <React.StrictMode>
    <RouterProvider router={router} />
  </React.StrictMode>
);


// Router.tsx
import { createBrowserRouter } from "react-router-dom";
import Home from "./screens/Home";
import About from "./screens/About";
import Root from "./Root";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    children: [
      {
        path: "",
        element: <Home />,
      },
      {
        path: "about",
        element: <About />,
      },
    ],
  },
]);

export default router;


// Root.tsx
import { Outlet } from "react-router-dom";
import Header from "./components/Header";

function Root() {
  return (
    <div>
      <Header />
      <Outlet />
    </div>
  );
}

export default Root;


// About.tsx
function About() {
  return <h1>About</h1>;
}

export default About;


// Home.tsx
function Home() {
  return <h1>Home</h1>;
}

export default Home;


// Header.tsx
import { Link } from "react-router-dom";

function Header() {
  return (
    <header>
      <ul>
        <li>
          <Link to={"/"}>Home</Link>
        </li>
        <li>
          <Link to={"/about"}>About</Link>
        </li>
      </ul>
    </header>
  );
}

export default Header;
```

<br>

## 3. Nested Routes 중첩 라우팅

```js
<BrowserRouter>
  <Routes>
    {/* App 컴포넌트에 Header Footer등 Layout */}
    <Route path="/" element={<App />}>
      {/* localhost:3000/ 경로 => Home 컴포넌트 */}
      <Route index element={<Home />} />
      {/* localhost:3000/teams 경로 => Teams 컴포넌트가 Layout */}
      <Route path="teams" element={<Teams />}>
        {/* localhost:3000/teams/13 경로 => Team 컴포넌트 */}
        <Route path=":teamId" element={<Team />} />
        <Route path="new" element={<NewTeamForm />} />
        {/* localhost:3000/teams 경로 => LeagueStandings 컴포넌트 */}
        <Route index element={<LeagueStandings />} />
      </Route>
    </Route>
  </Routes>
</BrowserRouter>
```

<br>

## 4. errorElement

```js
// Router.tsx
import { createBrowserRouter } from "react-router-dom";
import Home from "./screens/Home";
import About from "./screens/About";
import Root from "./Root";
import NotFound from "./screens/NotFound";
import ErrorComponent from "./components/ErrorComponenet";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    children: [
      {
        path: "",
        element: <Home />,
        errorElement: <ErrorComponent />,
      },
      {
        path: "about",
        element: <About />,
      },
    ],
    errorElement: <NotFound />,
  },
]);

export default router;


// NotFound
function NotFound() {
  return <h1>404 Not Found.</h1>;
}

export default NotFound;


// ErrorComponent.tsx
import React from "react";

export default function ErrorComponent() {
  return <h1>This component crashed</h1>;
}
```

<br>

## 5. useNavigation

### Ex1

```js
//  Header.tsx
import { Link, useNavigate } from "react-router-dom";

function Header() {
  const navigate = useNavigate();

  const onAboutClick = () => {
    navigate("/about");
  };

  return (
    <header>
      <ul>
        <li>
          <Link to={"/"}>Home</Link>
        </li>
        <li>
          <button onClick={onAboutClick}>About</button>
        </li>
      </ul>
    </header>
  );
}

export default Header;
```

### Ex2

```js
import { useNavigate } from "react-router-dom";

function SignupForm() {
  let navigate = useNavigate();

  async function handleSubmit(event) {
    event.preventDefault();
    await submitForm(event.target);
    navigate("../success", { replace: true });
  }

  return <form onSubmit={handleSubmit}>{/* */}</form>;
}
```

<br>

## 6. useParams

```js
// db.ts
export const users = [
  { id: 1, name: "nico" },
  { id: 2, name: "lynn" },
];


// Router.tsx
import { createBrowserRouter } from "react-router-dom";
import Home from "./screens/Home";
import About from "./screens/About";
import Root from "./Root";
import NotFound from "./screens/NotFound";
import ErrorComponent from "./components/ErrorComponenet";
import User from "./screens/users/User";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    children: [
      {
        path: "users/:userId",
        element: <User />,
      },
      // {
      //   path: "users",
      //   element: <User />,
      //   children: [{ path: ":userId", element: <User /> }],
      // },
    ],
  },
]);

export default router;


// User.tsx
import { useParams } from "react-router-dom";
import { users } from "../../db";

function User() {
  const { userId } = useParams();
  return (
    <h1>
      User with Id {userId} is named: {users[Number(userId) - 1].name}
    </h1>
  );
}

export default User;
```

<br>

## 7. Outlet

자식 경로 요소를 렌더링하려면 부모 경로 요소에서 <Outlet>을 사용해야 한다. 이렇게 하면 하위 경로가 렌더링될 때 중첩된 UI가 표시될 수 있다. 부모 라우트가 정확히 일치하면 자식 인덱스 라우트를 렌더링하거나 인텍스 라우트가 없으면 아무것도 렌더링하지 않는다.

### Ex1

```js
// User.tsx
import { Link, Outlet, useParams } from "react-router-dom";
import { users } from "../../db";

function User() {
  const { userId } = useParams();
  return (
    <div>
      <h1>
        User with Id {userId} is named: {users[Number(userId) - 1].name}
      </h1>
      <hr />
      <Link to="followers">See Followers</Link>
      <Outlet />
    </div>
  );
}

export default User;


// Router.tsx
import { createBrowserRouter } from "react-router-dom";
import Root from "./Root";
import NotFound from "./screens/NotFound";
import User from "./screens/users/User";
import Followers from "./screens/users/Followers";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    children: [
      {
        path: "users/:userId",
        element: <User />,
        children: [{ path: "followers", element: <Followers /> }],
      },
    ],
    errorElement: <NotFound />,
  },
]);

export default router;


// Followers.tsx
function Followers() {
  return <h1>Followers</h1>;
}

export default Followers;
```

### Ex2

```js
// App.jsx

import { Outlet, Routes, Route } from "react-router-dom";
import "./App.css";
import Footer from "./components/Footer";
import Nav from "./components/Nav";
import MainPage from "./pages/MainPage";
import DetailPage from "./pages/DetailPage";
import SearchPage from "./pages/SearchPage";

const Layout = () => {
  return (
    <div>
      <Nav />
      <Outlet />
      <Footer />
    </div>
  );
};

function App() {
  return (
    <div className="app">
      <Routes>
        <Route path="/" element={<Layout />}>
          <Route index element={<MainPage />} />
          <Route path=":movieId" element={<DetailPage />} />
          <Route path="search" element={<SearchPage />} />
        </Route>
      </Routes>
    </div>
  );
}

export default App;
```

<br>

## 8. useOutletContext

### Ex1

```js
// Users.tsx
import { Link, Outlet, useOutletContext, useParams } from "react-router-dom";
import { users } from "../../db";

function User() {
  console.log(useOutletContext);
  const { userId } = useParams();
  return (
    <div>
      <h1>
        User with Id {userId} is named: {users[Number(userId) - 1].name}
      </h1>
      <hr />
      <Link to="followers">See Followers</Link>
      <Outlet context={{ nameOfMyUser: users[Number(userId) - 1].name }} />
    </div>
  );
}

export default User;


// Followers.tsx
import { useOutletContext } from "react-router-dom";

interface IFollowersContext {
  nameOfMyUser: string;
}

function Followers() {
  const { nameOfMyUser } = useOutletContext<IFollowersContext>();

  return <h1>Here are {nameOfMyUser}의 followers</h1>;
}

export default Followers;
```

### Ex2

```js
// Root.tsx
import { Outlet } from "react-router-dom";
import Header from "./components/Header";

function Root() {
  return (
    <div>
      <Header />
      <Outlet context={{ darkMode: true }} />
    </div>
  );
}

export default Root;
```

<br>

## 9. useLocation

현재 위치 객체를 반환한다. 현재 위치가 변경될 때마다 일부 side effect을 수행하려는 경우에 유용할 수 있다.

```js
// App.jsx
import { useLocation } from "react-router-dom";

function App() {
  let location = useLocation();

  React.useEffect(() => {
    ga('send', 'pageview');
  }, [location]);

  return ();
}

```

<br>

## Extras : useSearchParams

<br>
