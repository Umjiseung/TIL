# Spring Security
## 스프링 스큐리티란

* spring 기반의 애플리케이션의 보안을 담당하는 스프링 하위 프레임워크

* '인증'과 '권한' 부분을 Filter에 따라 처리한다.

* Filter는 Dispatcher Servlet에 가기 전에 처리되어 URL 요청을 받지만, Intercepter는 Dispatcher와 Controller사이에 위치한다는 점에 차이가 있다.

* 스프링 시큐리티에서 보안쪽으로 많은 옵션을 제공하기 때문에 개발자에겐 보안로직을 짜지않아도 되는 장점이 있다.

## 인증관련된 아키텍쳐

* 인증(Authentication) : 해당 사용자가 본인이 맞는지 확인하는 과정

* 인가(Authorization): 인증된 사용자가 요청한 자원에 접근 가능한지 결정하는 과정

* 시큐리티는 기본적으로 인증 절차를 거친 후에 인가 절차로 진행된다.

* 이런 인증과 인가를 위해 `Principal`을 아이디로, `Credential`을 비밀번호로 사용하는 `Credential` 기반의 인증 방식을 사용한다.

    * Principal(접근 주체): 보호받는 Resource에 접근하는 대상

    * Credential(비밀번호): Resource에 접근하는 대상의 비밀번호

![Alt text](image.png)

1. **HTTP Request 요청**
    > HTTP Request에 로그인 정보가 오면서 인증 요청을 보낸다.

2. **유저 기반의 인증용토큰 생성**
    > AuthenticationFilter가 가로채서 UsernamePasswordAuthenticationToken으로 가서 인증하기 위한 객체를 만든다.

3. **Fliter에서 토큰을 AuthenticationManager로 전달**
    > AuthenticationManager의 구현체인 ProviderManager한테 인증하기 위해 만든 객체를 전달한다.

4. **AuthenticationProvider에서 정보를 찾아 인증 시도**
    > ProviderManager가 AuthenticationProvider들 중에 맞는 것이 있는 지 확인한다. 맞으면 인증을 요구한다.

5. **UserDeatailService에게 전달**
    > 실제 데베에서 정보를 가져오는 UserDetailService에게 사용자 정보를 넘겨준다.

6. **UserDetails 객체를 사용하여 User객체의 대한 정보 탐색**
    > 넘겨받은 정보를 통해서 데베에서 찾아낸 사용자 정보를 UserDetails라는 객체를 만든다.

7. User객체의 대한 정보를 UserDetails에 담아 UserDetailService로 전달
    > AuthenticationProvider은 UserDetails를 받아서 정보를 비교한다.

8. **정보 비교 후 맞으면 인증, 아니면 Exception**
    > 인증이 완료되면 사용자 정보가 담긴 Authentication 객체를 반환한다.

9. **인증 완료**
    > 다시 AuthenticationFliter에게 Authentication 객체를 반환한다.

10. **SecurityContext에 인증 객체를 설정**
    > Authentication 객체를 Security Context에 저장한다.

* 아키텍쳐를 봐보면 스프링 시큐리티가 세션-쿠키기반의 인증 방식을 사용하는 것을 알 수 있다.

## Spring Security 주요 모듈

### SecurityContextHolder, SecurityContext, Authentication

* 세가지는 스프링 시큐리티의 주요 컴포넌트이다.

* 사용자의 아이디와 패스워드 사용자 정보를 넣고 실제 가입된 사용자인지 체크하고 만약에 인증에 성공하면 사용자의 principal과 credential정보를 Authentication에 넣는다.

* 스프링 시큐리티는 방금 담은 Authentication을 SecurityContext에 보관한다.

* 근데 방금 SecurityContext에 보관한 것을 SecurityContext를 SecurityContextHolder에 넣어 보관한다.

### UsernamePasswordAuthenticatiomToken

* Authentication을 구현한 AbstractAuthenticationToken의 하위 클래스이다.

* 사용자의 ID가 Principal의 역할을 하고 유저의 Password가 Credential의 역할을 한다.

* UserPasswordAuthenticationToken의 첫 생성자는 인증 전에 객체를 생성하고 두번쨰 생성자는 인증 후 객체를 생성한다.

### AuthenticationManager

* 인증에 관한 부분은 여기서 처리한다.

* 직관적으로 말하자면 AuthenticationManager에 등록된 AuthenticationProvider에 의해 처리가 된다.

* 인증을 성공하면 두번째 생성자를 사용해 생성된 객체를 SecurityContext에 저장된다.

### AuthenticationProvider

* 실제 인증에 대한 부분을 처리하는 부분이다.

* 인증하기 전인 Authentication객체를 받아서 인증을 완료한 객체를 반환하는 역할이다.

* 인터페이스를 구현해서 Custom한 AuthenticationProvider를 작성하고 AuthenticationManager에 등록한다.

### ProviderManager

* AuthenticationManager를 구현한 ProviderManager은 AuthenticationProvider을 구성하는 목록을 가진다.

### UserDetailsService

* UserDetails 객체를 반환하는 하나의 메서드만 가지고 있다.

* 일반적으로는 이것을 구현한 클래스에서 UserRepository를 주입하여 DB와 연결해서 처리한다.

### UserDetails

* 인증이 성공된 UserDetails 클래스는 Authentication 객체를 구현한 UsernamePasswordAuthenticationToken을 생성하기 위해 사용한다.

* UserDetails를 구현해 처리할 수 있다.

### SecurityCOntextHolder

* 보안 주체의 세부 정보를 가지고 있어 응용 프로그램의 현재 보안 컨텍스트에 대한 세부 정보가 저장된다.

### SecurityContext

* Authentication을 보관하는 역할이다.

* SecurityContext를 통해서 Authentication을 가져올 수 있다.

### GrantedAuthority

* 현재 사용자(principal)가 가지고 있는 권한을 말한다.

* 예를 들어 `ROLE_ADMIN`, `ROLE_USER`처럼 `ROLE_*`의 형태이다.

* GrantedAuthority객체는 UserDetailsService에 의해 불러올 수도 있고, 특정 자원에 대해 권한이 있는지 확인해 접근 허용을 판단한다.

## 마무리
> spring security를 내부 구조나 무슨 역할을 하는지 잘 알아야 나중에 문제가 생겼을 때 빠르게 대처할 수 있다. 
Spring Security어렵다...