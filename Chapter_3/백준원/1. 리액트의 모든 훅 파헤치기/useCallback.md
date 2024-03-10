# useCallback

useMemo가 값을 기억했다면, useCallback은 인수로 넘겨받은 콜백 자체를 기억한다.

특정 함수를 새로 만들지 않고 다시 재사용

> ### useMemo와 useCallback의 차이
>
> - useMemo => 값의 메모이제이션
> - useCallback => 함수의 메모이제이션

첫 번째 인수: 함수
두 번째 인수: 의존성 배열

의존성 배열이 변경되지 않는 한 함수를 재생성하지 않는다.

함수의 재생성을 막아 불필요한 리소스 또는 리렌더링을 방지하고 싶을 때 사용

### 왜 useCallback에 기명 함수를 넘겨주었나??

일반적으로 useCallback이나 useMemo를 사용할 때 useEffect와 마찬가지로 많은 코드가 익명 함수로 첫 번째 인수를 넘겨준다.

```JavaScript
const toggle1 = useCallback(() => {
    setStatus1(!status1)
}, [status1])
```

위의 예제와 같이 기명 함수를 넘겨준 이유는 크롬 메모리 탭에서 디버깅을 용이하게 하기 위해서이다.

익명 함수는 말 그대로 이름이 없어 해당 함수를 추적하기 어렵다.

useCallback이나 useMemo는 모두 동일한 역할을 하지만 함수를 메모이제이션하는 용도라면 더 간단한 useCallback을 사용하자
