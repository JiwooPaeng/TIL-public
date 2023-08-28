23.08.28(월)
# preventDefault()와 stopPropagation()의 차이

event 인터페이스의 메서드

<br>

## event.preventDefault()
[mdn](https://developer.mozilla.org/ko/docs/Web/API/Event/preventDefault)
- 특정 태그의 이벤트에 대한 동작을 막는 메서드
- 이벤트 흐름의 어떤 단계에서라도 preventDefault()를 호출하면 이벤트가 취소된다

<br>

## event.stopPropagation() 
[mdn](https://developer.mozilla.org/ko/docs/Web/API/Event/stopPropagation)
- 상위 엘리먼트로의 이벤트 전파(이벤트 버블링)를 막기 위한 메서드