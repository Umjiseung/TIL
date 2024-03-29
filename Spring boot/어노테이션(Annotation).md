# Annotation
## Annotation이란

* 사전적 의미로는 `주석`이라는 뜻

* 자바에서 `Annotation`은 코드 사이에 주석처럼 쓰이며 특별한 의미, 기능을 수행하는 기술

* 즉, 프로그램에게 추가적인 정보를 제공하는 메타데이터라고 볼 수 있다.
---
## Annotation의 용도

* 컴파일러에게 코드 작성 문법 에러를 체크하도록 정보를 제공한다.

* 소프트웨어 개발 툴이 빌드나 배치시 코드를 자동으로 생성할 수 있도록 정보를 제공한다.

* 실행시 특정 기능을 실행하도록 정보를 제공한다.
---
## Annotation 사용 순서

1. 어노테이션을 정의한다.

2. 클래스에 어노테이션을 배치한다.

3. 코드가 실행되는 중에 Reflection을 이용하여 추가 정보를 획등하여 기능을 실시한다.
---
# Reflection
## Reflection이란

* 프로그램이 실행 중에 자신의 구조와 동작을 검사하고, 조사하고, 수정하는 것

* 프로그래머가 데이터를 보여주고, 다른 포맷의 데이터를 처리하고, 통신을 위해 serialization(직렬화)를 수행하고, bundling을 하기 위해 일반 소프트웨어 라이브러리를 만들도록 도와준다.

* Java와 같은 객체 지향 프로그래밍 언어에서 Reflection을 사용해 멤버 접근 가능성 규칙을 무시할 수 있다.

* Spring에서 BeanFactory라는 컨테이너에서 객체가 호출하면 객체의 인스턴스를 생성하게 되는데 이 때 필요하게 된다.

* Reflection을 이용하면 Annotation 지정만으로도 원하는 클래스를 주입할 수 있다.