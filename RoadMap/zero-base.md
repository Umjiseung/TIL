
# Zero-Base 백엔드 로드맵 정리

#
## Part 1. Computer Science, 컴퓨터 공학 기초
#

> 성장에 필요한 기초 Computer Science이다. 컴퓨터 공학 기초 중에서도 기술 블로그 관리 등을 통해 스스로 학습뿐 아니라, 이력서로 삼을 수 있는 수단 위주로 선별했다.

> 또한 취업에 필요한 자료구조, 알고리즘 또한 꾸준히 학습해야 한다.

### 기본
```
1. Process 와 Thread

2. Memory
```
### 중요
```
1. CPU Scheduling 

2. Synchronize(동기화)와 Deadlock

3. Security

4. 자료구조 / 알고리즘
```
# 
## Part 2. Java 
#

``` 
''주력 언어는 생각보다 더 중요하다''
```

> 전 세계에서 전부 자바가 가장 Major 하다고는 말할 수 없다.

> 다만 국내에서는 자바가 가장 Major한 언어라는 것은 맞다.

> 네카라쿠배, 유니콘 회사들의 채용공고를 한번 쓱 흝어 보면 어떤 언어를 채용하는 포지션이 많은지보면 자바가 거의 많은 지분을 차지하고 있다.

### 기본
```
1. 변수

2. 연산자

3. 조건 & 반복문

4. 배열

5. 객체지향 프로그래밍 I(오버로딩, 오버라이딩까지)

6. Exception Handing 

7. Java 자료 구조 Collection

8. 객체지향 프로그래밍 II

9. Generic, Enum

10. Lamda & Stream

11. IO 입출력
```
### 중요
```
1. Java와 JVM의 기초

2. Thread

3. Annotation

4. Network(네트워크, 소켓프로그래밍)

5. JVM 고급

6. 주요 디자인 패턴(MVC,싱글톤 필수, 어댑터 등)
```
#
## Part 3. DataBase
#

> Database에 대한 기술 스택은 개발자 사이에서 프로그래밍 언어 코딩 실력보다 편차가 큰 분야이다.

> 진입 장벽이 높지 않고 개발자라면 기본적으로 DB를 어느정도는 다루기 떄문에 자칫 코딩보다 덜 중요한 분야로 생각하는 경향이 있다.

> 기술 스택을 쌓는 것에 비해 투자하는 시간을 현저히 줄이는 경향이 있다.

> 대부분의 웹 서버 정보들은 데이터 베이스에서 관리, 보관을 하게 된다.

> 정보가 어떤 DB로 들어가고, DB를 뽑아오고, 뽑아올 때 어떤 필터를 걸치는지를 이해할 수 있어야 한다.

### 기본
```
1. Database 이론

2. Data CRUD

3. Data Relation(Join, 조건문, Dynamic Query 나누어서 사용)

4. Table

5. View

6. CUI 기반의 실습(Pure Java CRUD)
```
### 선택
```
1. 설치

2. 샘플로로 보는 DB의 활용

3. Procedure
```
### 중요
```
1. index
```
#
## Part 4. Git
#

### 기본
```
1. Git이란?

2. 가입 및 주요 기능 소개

3. Branch, PR, Merge, 커밋 메세지

4. Git 고급(Cherry pick, rebase 등)
```
#
## Part 5. Spring( Spring Boot MVC )
#

> Spring은 많은 회사가 선택한 것이고 자바라는 언어를 선택했다는 것은, 국내에서는 특수한 상활이 아닌 이상, Spring 기반의 개발을 진행하게 된다.

> Spring만큼 Enterprise 환경에서 안정적인 운영 환경을 기본적으로 제공하는 프레임워크는 없다고 생각한다.

> 옛날에는 Spring이 생산성에서 떨어지는 측면이 있어서, Django, Node.js 같은 웹 프레임워크들이 각광을 받았지만 지금은 SpringBoot가 자리를 잡으면서 문제가 많이 극복했다고 생각한다.

> SpringBoot를 활용하면 간단한 Implementation 몇개만으로 서버를 간단하게 만들 수 있다.

> Rest API 기반의 웹 개발은 반드시 알고 넘어가야되고 대다수의 회사가 Rest API기반의 웹 개발을 하고있다.

> 서서히 소멸해 가고 있는 JSP와 같은 부분을 최소화 하고 Spring, Mysql, JPA, Security등을 중심으로 학습해가는 것을 추천한다.

### 중요
```
1. Spring이란(AOP, IDC, DI 등 포함)

2. 웹 개발과 Rest API

3. 트랜잭션

4. Test code
```
### 기본
```
1. Spring Boot

2. CURD API 만들어보기(with lombok)

3. Mybatis(Datbase 연동, 리팩토링)

4. Exception Handling

4. 외부 API 연동(Rest template, Feign)

5. Logging
```
#
## Part 6-7. JPA, Security
#

### JPA

> 과거에는 대부분 Mtbatis를 사용했었지만 ORM이 니오고 최근에는 JPA가 대표적이다.

> 기존 SQL을 직접 작성해서 Database 와 연동한 것에 비해, ORM은 객체를 기반으로 DB의 Table을 매핑했기 떄문에, 좀 더 프로그래밍 친화적이라고 할 수 있고 재사용성이나, 유지 보수 같은 측면에서도 이득이다.

> JPA의 경우 진입장벽이 높고 객체를 기반으로 Table을 handling하다 보니 SQL이 실제로 어떻게 만들어지는 지도 알아야 하고, 당연하게도 Database와 실제 처리하는 SQL에 대해 잘 알아야 JPA를 어떻게 활용하는 지 알 수 있다.
```
1. ORM 소개(기존 방식과의 차이)

2. 영속성 관리(JPA의 동작원리)

3. Entity

4. Entity의 Relation

5. Proxy

6. JPQL
```
### Security, Spring Cloud Gateway

> 개발자도 보안에 대해 잘 알아야하고 대중적으로 많이 사용하는 JWT에 대해 다루고, 이를 기반으로 한 OAuth2를 통해 인증을 득하고, 세션을 관리할 수 있는 것은 꽤 우아한 방식이다.

> 물론, 필수는 아니지만, 그 안정성을 많은 이들에게 인정받고, 대중적으로 잘 사용하고 있는 기술들이다.  
```
1. OAuth2

2. JWT

3. Cluster 이론

4. MSA(Micro Service Architecture)

5. Feign

6. 실습
```