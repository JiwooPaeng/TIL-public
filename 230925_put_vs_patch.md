**23.09.25(월)**
# PUT vs PATCH
`PUT`과 `PATCH` 메서드는 모두 기존의 데이터에 대한 업데이트를 실시

## PUT
페이로드를 사용해 **새로운 리소스를 생성**하거나, 대상 리소스 **데이터를 대체**하는 메서드
- 멱등성 메서드

## PATCH
리소스의 부분적인 수정을 할 때 사용하는 메서드
- 요청한 URI에 자원이 존재하지 않으면, 새롭게 자원을 생성하지 않음
- 비멱등성 메서드

## 멱등성
동일한 요청을 한 번 보내는 것과 여러번 연속으로 보내는 것이 같은 효과를 지니고, 서버의 상태도 동일하게 남는 경우

-참고: [멱등성[MDN]](https://developer.mozilla.org/ko/docs/Glossary/Idempotent)

<br>
<hr>
<br>

**23.09.28(목)**
# HTTP multipart/form-data
- 웹 브라우저가 보내는 HTTP 메시지는 Content-Type 속성이 **multipart/form-data**로 지정되고 정해진 형식에 따라 메시지를 인코딩하여 전송한다.
    - Message Body에 들어가는 데이터 타입을 HTTP Header에 **Content-type** 필드로 명시해 줄 수 있다.
    - **multipart/form-data**로 명시하면 여러종류의 데이터타입을 한번에 보낼수있다. 이 경우 모든 문자를 인코딩하지 않는다.
- 서버는 multipart 메세지에 대해 각 파트별로 분리하여 개별파일의 정보를 얻게 된다.

<br>
<hr>
<br>

**23.10.01(일)**
# 웹 서버
웹 브라우저와 같은 클라이언트로부터 HTTP 요청을 받아들이고, HTML 문서와 같은 웹 페이지를 반환하는 컴퓨터 프로그램<br>
- **하드웨어 측면**에서, 웹사이트의 컴포넌트 파일(HTML 문서, 이미지, CSS, js파일 등)을 저장하는 컴퓨터로 인터넷에 연결되어 웹에 연결된 다른 기기들이 웹서버 데이터를 주고받을 수 있도록 함
- **소프트웨어 측면**에서, 웹 사용자가 호스트 파일들에 어떻게 접근하는지 관리<br>
ex) HTTP 서버의 경우 URL(Web address)과 HTTP(브라우저가 웹 페이지를 보여주기 위해 사용하는 프로토콜)의 소프트 웨어 일부

- 참고: [웹 서버란 무엇일까?](https://developer.mozilla.org/ko/docs/Learn/Common_questions/Web_mechanics/What_is_a_web_server)