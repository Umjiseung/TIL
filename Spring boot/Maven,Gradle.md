# Maven
## Maven이란

* 아파치 메이븐은 자바용 프로젝트 관리 도구

* 아파치 Ant의 대안으로 만들어졌다.

* 아파치 라이센스로 배포되는 오픈 소스 소프트웨어

### 특징

* 그 라이브러리들과 연관된 라이브러리들까지 거미줄처럼 모두 연동되어 관리가 된다.

* 네트워크를 통해 연관된 라이브러리까지 같이 업데이트 해주기 떄문에 사용이 편하다.

## POM(Project Object Model)

* Maven을 사용하기 위해 POM이 사용된다.

### pom.xml이 다루는 기능

* 프로젝트 정보: 프로젝트 이름, 라이센스..

* 빌드 설정: 소스, 리소스..

* 빌드 환경: 사용자 환경 별로 달라질 수 있는 프로파일 정보

* pom 연관 정보: 의존 프로젝트(모듈), 상위 프로젝트, 포함하는 하위 모듈..

---
# Gradle
## Gradle이란

* 빌드, 프로젝트 구성/관리, 테스트, 배포 도구

* 안드 앱의 공식 빌드 시스템

* 빌드 속도가 Maven에 비해 10~100배 빠름

* Java, c/c++ Python 등을 지원

* 빌드툴인 Ant Builder와 Groovy 스크립트 기반으로 만들어져 기존 Ant의 역할과 배포 스크립트의 기능을 모두 사용 가능

* 기존 메이븐의 경우 XML로 라이브러리를 정의하고 사용했으나 Gradle의 경우 별도의 빌드 스크립트를 통하여 사용할 어플리케이션 버전, 라이브러리 등의 항목을 설정할 수 있다.
### Groovy란

* Java 가상 머신에서 실행되는 스크립트 언어

* Java 가상 머신에서 동작하지만 Java와는 달리 소스 코드를 컴파일 할 필요는 없다..

* 스크립트 언어이고, 소스 코드를 그대로 실행한다.

## Gradle VS Maven

* 스크립트의 길이와 가독성 면에서도 gradle이 우세하다.

* 빌드 실행 결과도 gradle이 더 빠르다.

* 의존성이 늘어날 수록 성능과 스크립트 품질의 차이가 심해진다.