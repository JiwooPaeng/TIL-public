**23.09.11(월)**
# Headless CMS
Content Management System
frontend 없이 backend만 가지고 있는 파일 저장소 시스템
  - head에 해당하는 front-end를 자유롭게 구성할 수 있음

ex) WordPress, Strapi, [Sanity](https://www.sanity.io/docs)
## Sanity
- Content Lake <- Sanity Studio를 통해 접근 가능

<br>
<hr>
<br>

**23.09.12(화)**
# Edge functions
*CDN은 정적인 contents만 캐싱이 가능했음* <br>
**Edge Server** : 사용자와 가장 가까이에 있는 CDN <br>
## 특징
- small-size
- stateless
- short-lived
## 활용
- HTML 페이지 실시간 생성 (SSR)
- 사용자 인증 및 유효성 검사
- 사용자 위치별 비즈니스 로직 실행
## 장점
- 사용자와 가까운 곳에서 코드 실행
- 실 서버까지 왕복 통신 하지 않음
- 일정하고 짧은 반응 시간
- **Next.js에서는 런타임 환경을 페이지, API route 별로 설정할 수 있다**

**Livin' on the edge**
*The beauty of the edge is that is taking the best part of CDNs (being close to users) and the best part of serverless(running functions) and marrying them together*
- 참고 : [The Future of the Web is on the Edge(Deno)](https://deno.com/blog/the-future-of-web-is-on-the-edge)
- **CDN**의 장점과 **Serverless**의 장점을 잘 조합

## 한계점
- cold start를 줄이기 위해 런타임 환경이 제한되어있음
- DB에 의존적인 서비스에는 적합하지 않음 (함수 자체는 가까이에 있을지라도 데이터베이스는 여전히 멀다) 
  - 분산형 데이터베이스(e.g. Mongo DB Atlas 등으로 해결 가능)

<br>
<hr>
<br>

**23.09.13(수)**
# 쿠키, 세션, 토큰
웹 환경에서 반복적으로 사용되는 데이터나 정보를 종류와 특성에 맞게 저장하고 재활용하기 위해 사용하는 방식들

## 쿠키
크롬이나 사파리 같은 **브라우저에 저장되는 작은 텍스트 조각**을 브라우저에 저장해 웹사이트 이용을 편리하게 해줌<br>
- 쿠키는 당사자뿐만 아니라 제 3자가 조회하는 것도 가능하기 때문에 개인 정보를 담은 내용이나 보안상 민감한 정보 저장 X

## 세션
### 로그인 여부 등 사용자와 서버의 관계가 기억되어 보존되고 있는 상태
e.g.) 사용자가 사이트에 한 번 로그인하면 유효기간이 끝날 때까지 더 이상 아이디와 비밀번호를 입력하지 않아도 되도록, 이미 사용자가 서버로부터 인증받았음을 증명해주는 증서
  - 서버가 **세션 아이디**를 사용자에게 전달하고, 메모리에 아이디 사본을 어떤 사용자의 것인지 적어서 보관
  - 사용자는 서버로 받은 세션 아이디를 쿠키로 저장 -> 요청을 보낼시에 쿠키 헤더에 담아 함께 전달하여 인증
  - 서버는 요청시마다 세션 아이디 확인해서 요청 응답 보냄

### 한계
- 세션 아이디를 담아두는 메모리 공간이 부족해지면 서버 부하(저장된 메모리를 찾는데 시간이 오래 걸림)가 걸릴 수 있음

## 토큰
### 해당 서버만이 만들 수 있는 토큰을 발급함으로써 상태를 저장하지 않고도 사용자의 로그인 여부를 파악할 수 있도록 함
- 세션 아이디를 메모리에 올려둘 필요가 없으므로 서버 부하 줄일 수 있음

### 한계
- 한 번 발행한 토큰은 유효기간이 끝나기 전까지 따로 통제 불가능하기 때문에 세션에 비해 토큰 탈취의 가능성이 높음

<br>
<hr>
<br>

**23.09.15(금)**
# Fetch vs Axios
백엔드 또는 서드파티 API에 네트워크 요청을 보낼때 사용하는 HTTP 클라이언트<br>
- 모두 promise 기반의 HTTP 클라이언트

## Fetch API
- 모던 브라우저에 내장되어 있어 따로 설치할 필요 없음

```js

fetch(url, {
  method: "GET", // (POST, PUT, DELETE, etc.)
  headers: {
    "Content-Type": "application/json", // 명시해야함
  },
  body: JSON.stringify({}), // 객체를 변환한 뒤 body에 할당
}).then((res) => res.json()).then(console.log)
.catch((err) => console.log(err.message))

```
- fetch()는 .then() 메서드에서 처리된 promise를 반환하기 때문에, JSON 데이터로 변환하기 위해 `.json()`메서드를 호출

```js

fetch(url)
  .then((response) => {
    if (!response.ok) {
      throw new Error(
        `This is an HTTP error: The status is ${response.status}`
      );
    } // response.ok의 상태가 false인 경우 .catch 블록에서 처리되도록 커스텀
    return response.json();
  })
  .then(console.log)
  .catch((err) => {
    console.log(err.message);
  });

```
- Fetch는 404에러 또는 다른 HTTP 에러 응답을 받았다고 해서 promise를 곧장 reㅓect하지 않음 (네트워크 장애가 발생한 경우에만 promise를 거부)
- 따라서 수동으로 HTTP 에러를 처리

### TimeOut 설정
```js

const controller = new AbortController();
const signal = controller.signal;
setTimeout(() => controller.abort(), 4000);

fetch(url, {
  signal: signal,
})
  .then((response) => response.json())
  .then(console.log)
  .catch((err) => {
    console.error(err.message);
  });
```
- abort 메서드가 호출될 때 마다 fetch 요청이 종료됨


## Axios
- 별도로 프로젝트에 추가하여 브라우저 또는 node.js 환경에서 사용 가능

```js

axios({
  timeout: 4000, // 기본 설정은 '0'입니다 (타임아웃 없음)
  method: "get",
  url: url,
  headers: {},
  data: {},
}).then((res) => console.log(res.data))
.catch((err) => {
// 에러 처리 (promise의 상태코드가 2xx의 범위를 넘어간 경우)
if (err.response) {
// 요청이 이루어졌고 서버가 응답했을 경우

    const { status, config } = err.response;

    if (status === 404) {
      console.log(`${config.url} not found`);
    }
    if (status === 500) {
      console.log("Server error");
    }

  } else if (err.request) {
    // 요청이 이루어졌으나 서버에서 응답이 없었을 경우
    console.log("Error", err.message);
  } else {
    // 그 외 다른 에러
    console.log("Error", err.message);
  }
});

```
- axios response 데이터 타입은 기본적으로 JSON

<br>
<hr>
<br>

**23.09.16(토)**
# lambda
python 함수 표현식

```py
lambda 매개변수 : 표현식
```

<br>
사용예시

## map()
```py

list(map(lambda x: x ** 2, range(5))) 
# [0, 1, 4, 9, 16]

```

## reduce()
시퀀스(문자열, 리스트, 튜플)의 원소들을 누적적으로 함수에 적용

```py

from functools import reduce
reduce(lambda x, y: x + y, [0, 1, 2, 3, 4])
# 10

```

## filter()

```py

list(filter(lambda x: x < 5, range(10)))
[0, 1, 2, 3, 4]

```

<br>
<hr>
<br>

**23.09.17(일)**
손으로 10초면 충분히 할 수 있는 일을 컴퓨터로 하루 종일 프로그래밍해서 자동으로 수행할 때, 나는 더할 나위 없이 큰 행복을 느낀다.
-Douglas Noel Adams