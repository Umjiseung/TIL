# 스프링 빈(Bean)
## Bean이란
spring 컨테이너에 의해 관리되는 재사용 가능한 소프트웨어 컴포넌트

즉, 스프링 컨테이너가 관리하는 객체를 뜻하고, 하나 이상의 빈을 관리

new 연산자를 대신하여 객체를 생성할 수 있다고 알면 편함

### 예시
```xml
<bean id="helloService" class="com.example.myapp.di.HelloService"/>
```
```java
IHelloService helloService = new IHelloService()
```
IHelloService 라는 인터페이스가 존재하고 helloService 인스턴스를 만들기 위해 new 연산자를 사용하였다. 

위와 같은 new를 사용하지 않고 인스턴스를 만드는 방법은 빈태그를 사용하면 된다.

위처럼 xml 파일에 빈태그를 추가하면 helloService 인스턴스를 스프링 컨테이너가 관리하게 된다.

### 스프링 빈을 사용하는 이유
* 가장 큰 이유는 스프링 간 객체가 의존관계를 관리하기 위한 것이 가장 큰 목적이다.

* 객체가 의존관계를 등록할 때 스프링 컨테이너에서 해당한 빈을 찾고, 그 빈을 통해 의존성을 만든다.
---
## 스프링 빈 등록 방법
**대표적인 3가지 방법**
* xml에 직접 등록하기

* @Bean 어노테이션을 사용하여 등록

* @Component, @Controller, @Service, @Repository 를 사용하여 등록

1. XML에 직접 등록
    * bean 태그를 사용하는 방법
    ```xml
    <bean id="helloService" class="com.example.myapp.di.HelloService"/>

    <bean id="helloController" class="com.example.myapp.di.HelloController" p:helloService-ref="helloService">		
    </bean>
    ```
    application-config.xml을 resource 아래에 만든다. 그리고 beans 태그 안에 bean을 만든다.


2. @Bean을 사용한 방법
    ```java
    package com.example.myapp.di;

    import org.springframework.beans.factory.annotation.Configurable;
    import org.springframework.context.annotation.Bean;
    import org.springframework.context.annotation.ComponentScan;
    import org.springframework.context.annotation.ImportResource;

    @Configurable
    @ComponentScan(basePackages= {"com.example.myapp"})
    @ImportResource(value= {"classpath:application-config.xml"})
    public class AppConfig {
            @Bean
            public IHelloService helloService() {
                return new HelloService();
            }
            
            @Bean
            public HelloController helloController() {
                HelloController controller = new HelloController();
                controller.setHelloService(helloService());
                return controller;
            }
    }
    ```
    인스턴스를 반환하고 빈에 등록하는 코드

    메서드 위에 Bean태그를 사용하고 AppConfig 객체 위에 여러 어노테이션을 선언해준다.

3. Component, Controller, Service, Repository 어노테이션 사용
    ```java
    package com.example.myapp.hr;

    import org.springframework.beans.factory.annotation.Autowired;
    import org.springframework.beans.factory.annotation.Qualifier;
    import org.springframework.stereotype.Controller;


    @Controller
    public class EmpController {
        
        private IEmpService empService;
        
        @Autowired
        public EmpController(IEmpService empService) {
            this.empService = empService;
        }
        
        void printInfo() {
            int count = empService.getEmpCount(50);
            System.out.println("사원의 수 : " + count);
        }
    }
    ```
    위 코드는 Controller와 Autowired를 사용하여 빈에 등록하고 의존성을 주입해준 경우이다.