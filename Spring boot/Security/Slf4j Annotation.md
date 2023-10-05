# @Slf4j
## @Slf4j란

* Simple Logging Facade for Java

* 추상 로깅 프레임워크

* 로깅에 대한 추사 레이어를 제공하는 인터페이스이다.

* 로깅을 구현하게 되면 좋은 점은 추후에 필요로 의해 로깅 라이브러리를 변경할 때 코드의 변경 없이 가능하다.

## 동작과정

* 개발할 때, SLF4J API를 사용해 로깅 코드 작성한다.

* 배포할 떄, 바인딩된 Logging Framework가 실제 로깅 코드를 수행한다.

### 모듈

1. Slf4j Bridging Modules

2. Slf4j API(인터페이스)

3. Slf4j Binding(.jar)