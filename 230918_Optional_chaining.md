**23.09.18(월)**
# 옵셔널 체이닝(Optional chaining)
```js
.?
```
각 참조가 유효한지 명시적으로 검증하지 않고, 연결된 객체 체인 내에 위치한 속성 값을 에러없이 읽을 수 있음
- 체이닝(.)과 동일한 기능

<br>
<hr>
<br>

**23.09.19(화)**
# !!

```js

const isTrue = !!"string"
//true

```
다른 타입의 데이터를 boolean 타입으로 명시적으로 변환해주기 위해 사용

<br>
<hr>
<br>

**23.09.20(수)**
# z-index
CSS에서 위치 지정 요소(position absolute, fixed 등)의 박스에 대해, 그 자손 또는 하위 플렉스 아이템의 Z축 순서를 지정
- z-index: auto 보다 z-index: 6이 더 상위에 위치 (더 큰 값을 가질수록 위)

- 참고: [z-index](https://developer.mozilla.org/ko/docs/Web/CSS/z-index)

<br>
<hr>
<br>

**23.09.21(목)**
# Pre-Rendering
각 페이지에 대한 html을 미리 생성하는 Next.js의 페이지 렌더링 방식
- 최초 Load 되었을 때, js동작이 html을 먼저 화면에 보여줌
- hydration이 이루어지면 인터렉티브한 화면이 완성!

### 프로젝트 회고
*Next.js를 사용하면 렌더링 방식을 관리할 수도 있어서*
*프로젝트가 더 안정적이게 느껴질 줄 알았는데 아직 익숙치 않아서 그런가 새로 업데이트된 버전을 사용해서 그런가...*
*뭔가 더 불안하고 덜 안정적이게 느껴진다...*
*그래도 오류를 해결하고 지속적으로 새로운 배움에 맞부딪히며 나아가다보면 조금씩이나마 더 나아지겠지...*<br>
**불안은 노력과 시간으로 극복하기**
**라이브러리 의존성 관리, 패키지 버전 관리 잘하기!!**

<br>
<hr>
<br>

**23.09.22(굼)**
# DTO
Data Transfer Object <br>
Spring에서 사용 <br>
계층간 데이터 전송을 위해 도메인 모델 대신 사용되는 순수한 데이터 객체(getter & setter)<br>
계층 간 데이터 교환을 위해 사용되는 객체

### 데이터 전송 계층
Presentation(View, Controller) → Business(Service) → Persistence(DAO, Repository) 등
- **DAO** (Data Access Object) : DB의 data에 접근하기 위한 객체 

1. 유저가 자신의 브라우저에서 데이터를 입력하여 form에 있는 데이터를 DTO에 넣어 전송
2. 해당 DTO를 받은 서버가 DAO를 이용하여 데이터베이스로 집어넣음