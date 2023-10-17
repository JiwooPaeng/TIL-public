**23.10.16(월))**
# Dependencies in javaScript
## javaScript package
# npm
## package.json
- 프로젝트가 의존하고 있는 패키지 목록
- 빌드를 언제든 다시 할 수 있게 해 다른 개발자들의 공유를 쉽게 함

## 프로젝트가 가질 수 있는 다양한 종속성 타입
- dependencies: 프로젝트 코드를 호출하는데 있어 필수적으로 의존하고 있는 종속성
- devDependencies: 개발단계에서 필요한 종속성
- peerDependencies: 패키지를 설치하는 다른 개발자들에게 종속성 버전 알림
- optionalDependencies: 옵션 성격의 종속성, 이 종속성을 설치하는데 실패해도 문제 X
- bundleDependencies: 패키지 번들링 시 함께 들어가게 되는 의존성. npm에 있지 않은 제 3의 라이브러리 유용

## package-lock.json
**package.json**이나 **node_modules** 디렉토리가 변할 때 마다 자동으로 생성
- 후속 설치 시에도 동일한 의존성 트리를 생성할 수 있도록 함

## npm ci
package.json에는 명확하게 지정된 버전이 아닌 **시멘틱 버전**으로 작성<br>
-> package.json이 아닌 package-lock.json에 명시된 버전의 변경 없이 설치 수행하는 명령어<br>

- 참고: [자바스크립트 의존성 지옥](https://yceffort.kr/2020/11/javascript-dependency-hell)

<hr>
<br>

**23.10.17(화)**
# 활용 도구 선택시 고려할 사항

- [시멘틱 버저닝](https://jake-seo-dev.tistory.com/283)
- [DI(의존성 주입)](https://velog.io/@moongq/Dependency-Injection)



