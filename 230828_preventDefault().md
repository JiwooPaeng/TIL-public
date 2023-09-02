**23.08.28(월)**
# preventDefault()와 stopPropagation()의 차이

event 인터페이스의 메서드


## event.preventDefault()
[mdn](https://developer.mozilla.org/ko/docs/Web/API/Event/preventDefault)
- 특정 태그의 이벤트에 대한 동작을 막는 메서드
- 이벤트 흐름의 어떤 단계에서라도 preventDefault()를 호출하면 이벤트가 취소된다

<br>

## event.stopPropagation() 
[mdn](https://developer.mozilla.org/ko/docs/Web/API/Event/stopPropagation)
- 상위 엘리먼트로의 이벤트 전파(이벤트 버블링)를 막기 위한 메서드

<br>
<hr>
<br>

**23.08.29(화)**
# SEO
### 검색 엔진 최적화 (Search Engine Optimization)

검색 시, 검색 결과 상위에 노출 될 수 있도록 내 콘텐츠를 최적화하는 작업

## Meta Tag
브라우저 탭에 노출되는 제목이며, 웹페이지를 검색 엔진에 검색했을 때 노출되는 제목

### <title> 태그
title 태그로 메타태그 정의
```html
<title>Google</title>
```

### <description> 태그
```html
<meta content="최대한 반복이 없는 키워드로 작성하는 것이 좋음" name="description">
```

### <robots> 태그
웹페이지별 검색 로봇 접근 여부 설정 (크롤링 권한 설정)
```html
<meta content="noodp" name="robots">
```

## Open Graph 태그
링크 공유 시 웹페이지가 어떻게 노출될지 정의<br>
검색 상위 노출을 위한 품질 평가에도 영향<br>

- og:title : 제목
- og:description : 상세 설명
- og:image : 웹페이지 카드에 나타나는 썸네일 (1200x630)
- og:type : 유형 (e.g. website)
- og:url : 웹페이지 주소

<br>
<hr>
<br>

**23.08.30(수)**
# Monolithic Architecture와 MSA
## Monolithic Architecture
프로젝트를 하나로 패키징하여 진행하고 배포하는 형태의 아키텍쳐
- 심플한 패키징
- 모든 모듈이 하나의 프로세스로 동작하기 때문에 부분적인 확장이 어렵다

## MSA
MicroService Architecture
**단일 책임 원칙, 하나의 서비스는 한 가지 일만 잘 처리하자!**
- 큰 문제들을 작은 문제로 분해
- 각각의 서비스는 독립적으로 배포가 가능해야며, 다른 서비스에 대한 의존성 최소화
- CI,CD 및 자동화된 테스트도 있어야 한다


<br>
<hr>
<br>

**23.09.01(금)**
# CSR과 SSR
## CSR 
Client Side Rendering<br>
렌더링이 클라이언트 쪽에서 일어남<br>
서버처리 없이 클라이언트로 html과 js가 전송되기에 js 실행까지 끝나기 전까지는 User는 어떤 화면도 볼 수 없다.<br>
1. User(클라이언트)가 Website(서버)에 요청을 전송
2. CDN이 html파일과 js로 접근할 수 있는 링크를 클라이언트로 전송
    - 엔드 유저의 요청에 물리적으로 가까운 서버에서 요청하는 응답방식
3. 클라이언트가 html과 js를 다운로드 (화면 그려져있지 x)
4. 다운이 완료된 js가 실행
5. 데이터 가져오기 위해 서버에 API 호출 (placeholder 표시)
6. 서버가 클라이언트가 보낸 API 요청에 응답
7. API 요청으로 받아온 데이터를 클라이언트의 placeholder 자리에 넣음
8. 페이지 렌더링 완료. 상호작용 가능한 상태.

<br>

## SSR
Server Side Rendering<br>
서버쪽에서 렌더링 준비를 끝마친 상태로 클라이언트에 전달<br>
서버에서 이미 렌더링 가능한 상태의 html을 클라이언트에 전달하기에, js가 다운로드 되는 동안 User는 무언가를 보고 있을 수 있다<br>
1. User(클라이언트)가 Website(서버)에 요청을 전송
2. 서버는 요청을 받아 즉시 렌더링 가능한 html파일 생성
    - 리소스 체크, 컴파일 후 완성된 html 컨텐츠 생성
3. 서버로부터 html이 클라이언트에 전송되면, 이미 렌더링 준비가 되어있는 html은 즉시 렌더링
    - 그러나 js가 파싱되기 전이므로 사이트 조작은 불가능
4. 클라이언트가 js를 다운받음
    - 다운받아지고 있는 사이에 유저가 컨텐츠는 볼 수 있으나 조작은 불가능
    - 이때 사용자 조작을 기억함
5. js 다운 완료 후, 브라우저가 js 프레임워크를 실행
6. js까지 성공적으로 컴파일 되었기 때문에, 기억하고 있던 사용자 조작이 실행되고 상호작용 가능해짐<br>

<br>

## SEO 대응의 차이
검색 엔진은 자동화된 로봇인 **크롤러**로 웨 사이트들을 읽음<br>
- CSR은 js를 실행시켜 동적으로 콘텐츠를 생성하기에 js가 생성되어야 metadata가 바뀐다<br>
    - SEO 최적화가 필수
- SSR은 애초에 서버 사이드에서 컴파일 완료되어 클라이언트로 넘어오기에 크롤러 대응이 용이

<br>
<hr>
<br>

**23.09.02(토)**
# TypeScript interface
Typescript에서 객체를 선언할 때 사용 : interface와 type alias<br>
## 사용법
```js
interface Point {
	x: number;
	y: number;
}

function printPoint(point: Point) {
	console.log(`x 좌표는 ${point.x}입니다`)
	console.log(`y 좌표는 ${point.y}입니다`)
	console.log(`z 좌표는 ${point.z}입니다.`)
}

interface Point {
	z: number;
}
// 인터페이스 확장 가능

printPoint({ x: 100, y: 100, z: 200 })
``` 
## 상속
**extends**를 활용하면 interface간 상속 가능
```js
interface User {
    user_name: string,
    age: number,
}

interface MyCar extends User{
    car_name:string,
    color: string,
    start: () => void,
    stop: () => void,
}
// User를 상속받은 MyCar 객체를 활용 가능
```
