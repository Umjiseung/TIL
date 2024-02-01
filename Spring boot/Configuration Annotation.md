# Configuration
## Configuration이란?
Spring 에서 Bean을 수동으로 등록하기 위해 class위에 어노테이션을 추가하고, Bean을 사용하여 수동으로 등록할 수 있다.

이런 방법으로 등록할 때 메서드의 이름으로 빈이 등록되기 때문에 중복되지 않게 등록해야 된다.

### 빈이 등록되는 과정
스프링 컨테이너는 Configuration이 붙어있는 클래스를 자동으로 빈으로 등록한다.

Configuration 내부에 Component가 들어있다. 이래서 해당 Class가 Bean으로 등록된다.

이래서 클래스 안에 Bean이 붙어있는 메서드를 찾아 빈을 생성한다.

## 역할
* Bean을 등록할 때 싱글톤이 되도록 보장한다.

* 스프링 컨테이너에서 Bean을 관리할 수 있다.