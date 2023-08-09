# 과제

* DAO
* DTO
* VO
* Entity

<br>

## DAO, DTO, VO, Entity란?
   
### DAO(Data Access Object)란?

* DAO는 데이터베이스의 데이터에 접근하기 위한 객체로 직접 데이터베이스에 접근하여 데이터를 삽입, 삭제, 조회 등 조작할 수 있는 기능을 수행한다   
* 데이터베이스 접근을 하기 위한 로직과 비지니스 로직을 분리하기 위해 사용한다   
* DAO의 경우는 데이터베이스와 연결한 Connection 까지 설정되어 있는 경우가 많다   
* 현재 많이 쓰이는 Mybatis 등을 사용할 경우 커넥션풀까지 제공되고 있기 때문에 DAO를 별도로 만드는 경우는 드물다   
    * Mybatis -> 객체 지향 언어인 자바의 관계형 데이터베이스 프로그래밍을 좀 더 쉽게 할 수 있게 도와 주는 개발 프레임 워크이다
    * JPA -> 자바 어플리케이션에서 관계형 데이터베이스를 사용하는 방식을 정의한 인터페이스이다

<br>

### DTO(Data Transfer Object)란?

* DTO는 게층간(Controller, View, Businuess Layer) 데이터 교환을 위한 자바 빈즈(Java Beans)를 의미한다   
* DTO는 로직을 가지지 않는 데이터 객체이고 getter/setter메소드만 가진 클래스를 의미한다   
* DTO는 데이터 전송(이동) 객체라는 의미를 가지고 있다    
* DTO는 주로 비동기 처리를 할 때 사용한다    
* 계층간 데이터 교환을 위한 객체(Java Beans)이다   
* 데이터베이스의 데이터를 Service나 Controller 등으로 보낼 때 사용하는 객체를 말한다 / 즉, 데이터베이스의 데이터가 Presentation Logic Tier로 넘어올때는 DTO로 변환도어 오고가는 것이다   
* Controller Layer에서 Response DTO 형태로 Client에 전달한다    

<br>


* Java Beans 
    * Java로 작성된 소프트웨어 컴포넌트를 지칭하는 단어 비즈니스 로직 부분을 담당하는 Java 프로그램 단위   
    * JSP페이지가 복잡한 자바 코드로 구성되는 것을 피할 수 있다(장점)   
    * 재사용 가능한 컴포넌트를 만들 수 있다(장점)   

<br>

### VO(Value Object)란?

* DTO와 달릴 VO는 Read-Only속성을 값 오브젝트이다    
* 자바에서 단순히 값 타입을 표현하기 위해 불변 클래스(Read-Only)를 만들어 사용한다   
* 예를 들면 빨강은 Color.RED, 초록은 Color.GREEN 이렇게 단순히 값만 펴현하기 위해 getterr기능만 존재한다   
* VO의 핵심 역할을 equals()와 hashcode()를 오버라이딩 하는 것이다   
* VO 내부에 선언된 속성(필드)의 모든 값들이 VO 객체마다 값이 같아야, 똑같은 객체라고 판별한다    
* VO는 Getter와 Setter를 가질 수 있으먀, VO는 테이블 내에 있는 속성 외에 추가적인 속성을 가지룻 있으며, 여러 테이블에 대한 공통 속성을 모아서 만든 BaseVO 클래스를 상속받아서 사용할 수 도있다   

<br>

* DTO vs VO
    * DTO는 가변의 성격을 가진 클래스이며 데이터 전송을 위해 존재한다(getter, setter)   
    * VO는 값 그 자체의 의미를 가진 불변 클래스(Read-Only)를 의미한다(getter만 존재)   

*즉, VO는 특정한 비즈니스 값을 담는 객체이고, DTO는 Layer간의 통신 용도로 오고가는 객체를 말한다*

<br>

### Entity란?

* Entity 클래스는 실제 데이터베이스의 테이블과 1 : 1로 매핑 되는 클래스로, 데이터베이스의 ㄷ3ㅔ이블내에 존재하는 컬럼만을 속성으로 가져야 한다   
* Entity 클래스는 상속을 받거난 구현체여서는 안되며, 테이블내에 존재하지 않는 컬럼을 가져서도 안된다
* Entity 클래스 또는 가장 Core한 클래스라고 부른다    
* 최대한 외부에서 Entity 클래스의 getter method를 사용하지 않도록 해당 클래스 안에서 필요한 로직 method를 구현 해야하고, Domain Logic만 가지며 Presentation Logic을 가지고 있어서는 안된다   
* 구현 method는 주로 Service Layer에서 사용한다

* * *

1. Entity, DTO Class 분리 이유
* Entity와 DTO를 분리해서 관리해야 하는 이유는 DB Layer와 View Layer 사이의 역할을 분리 하기 위해서이다
* Entity 클래스는 실제 테이블과 매핑되어 만일변경되게 되면 여러 다른 클래스에 영향을 끼치고, DTO클래스는 View와 통신하며 자주 변경되므로 분리 해주어야 한다   

*결국 DTO는 Domain Model 객체를 그대로 두고, 복사하여 다양한 Presentation Logic을 추가한 정도로 사용하며 Domain Model 객체는 Persistent만을 위해서 사용해야한다*

<br>

2. Entity Setter 금지 및 생성자, 접근 제어
* Entity를 작성할 때 setter를 문분별하게 사용하면 객체의 값을 변경할 수 있으므로 객체의 일관성을 보장할 수 없다
* 객체의 일관성을 유지할 수 있어야 유지 보수성이 올라가기 때문에 setter를 사용해서는 안되며, 객체의 생성자에 값들을 넣어줌으로써 setter 사용을 줄일 수 있다

```
// 객체 생성자 설정
public Member(String username, String password, String name){
    this.username = username;
    this.password = password;
    this.name = name;
}
```

```
// 객체 생성 시 값 세팅(빌더패턴 사용)
Member member = Member.Builder()
.username("name")
.password("1234")
.name("name")
.build();
```

* * *

* @Entity
    * 테이블과 링크될 클래스임을 나타낸다
    * 기본값으로 카멜케이스 이름을 언더 스커어 네이밍(_)으로 테이블 이름을 매핑한다
    * SalesManager.java -> sales_manager table(예시)

* @GenertateValue
    * PK 생성 규칙
    * 스프링 부트 2.0에서는 GenerationType.IDENTITY 옵션을 추가해야만 auto_increment가 된다

* @ld
    * 해당 테이블의 PK 필드를 나타낸다

* @Column
    * 테이블의 컬럼을 나타내며 굳이 선언하지 않더라도 해당 클래스의 필드는 모두 컬럼이 된다
    * 사용하는 이유는, 기본값 외에 추가로 변경이 필요한 옵션이 있으면 사용한다

* @Builder
    * 해당 클래싕 빌더 패턴 클래스를 생성
    * 생성자 상단에 선언 시 생성자에 포한된 필드만 빌더에 포함

* * *

### *데이터를 셋팅하고 가져오는 용도로는 DTO를 사용하며, getter/setter 메소드 외에 로직은 절대 있으면 안된다*
### *VO는 데이터를 그대로가져오는 경우에 사용한다*
