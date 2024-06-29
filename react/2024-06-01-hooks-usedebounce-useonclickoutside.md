# 커스텀 Hooks : useDebounce(), useOnClickOutside()

<br>

## useDebounce()

검색 입력창에 입력할 때 입력 결과가 나타날 때까지 지연이 있다.

이 기능은 debounce 디바운스라는 function에 의해 제어된다.

debounce function은 사용자가 미리 결정된 시간 동안 타이핑을 멈출 때까지 keyup 이벤트의 처리를 지연 시켜준다.

이렇게 하면 UI 코드가 모든 이벤트를 처리할 필요가 없고 서버로 전송되는 API 호출 수도 크게 줄어든다.

입력된 모든 문자를 처리하면 성능이 저하되고 백엔드에 불필요한 로드가 추가될 수 있다.

### index.js

```js
import { useDebounce } from "../../hooks/useDebounce";
import { useLocation, useNavigate } from "react-router-dom";

const useQuery = () => {
  return new URLSearchParams(useLocation().search);
};

let query = useQuery();
const searchTerm = query.get("q");
const debouncedSearchTerm = useDebounce(searchTerm, 500); // 0.5초가 지난 다음에 Debounce value로 들어감

useEffect(() => {
  if (debouncedSearchTerm) {
    fetchSearchMovie(debouncedSearchTerm);
  }
}, [debouncedSearchTerm]);

<section className="no-results">
  <div className="no-results__text">
    <p>찾고자하는 검색어"{debouncedSearchTerm}"에 맞는 영화가 없습니다.</p>
  </div>
</section>;
```

### useDebounce.js

```js
import { useState, useEffect } from "react";

export const useDebounce = (value, delay) => {
  // State and setters for debounced value
  const [debounceValue, setDebounceValue] = useState(value);

  useEffect(() => {
    // Update debounced value after delay
    const handler = setTimeout(() => {
      setDebounceValue(value);
    }, delay);

    // Cancel the timeout if value changes (also on delay change or unmount)
    // This is how we prevent debounced value from updating if value is changed ...
    // .. within the delay period. Timeout gets cleared and restarted.
    return () => {
      clearTimeout(handler);
    };
  }, [value, delay]); // Only re-call effect if value or delay changes

  return debounceValue;
};
```

<br>

## useOnClickOutside()

useRef()를 이용해서 Ref 객체를 만들고 이 객체를 특정 DOM에 ref 값으로 설정한다. 이렇게 되면 객체의 .current 값이 특정 DOM을 가리키게 된다.

- DOM을 직접 선택해야 할 경우
  - 엘리먼트 크기를 가져와야 할 때
  - 스크롤바 위치를 가져와야 할 때
  - 엘리먼트에 포커스를 설정 해줘야 할 때 등

### MovieModal.js

```js
import useOnClickOutside from "../../hooks/useOnClickOutside";

const ref = useRef();

useOnClickOutside(ref, () => {
  setModalOpen(false);
});

<div className="modal" ref={ref}>
  <span onClick={() => setModalOpen(false)} className="modal-close">
    X
  </span>
  ...
</div>;
```

### useOnClickOutside.js

```js
import { useEffect } from "react";

export default function useOnClickOutside(ref, handler) {
  useEffect(() => {
    const listener = (event) => {
      if (!ref.current || ref.current.contains(event.target)) {
        // 클릭 시 모달창 안이면 그냥 return
        return;
      }
      handler(event);
    };
    // 모달 창 바깥을 클릭하면 Callback 함수를 호출하는 Event를 등록
    document.addEventListener("mousedown", listener);
    document.addEventListener("touchstart", listener);
    return () => {
      document.removeEventListener("mousedown", listener);
      document.removeEventListener("touchstart", listener);
    };
  }, [ref, handler]);
}
```

<br>
