# Mybatis

## Mybatis란?
자바 개발자들이 DataBase를 쉽게 다루기 위해 도와주는 ORM 중 하나이다.
<br>
또한, 오픈 소스이다.

## 사용 목적
Mybatis를 사용하면서 데이터베이스 쿼리와 프로그래밍 언어와 분리하여 생산성과 유지보수성을 높이는 이점으로 사용한다.

## 장점
* SQL 쿼리를 직접 작성할 수 있고 동적 쿼리를 사용할 수 있다.
* SQL과 프로그래밍 언어와 분리되어 코드가 간결해지고 유지보수가 용이하다.
* Mybatis는 캐싱을 제공하기 때문에 데이터베이스 연산 속도를 샹항시킬 수 있다.

## 동적 쿼리
동적 쿼리는 말 그대로 실행하는 시점에 쿼리를 보내는 것으로 이것의 장점이 돋보일 때는 검색결과가 실시간으로 바뀔 때 동적으로 쿼리를 보내 검색 할 수 있는 장점이 있다.

동적 쿼리를 작성할 때 `<if>, <choose>, <when>, <otherwise>, <foreach>`와 같은 태그를 사용하여 작성 할 수 있다.

```xml
// xml 파일

<select id="getUserList" resultType="User">
  SELECT * FROM users
  <where>
    <if test="name != null"> // 동적 쿼리 
      AND name = #{name}
    </if>
    <if test="email != null"> // 동적 쿼리 
      AND email = #{email}
    </if>
  </where>
</select>
```