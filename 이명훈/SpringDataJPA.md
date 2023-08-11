# 과제

* Spring Data JPA

<br>

## Spring Data JPA란?

*먼저 JPA란 Java Persistentce API의 약자로 JAVA에서 관계형 데이터베이스를 사용하는 방식을 정의한 인터페이스이다* -> 즉, 인터페이스이기 때문에 구현체가 없다

* Spring Data JPA는 JPA를 한 단계 더 추상화 시켜 개발 용이성을 상당히 올려주는 인터페이스이다
* Spring Data JPA는 Repository라는 인터페이스를 제공한다 -> 이 Repository는 정해진 규칙으로 인터페이스를 선언하기만 해도 자동으로 내부에서 구현체를 만들어 작동시켜준다
```
//
public interface MemberRepository extends JapRepository<Member, Long> {
    List<Member> findByUsername(String username);
}
```
-Jparepositor<엔티티, PK type> // 기본 키[PK]   
-findByUsername(String username) : 인터페이스를 선언하면 해당 메서드를 내부에서 자동으로 만들어 줌   

* Repository인터페이스의 기본 구현체인 SimpleJpaRepository의 내부를 본다면 EntityManager를 사용함, 이를 통해 Spring Data JPA는 JPA를 추상화 시켰다는 것을 알 수 있다   

-그림-
![텍스트](https://velog.velcdn.com/images%2Fyebali%2Fpost%2Fad31292b-eba6-4cc0-9b18-55b4a0b4072f%2Fimage.png)
-위의 사진을 보면 JPA, Hibernate, Spring Data JPA의 관계를 나타내고 있다

* * *

## Hibernate이란?

* Hibernate이란 JPA의 한 종류이고, 표준으로 사용되는 구현체인데 마음에 들지 않는다면 다른 구현체를 사용하거나 직접 구현하는 것도 가능하다

## JDBC란?

* JDBC는 데이터베이스에 접근할 수 있도록 자바에서 제공하는 API이다
* 위의 그림에서 처럼 JPA는 JDBC를 통해 데이터베이스와 통신한다