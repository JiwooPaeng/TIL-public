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


