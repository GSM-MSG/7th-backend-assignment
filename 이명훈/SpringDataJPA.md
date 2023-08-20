# 과제

* Spring Data JPA

<br>

## Spring Data JPA란?

*먼저 JPA란 Java Persistentce API의 약자로 JAVA에서 관계형 데이터베이스를 사용하는 방식을 정의한 인터페이스이다* -> 즉, 인터페이스이기 때문에 구현체가 없다

* Spring Data JPA는 JPA를 한 단계 더 추상화 시켜 개발 용이성을 상당히 올려주는 인터페이스이다
* Spring Data JPA는 Repository라는 인터페이스를 제공한다 -> 이 Repository는 정해진 규칙으로 인터페이스를 선언하기만 해도 자동으로 내부에서 구현체를 만들어 작동시켜준다   
    
* 추가로 ORM이란?
    * 객체와 관계형 데이터베이스의 데이터를 자동으로 매핑해주는 것을 말한다
    * 객체를 통해 간접적으로 데이터베이스 데이터를 다룬다   
        
    * 객체 지향적인 코드로 인해 더 직관적이고, 비즈니스 로직에 더집중할 수 있게 도와준다(장점)
    * 재사용성 및 유지보수의 편리성이 증가한다(장점)
    * DBMS에 대한 종속성이 줄어든다(장점)
        
    * 완벅한 ORM으로만 서비스를 구현하기가 어렵다(단점)
    * 프로시저(데이터베이스에 대한 하나로 이어지는 작업을 정리한 절차를 관계형 데이터베이스 관리 시스템에 저장한것)가 많은 시스템 에서는 ORM의 객체 지향적인 장점을 활용하기 어렵다(단점)
    
```
//
public interface MemberRepository extends JpaRepository<Member, Long> {
    List<Member> findByUsername(String username);
}
```
-JpaRepositor<엔티티, PK type> // 기본 키[PK]   
-findByUsername(String username) : 인터페이스를 선언하면 해당 메서드를 내부에서 자동으로 만들어 줌   

* Repository인터페이스의 기본 구현체인 SimpleJpaRepository의 내부를 본다면 EntityManager를 사용함, 이를 통해 Spring Data JPA는 JPA를 추상화 시켰다는 것을 알 수 있다   

-그림-
![텍스트](https://velog.velcdn.com/images%2Fyebali%2Fpost%2Fad31292b-eba6-4cc0-9b18-55b4a0b4072f%2Fimage.png)
-위의 사진을 보면 JPA, Hibernate, Spring Data JPA의 관계를 나타내고 있다

* * *

## Hibernate이란?

* Hibernate이란 JPA의 한 종류이고, 표준으로 사용되는 구현체인데 마음에 들지 않는다면 다른 구현체를 사용하거나 직접 구현하는 것도 가능하다
* 자바 언어를 위한 ORM 프레임워크이다
* 내부적으로 JDBC API를 사용한다
   
* 장점
    * Hibernate는 SQL을 적접 사용하지 않고, 메서드 호출만으로 궈리가 수앵된다, 즉 SQL 반복 작업을 하지 않음으로 생산성이 높다
    * 설정 파일에서 JPA에게 어떤 데이터베이스를 사용하고 있는지를 알려주기만 하면 얼마든지 데이터베이스를 바꿀 수 있다
    * 상속, 연관 관계, 객체 그래프 탐색, 비교 등 객체와 관계형 테이터베이스와의 패러다임 불일치(객체와 관계형 데이터베이스의 데이터 표현방식과 다루는 방법이 달라 일어나는 현성)를 해결할 수 있다

* 단점
    * 메서드 호출만으로 쿼리를 수행하는 것을 직접 SQL을 작성하는 것보다는 성능상 좋지 않다
    * 메서드 호출만으로 DB 데이텉를 조작하기에는 한계가 있다


## JDBC란?

* JDBC는 데이터베이스에 접근할 수 있도록 자바에서 제공하는 API이다
* 위의 그림에서 처럼 JPA는 JDBC를 통해 데이터베이스와 통신한다