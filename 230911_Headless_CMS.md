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