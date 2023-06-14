## [클라이언트 컴포넌트를 Leaf로 배치하십시오.](https://nextjs.org/docs/getting-started/react-essentials#moving-client-components-to-the-leaves)
- interactive search bar that uses state


## [클라이언트 컴포넌트에서 서버 컴포넌트 사용.](https://nextjs.org/docs/getting-started/react-essentials#composing-client-and-server-components)

### Bad
클라이언트 컴포넌트에서 서버 컴포넌트를 import 하면 동작하지 않습니다.
```ts
'use client'
// 
import ExampleServerComponent from './example-server-component'
 
export default function ExampleClientComponent({
  children,
}: {
  children: React.ReactNode
}) {
  const [count, setCount] = useState(0)
 
  return (
    <>
      <button onClick={() => setCount(count + 1)}>{count}</button>
 
      <ExampleServerComponent />
    </>
  )
}
```
### Good
props를 사용하여 서버 컴포넌트를 사용할 경우 사용가능합니다.
```ts
'use client'
export default function ExampleClientComponent({
  children,
}: {
  children: React.ReactNode
}) {
 
  return (
    <>
      {children}
    </>
  )
}
```

## [서버에서만 사용해야 할 컴포넌트를 분리하십시오](https://nextjs.org/docs/getting-started/react-essentials#keeping-server-only-code-out-of-client-components-poisoning)
다음 함수가 클라이언트에서 실행 될 경우 API Key가 유출됩니다.
```ts
// example.ts
export async function getData() {
  const res = await fetch('https://external-service.com/data', {
    headers: {
      authorization: process.env.API_KEY,
    },
  })
 
  return res.json()
}
```
[반드시 서버에서만 실행 될 수 있도록 server only 패키지를 이용합니다.](https://nextjs.org/docs/getting-started/react-essentials#the-server-only-package)

```ts
// example.ts
import 'server-only'
```
이후 클라이언트에서 `getData` 함수를 실행하면 빌드 과정에서 에러가 발생합니다.
_(Optional) 반대의 개념인 client-only 패키지도 있습니다._


## Data Fetching
될 수있는한 서버와 통신하는 작업은 서버컴포넌트를 사용하세요.
다음과 같은 장점이 있습니다.
- 보안 향상
- 높은 성능과 유저 경험

## 3자 패키지 사용시
서버 컴포넌트 개념이 도입되지 않은 3자 패키지는, 클라이언트 환경 앱에서만 동작 할 수 있습니다.
만약 동작하지 않는다면, `use client` 디렉티브로 클라이언트 환경 렌더링을 보장하세요.
```ts
import { Carousel } from 'acme-carousel'
 
export default function Page() {
  return (
    <div>
      <p>View pictures</p>
 
      {/* 예시 에러: `useState` can not be used within Server Components */}
      <Carousel />
    </div>
  )
}
```

## Context
중앙 데이터 관리의 방법으로 Context를 많이 사용하지만, 서버 컴포넌트에서는 사용이 제한됩니다.   
- Context는 컴포넌트 변경이 발생 할 경우 재 렌더링을 하는 구조입니다.
- 3자 패키지(only `use client`)를 Context로 사용 할 경우 Provider 되는 부모 엘리먼트는 `use client` 디렉티브를 사용해야합니다. 

## 더 읽어보기
- [서버컴포넌트와 Provider 사용하기](https://nextjs.org/docs/getting-started/react-essentials#rendering-third-party-context-providers-in-server-components)
- [서버컴포넌트간 데이터 공유하기](https://nextjs.org/docs/getting-started/react-essentials#rendering-third-party-context-providers-in-server-components)
