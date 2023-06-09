#
# SOLID

## SOLID 5원칙
1. SRP(Single responsibility principle): 단일 책임 원칙
2. OCP(Open-closed principle) : 개방-폐쇄 원칙
3. LSP(Liskov substitution principle) : 리스코프 치환 원칙
4. ISP(Interface segregation principle) : 인터페이스 분리 원칙
5. DIP(Dependency inversion principle) : 의존관계 역전 원칙

## SRP - 단일 책임 원칙
* 모든 클래스는 각각 하나의 책임만을 가져야 하며, 수정할 이유는 단 한 가지여야 한다.

* 즉, 클래스는 그 책임을 완전히 캡슐화해야 함을 말한다.

## OCP - 개방-폐쇄 원칙
* 소프트웨어의 구성요소(컴포넌트, 클래스, 모듈, 함수)는 확장에는 열려 있어야 하지만 변경에는 폐쇄적이어야 함을 의미한다.

즉, 기존의 코드를 변경하지 않으면서, 기능을 추가할 수 있도록 설계가 되는 원칙을 말한다.

### 중요 메커니즘
1. 추상화
2. 다형성

## LSP - 리스코프 치환 원칙

* 상위 타입은 항상 하위 타입으로 대체될 수 있어야 함을 의미한다.

* 즉, 부모 클래스가 들어갈 자리에 자식 클래스를 넣어도 역할을 하는데 문제가 없어야 한다는 의미다.

## ISP - 인터페이스 분리 원칙
* 각 역할에 맞게 인터페이스를 분리하는 것이다.
* 인터페이스 내에 메소드는 최소한 일수록 좋다.
* 가능한 최소한의 인터페이스를 사용하도록 하여 단일 책임을 강조한다.
* 일반적으로 ISP보다 SRP 할 것을 권장한다.

## DIP - 의존관계 역전 원칙
* 의존 관계를 맺을 때 변화하기 쉬운 것 또는 자주 변화하는 것보다는 변화하기 어려운 것, 거의 변화가 없는 것에 의존하라는 것이다.

* 즉, 구체적인 클래스보다 상위 클래스, 인터페이스, 추상 클래스와 같이 변하지 않을 가능성이 높은 클래스와 관계를 맺는 것이다.

### 정리
* DIP 원칙을 따르는 가장 인기 있는 방법은 의존성 주입(DI; Dependency Injection)을 활용하는 것이다.