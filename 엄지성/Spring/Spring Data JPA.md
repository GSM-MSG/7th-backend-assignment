# Spring Data JPA

## JPA 전에 ORM이란?
> ORM은 객체와 관계형 데이터베이스를 매핑해주는 기술!

> ORM이란 프레임워크가 중간에서 매핑해준다!!

### 이제 JPA란
> 자바 ORM기술에 대한 API 표준 명세를 뜻

### JPA를 이해하기 위한 Hibernate란?

* Hibernate는 JPA를 구현한 구현체

* 내부적으로 JDBC를 사용해 관계형 데이터베이스와 커넥션을 맺는다.
---
## Spring Data JPA란

* Spring Data JPA를 더 편하게 사용하기 위해 만든 모듈

### 주요 기능

1. Repository 인터페이스
    > 데이터 액세스 작업을 위한 메서드를 정의하는 인터페이스를 만들 수 있다. Spring Data JPA가 이것을 자동으로 구현해서 기본적인 데이터 조작을 처리한다.

2. 쿼리 메서드
    > 메서드 이름만으로 데이터를 조회하거나 조작할 수 있다.

3. 쿼리 생성
    > 복잡한 쿼리라도 "@Query"라는 어노테이션을 이용하여 직접 작성 할 수 있다.

### 설치 방법

* JPA를 사용하면 Spring Data JPA 라이브러리는 이미 설치되어 있다
```java
implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
```

### 정리

* JPA을 기반으로 만들어진 라이브러리이다.

* JPA를 잘 알아야 Spring Data JPA도 잘 이용할 수 있다.