# Funtional Interface
## 함수형 인터페이스

* 1개의 추상 메소드를 갖는 인터페이스

* Java8부터 인터페이스는 기본 구현체를 포함한 디촐트 메서드를 포함할 수 있다.

* 여러 개의 디폴트 메서드가 있어도 추상 메서드가 오직 하나라면 함수형 인터페이스에 부합하다.

* 자바 람다 표현식은 함수형 인터페이스로만 사용 가능하다.

* 추상 메서드가 하나라는 말은 `default method`, `static method`는 여러 개 존재해도 상관없다는 말이다.

* `@FuntionalInterface` 어노테이션을 안 붙여도 함수형 인터페이스로 동작은 하지만, 저 어노테이션을 붙이면 검증과 유지보수가 가능하므로 되도록은 붙여주면 최고다.

### 예제
```java
@FunctionalInterface
interface CustomInterface<T> {
    // abstract method 오직 하나
    T myCall();

    // default method 는 존재해도 상관없음
    default void printDefault() {
        System.out.println("Hello Default");
    }

    // static method 는 존재해도 상관없음
    static void printStatic() {
        System.out.println("Hello Static");
    }
}
```
* 만약에 함수형 인터페이스에 형식이 맞지 않다면 
`Multiple non-overriding abstract methods found in interface com.practice.notepad.CustomFunctionalInterface`라는 에러를 띄워준다.

```java
CustomInterface<String> customInterface = () -> "Hello Custom";

// abstract method
String s = customInterface.myCall();
System.out.println(s);

// default method
customInterface.printDefault();

// static method
CustomFunctionalInterface.printStatic();
```

* 위 함수형 인터페이스를 사용하여 코드를 실행해보면 결과는 이렇게 나온다.
```
Hello Custom
Hello Default
Hello Static
```
