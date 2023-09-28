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
