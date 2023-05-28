#
# REST

## REST란
REST(Representational State Transfer)의 약자로 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것을 의미한다

### 즉 REST란
1. HTTP URI를 통해 자원을 명시

2. HTTP Method(POST, GET,PUT,DELETE,PATCH 등)을 통함

3. 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미


#
# REST API

## REST API란
REST API란 REST의 원리를 따르는 API를 의미

## REST API 설계 예시
1. URI는 동사보다 명사, 대문자보다는 소문자를 사용

* Bad Example http://khj93.com/Running/
* Bad Example http://khj93.com/Running/

2. 마지막에 슬래시(/)를 포함않함

* Bad Example http://khj93.com/test/  
* Good Example  http://khj93.com/test

3. 언더바 대신 하이폰을 사용

* Bad Example http://khj93.com/test_blog
* Good Example  http://khj93.com/test-blog  

4. 파일확장자는 URI에 포함하지 않음

* Bad Example http://khj93.com/photo.jpg  
* Good Example  http://khj93.com/photo  

5. 행위를 포함하지 않음

* Bad Example http://khj93.com/delete-post/1  
* Good Example  http://khj93.com/post/1
