**23.09.04(월)**
# 랜딩 페이지
방문자가 유입되어 보는 첫 페이지 <br>
랜딩페이지는 한가지 목적(DB수집, 소개 등)을 가진 페이지로, 한가지 목적을 가진 CTA 버튼만이 존재<br>
## 랜딩 페이지의 필요 요소
a. 상단 50%에 가장 중요한 내용을 모두 넣기 <br>
b. CTA로 방문자가 행동 일으키게 만들기<br>
c. 보상 제시<br>
d. 사회적 증거 제시<br>
e. 관계 형성<br>

참고 : [랜딩페이지 가장 쉽게 이해하기 + 완벽 가이드(유료 전자책급 노하우) 2022년 버전](https://tnart.me/%EB%9E%9C%EB%94%A9%ED%8E%98%EC%9D%B4%EC%A7%80-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%99%84%EB%B2%BD-%EA%B0%80%EC%9D%B4%EB%93%9C/)

<br>
<hr>
<br>

**23.09.05(화)**
# Hydrate
Next.js<br>
Server Side 단에서 Pre-Rendering 된 정적 페이지(HTML document)와 번들링된 js파일을 클라이언트에 보낸 뒤, 클라이언트단에서 HTML 코드와 JS코드를 서로 매칭시키는 과정<br>
  - Next.js 서버에서는 Pre-Rendering된 웹 페이지를 클라이언트에 보내고 나서, 곧이어 리액트가 번들링된 js 코드들을 클라이언트에 전송

<br>
<hr>
<br>

**23.09.06(수)**
# CDN
콘텐츠 전송 네트워크(Content Delivery Network)<br>

### 목적
인터넷의 글로벌 한 특성으로 인해 아주 먼 물리적 거리를 이동해야하는 서버와 클라이언트간의 통신 트래픽 전송 대기 시간과 통신 지연을 줄이는 것

- 따라서, **지리적으로 사용자와 가까운** CDN 서버에서 컴퓨터에 빨리 도달되도록 함
- 클라이언트와 웹 사이트 서버간 **중간 서버**를 두어 효율성 높임
  - 이와같은 CDN 서버가 클라이언트-서버 통신의 일부 관리 
<br>

참고: [CDN이란 무엇입니까?](https://aws.amazon.com/ko/what-is/cdn/)

<br>
<hr>
<br>

**23.09.07(목)**
# App Router - Params
App Router의 params와 searchParams를 활용해 편리한 라우팅 가능
```js
type Props = {
  params: {
    id: string,
  }
  searchParams: {
    [key: string]: string | string[] | undefined 
  }
}

export default function Page({ params, searchParams, }: Props) {
  return (
    <div>
      <h1>{params.id}</h1>
      <h2>{searchParams.a}</h2>
    </div>
  )
}
```
- http://URL/{params.id}?a={searchParams.a} 로 이동가능

- 참고: [Next.js-App Router-File Conventions-page.js]([https://aws.amazon.com/ko/what-is/cdn/](https://nextjs.org/docs/app/api-reference/file-conventions/page#searchparams-optional)https://nextjs.org/docs/app/api-reference/file-conventions/page#searchparams-optional)
