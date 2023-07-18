#
## void
#

### void란
---
> void의 역할은 `return 되는 타입이 없음을 의미`한다. 즉 아무것도 리턴하지 않음을 선언해주는 것과 같다

> 예를 들어 아래 코드는 리턴에 대하여 void를 선언하였으므로 아무것도 리턴하지 않아야 에러가 발생하지 않는다.
---
### void 사용 예제

```java
public void test() {
    siteurl = 'webisfree.com';
}
```
> 위 함수 test()는 void로 리턴타입을 선언하였다. 만약에 리턴타입이 다르다면 실제 함수의 리턴값도 동일해야한다. 아래는 string이므로 문자열을 리턴해야한다.

```java
public string getUrl() {
    return 'webisfree.com'
}
```
> 만약에 문자열이 아니라면 에러가 발생한다. 이처럼 유연한 자바스크립트와는 달리 자바는 매우 strict한다.