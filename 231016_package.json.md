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

<br>
<br>

**23.10.17(화)**
# SDK
**소프트웨어 개발 키트(SDK)**<br>
플랫폼별 구축 도구 세트, 소프트웨어를 개발하고 실행하는 데 필요한 모든 것을 한 곳에서 제공
- 디버거, 컴파일러, 라이브러리 등 포함
- 문서, 튜토리얼 및 가이드와 같은 리소스와 더 빠른 애플리케이션 개발을 위한 api 및 프레임워크가 포함

## 장점
1. 애플리케이션에 통합할 수 있는 사전 빌드된 구성 요소와 라이브러리를 제공하여 개발 효율성을 높임
2. 빠른 배포를 가능하게 함. SDK는 여러 플랫폼을 지원하는 경우가 많기 때문에 개발자는 여러 장치 또는 운영 체제에 빠르게 배포 가능.

## 활용
- 모바일 앱 개발
- 웹 개발
등등 다양한 분야에서 사용!

## SDK와 API의 차이점
- API: 애플리케이션이 서로 통신할 수 있도록 하는 일련의 프로그래밍 명령 / 두 애플리케이션 간의 통신 브리지
- SDK : 타사 도구를 개발자의 환경에 제공

- [시멘틱 버저닝](https://jake-seo-dev.tistory.com/283)
- [DI(의존성 주입)](https://velog.io/@moongq/Dependency-Injection)



