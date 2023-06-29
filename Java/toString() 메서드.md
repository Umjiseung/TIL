#
## toString 메서드
#

### Object 클래스
> 자바의 `Object`클래스는 모든 자바 클래스의 최상위 클래스로, 전체 이름은 `java.lang.Object`이다.

> `Object`클래스는 가장 최상위 클래스이므로 자바의 모든 클래스들은 `Object`클래스를 상속받는데, 컴파일 과정에서 컴파일러가 자동으로 extends해준다.

### Object 클래스의 메서드

#### toString() 메서드
> `toString`은 말 그대로 객체의 정보를 String(문자열)형으로 형변환 해준다.

> `Object`클래스를 상속받은 클래스들은 `toString()`을 오버라이딩(재정의)하여 사용할 수 있다.

> 자주 쓰이는 String이나 Integer클래스에는 `toString()`이 임 재정의 되어 있다.

> 먼저 `Object`클래스의 `toString()`부터 살펴보면, 예제로 `Book`이라는 클래스를 만들어 테스트 해 볼 것이다.

> Book은 따로 상속받는 클래스가 없으므로 자동으로 Object를 상속받는다.

```java
public class Book {
  int bookNumber;
  String bookTitle;

  Book (int bookNumber, String bookTitle) {
    this.bookNumber = bookNumber;
    this.bookTitle = bookTitle;
    }
  }

public class toStringEx {
  public static void main (String[] args) {
    Book book = new Book(100,"개미");

    System.out.println(book);
    System.out.println(book.toString());
    }
}

/* 출력결과
object.Book@16f65612
object.Book@16f65612
*/
```
> `Book`을 그대로 출력한 결과와 `book.toString()`의 출력결과가 같다.

> `System.out.println`에 참조 변수(Object형)를 넣으면 `toString()`이 자동으로 호출된다.

* Object.Book@16f65612

> 출력결과의 @를 기준으로 좌측은 `클래스의 이름`을 나타내고, 우측은 `해시코드 값`을 나타낸다. 

> 해시 함수에 의해 자동으로 생성된 값인데 객체를 유일하게 식별할 수 있는 정수 값이다.

#### toString() 재정의 하기

> Book클래스에서 `toString`메서드를 사용했을 때 해시코드 값이 아니라 사용자가 원하는 문자열을 출력하도록 메서드를 재정의해야된다.

```java
public class Book {
  int bookNumber;
  String bookTitle;

  Book (int bookNumber, String bookTitle) {
    this.bookNumber = bookNumber;
    this.bookTitle = bookTitle;
    }
    
  @Override
  public String toString() {
     System.out.println(bookTitle+" "+bookNumber);
       }
    }

public class toStringEx {
  public static void main (String[] args) {
    Book book = new Book(100,"개미");

    System.out.println(book);
    System.out.println(book.toString());
    }
}

/* 출력결과
개미 100
개미 100
*/
```

> Book클래스에 위와 같이 오버라이딩 코드를 추가하고, 다시 테스트해보면 해시코드 대신에 책제목과 책번호가 출력되는 것을 볼 수 있다.
