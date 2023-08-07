## DAO(Data Access Object)

* DB에 직접 접근하는 객체 DB의 데이터를 삽입, 삭제, 조회 등을 조작하는 기능 수행

* DB 접근 로직과 비즈니스 로직을 분리하기 위해 사용

* DAO는 DB와 연결할 Connection 까지 설정 되어 있는 경우가 많으며 현재는 커넥션풀이 제공되고 있어서 DAO를 별도로 만드는 경우는 드물다.

```java
public interface ChattingLogRepository extends MongoRepository<ChattingLog, String> {

	public ChattingLog findAllByRoomIdx(Long roomIdx);

	public List<ChattingLog> findByRoomIdx(Long roomIdx);
}
```
---
## DTO(Data Transfer Object)

* 계층간 데이터 교환을 위해 Data를 변형하여 사용하는 객체

* 데이터 전송 객체라는 의미를 가지고 있어 주록 비동기 처리를 할 때 사용한다.

### 특징

* 로직이 없고, 순수하게 getter/setter로만 이루어져있는 객체

### 예시

> 모든 회원 정보를 불러와야 한다고 가정하자.
User Table에는 회원의 이름, 성별, 나이, 핸드폰번호, 아이디, 비밀번호 등 많은 정보들이 존재한다.
하지만, 나는 이름, 성별, 나이만 필요하다.
User Table에 모든 데이터가 필요하지 않은 지금, Entity로 만들어 둔 class를 사용하기에는 보안상의 문제, 필요없는 값을 가지고 있다는 점에서 좋지 않다.
이런 경우, 이름, 성별, 나이만 담는 DTO를 만들어 사용하자.
---
## VO(Value Object)

* DTO와 동일한 개념이지만, Read Only의 속성을 지니고 있다.

* 자바에서 단순히 값 타입을 표현하기 위해 불변 클래스를 만들어 사용한다.

* VO의 핵심 역할은 equals()와 hashcode()를 오버라이딩 하는 것

### DTO vs VO
* DTO는 가변의 성격을 가진 클래스이며 데이터 전송을 위해 존재한다. 

* 그의 반해 VO는 값 그 자체의 의미를 가진 불변 클래스를 의미한다.

---
## Entity

* 실제 DB Table과 연결된 클래스

* @Table, @ID, @Column 등의 어노테이션에 쓰인다.

### Entity, DTO 분리 이유

* 단순 테스트가 아닌 실제 프로젝트를 작성할 경우 Entity 객체를 영속 계층 바깥쪽에서 사용하는 방식 보다는 DTO를 이용하는 방식을 권장

* DTO는 Entity 객체와 달리 각 계층끼리 주고받는 우편물이나 상자의 개념

* 순수하게 데잍를 담고 있다는 점에선 Entity 객체와 유사하지만, 목적 자체가 데이터의 전달이므로 읽고, 쓰는 것이 모두 허용되는 점이 가능하고 일회성으로 사용되는 성격이 강함!!

* JPA를 이용하게 되면 Entity 객체는 단순히 데이터를 담는 객체가 아니라 실제 데이터베이스와 관련이 있고, 내부적으로 EM이 관리하는 객체

### 예시

```java
@Getter
@Setter
@Entity
@Table(name = "follow")
public class Follow extends BaseEntity {
    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    @Column(name = "follow_idx")
    private Long followIdx;

    @Column(name = "user_follower_idx")
    private Long userFollowerIdx;

    @Column(name = "user_streamer_idx")
    private Long userStreamerIdx;
}
```