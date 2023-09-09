# ResponseEntity
## ResponseEntity란

* HTTPEntity를 상속받는, 결과 데이터와 HTTP 상태 코드를 직접 제어할 수 있는 클래스

* ResponseEntity에는 사용자의 HTTPRequest에 대한 응답 데이터가 포함된다.

* 에러 코드와 같은 HTTP 상태 코드를 전송하고 싶은 데이터와 함께 전송할 수 있기 때문에 좀 더 세밀한 제어가 필요한 경우 사용한다.

## ReponseEntity 구조

* ReponseEntity는 HTTPEntity를 상속받고 사용자의 응답 데이터가 포함된 클래스이기 때문에 **HTTPStatus, HTTPHeaders, HTTPBody를 포함한다.

* ResponseEntity 내부를 보면, <바디, 헤더, 상태코드>순의 생성자가 만들어지는 것을 볼 수 있다.

## HTTP Heager와 body차이점

* HTTP Header애는 요청, 응답에 대한 요구사항이 있고

* HTTP Body에는 요청과 응답에 내용이 적혀있다.

* Response header에는 웹서버가 웹브라우저에 응답하는 메세지가 들어있고, Response Body에 데이터 값이 들어가있다.

### Response header form

* 웹브라우저가 요청한 메세지에 대해 status 즉 성공했는지 여부, 메세지 그리고 요청한 값들이 body에 담겨있다.

![Alt text](image.png)

* Location: 301,302 상태코드일 때만 볼 수 있는 헤더로 서버의 응답이 다른 곳에 있다고 알려주면서 URI를 지정한다.

* Sever: 웹서버의 종류

* Age: max-age 시간내에 얼마나 흘렀는지 초 단위로 알려주는 값

* Referrer-policy: 서버 referrer 정책을 알려주는 값

* WWW-Authenticate: 사용자 인증이 필요한 자원을 요구할 시, 서버가 제공하는 인증 방식

* Proxy-Authenticate: 요청한 서버가 프록시 서버인 경우 유저 인증을 위한 값

### 정리

> ResponseEntity 클래스를 사용하면 결과값, 상태코드, 헤더값을 모두 프론트쪽으로 넘겨줄 수 있고, 에러코드 또한 자세하게 설정해서 보내주기 가능
---
## ResponseEntity 사용방법

* String 내부에서 ResponseEntity 객체가 구현이 되어있고, 그것을 보고 그대로 사용하면 된다.

* 생성자를 다양하게 써서 status값만 넣거나, body만 넣어도 ResponseEntity의 나머지 값은 NULL로 들어간다.
---
## 주의할 점

* 자바 제네릭 특징으로 와일드 카드가 있다.

* ResponseEntity도 제네릭 타입으로 컴파일 전에 미리 데이터타입을 명시하므로 와일드 카드를 사용할 수 있다.

### 여기서 와일드 카드란?

* 제네릭 타입으로 데이터타입을 명시하지않고, 런타입까지 유연하게 가져가는 것

### ResponseEntity가 Void를 처리할 때

* 타입을 형식을 맞춰주기 위해, 와일드 카드를 사용하기 보다, Object로 데이터 타입을 명시해주는 것이 가독성 측면, 혹시 모를 에러 측면과 유지보수 측면에서 더 낫기때문이다.

```java
@PostMapping("/post/like")
public ResponseEntity<Objects> updateLike(@RequestBody SetLikeDto.Request postLikeDto, @AuthenticationPrincipal UserDetailsImpl userDetails){
    Post post = postService.setPostLike(postLikeDto,userDetails.getUser());

    SetLikeDto.Response response = modelMapper.map(post, SetLikeDto.Response.class);

    return ResponseEntity.ok(response);
}


//와일드카드 대신 이렇게도 할 수 있지만, 타입을 명시해주는게 더 좋습니다.
@PostMapping("/post/like")
public ResponseEntity updateLike(@RequestBody SetLikeDto.Request postLikeDto, @AuthenticationPrincipal UserDetailsImpl userDetails){
    Post post = postService.setPostLike(postLikeDto,userDetails.getUser());

    SetLikeDto.Response response = modelMapper.map(post, SetLikeDto.Response.class);

    return ResponseEntity.ok(response);
}
```
    