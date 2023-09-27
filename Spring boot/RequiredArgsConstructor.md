# RequiredArgsConstructor 
## 어노테이션

* 원래는 의존성 주입을 위해 생성자(Constructor),Setter, Field 방식을 사용해야 한다.

* But Lombok의 `@RequiredArgsConstructor` 어노테이션을 사용하면 간단하게 생성자 주입을 해줄 수 있다.

* 어노테이션은 `final` 혹은 `@NotNull`이 붙은 `필드의 생성자를 자동`으로 만들어 준다.

* 하지만 자동으로 생성자가 만들어지기 때문에 예외는 언제나 발생할 수 있다.

### RequiredArgsConstructor 방식
```java
@Service
@RequiredArgsConstructor
public class TestService {
    private final TestRepository1 testRepository1;
    private final TestRepository2 testRepository2;
}
```

### 생성자 방식
```java
@Service
public class TestService {
    private final TestRepository1 testRepository1;
    private final TestRepository2 testRepository2;

    @Autowired
    public TestService(TestRepository1 testRepository1, TestRepository2 testRepository2) {
        this.testRepository1 = testRepository1;
        this.testRepository2 = testRepository2;

    }
}
```

### Setter 방식
```java
@Service
public class TestService {
    private TestRepository1 testRepository1;
    private TestRepository2 testRepository2;

    @Autowired
    public void setTestRepository1(TestRepository1 testRepository1) {
        this.testRepository1 = testRepository1;
    }

    @Autowired
    public void setTestRepository2(TestRepository2 testRepository2) {
        this.testRepository2 = testRepository2;
    }
}
```

### Field 방식
```java
@Service
public class TestService {
    @Autowired
    private TestRepository1 testRepository1;
    @Autowired
    private TestRepository2 testRepository2;
}
```