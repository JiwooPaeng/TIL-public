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

<br>
<hr>
<br>

**23.09.08(금)**
# VIEW
하나 이상의 기본 테이블이나 다른 뷰를 이용하여 생성되는 가상 테이블<br>
- 뷰에서는 데이터 딕셔너리 테이블에 뷰에 대한 SQL문만 저장되어 디스크 저장공간 할당이 이루어지지 않음
- 테이블 구조가 변경되어도 뷰를 사용하는 응용 프로그램은 변경하지 않아도 된다.
```SQL
CREATE VIEW my_view AS
SELECT column1, column2, ...
FROM my_table
WHERE condition;
```

<br>
<hr>
<br>

**23.09.09(토)**
# Hoisting
**자바스크립트 호이스팅** <br>
인터프리터가 코드를 실행하기 전에 js 엔진이 함수, 변수, 클래스 또는 임포트의 선언문을 해당 범위의 맨위로 이동시킨 것<br>

#### 💡함수만 지역변수 호이스팅, if문 while문 등등 전역변수 호이스팅

<br>

- 선언되지 않은 변수에 접근을 시도하는 경우 ReferenceError(not defined) 예외가 발생하지만, **var**를 사용해 접근 시도 이후 변수 선언되어있는 경우에는 undefined (변수 선언과 변수 초기화(undefined) 이루어짐). 

- let으로 개선 : 호이스팅을 하지만 선언되기 이전까지를 **temporal dead zone**으로 두고, 변수의 사용을 제한