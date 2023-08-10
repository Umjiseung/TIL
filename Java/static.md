## Static이란

* Java에서 Static을 사용한다는 것은 메모리에 한번 할당되어 프로그램이 종료될 때 해제되는 것을 의미한다.

* 일반적으로 우리가 만든 Class는 Static 영역에 생성되고, new 연산을 통해 생성한 객체는 Heap영역에 생성된다.

* 객체의 생성시에 할당된 Heap영역의 메모리는 Garbage Collector를 통해 수시로 관리를 받는다.

* 하지만 Static 키워드를 통해 Static 영역에 할당된 메모리는 모든 객체가 공유하는 메모리라는 장점을 지니지만, Garbage Colletor의 관리 영역 밖에 존재하므로 Static을 자주 사용하면 프로그램의 종료시까지 메모리가 할당된 채로 존재하므로 자주 사용하게 되면 시스템의 퍼포먼스에 악영향을 준다.

### Static 변수 특징

* 객체를 생성하지 않고도 Static 자원에 접근이 가능하다.

```java
public class MyCalculator {
    public static appName = "MyCalculator";

    public static int add(int x, int y) {
        return x + y;
    }

    public int min(int x, int y) {
        return x - y;
    }
}

MyCalculator.add(1, 2);   //  static 메소드 이므로 객체 생성 없이 사용 가능
MyCalculator.min(1, 2);   //  static 메소드가 아니므로 객체 생성후에 사용가능


MyCalculator cal = new MyCalculator();
cal.add(1, 2);   // o 가능은 하지만 권장하지 않는 방법
cal.min(1, 2);   // o
```
