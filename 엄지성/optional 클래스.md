## NPE(NullPointerException)이란

* null 값을 가진 객체를 참조하려고 했을 때 일어나는 Exception

* String 처리나, 서버 송수신 처리시에 자주 발생한다.

```java
List<String> names = getNames();
names.sort(); // names가 null이라면 NPE가 발생함

List<String> names = getNames();
// NPE를 방지하기 위해 null 검사를 해야함
if(names != null){
    names.sort();
}
```
---
## Optional이란

* Optional<T> 클래스를 사용해 NPE를 방지할 수 있도록 도와준다.

* Optional<T>는 null이 올 수 있는 값을 감싸는 Wrapper클래스로 참조해도 NPE가 발생하지 않도록 도와준다.

* Optional 클래스는 아래와 같은 value에 값을 저장하기 때문에 값이 null이여도 바로 NPE가 발생하지 않는다.

```java
public final class Optional<T> {

  // If non-null, the value; if null, indicates no value is present
  private final T value;
   
  ...
}
```
---
## Optional 활용

<br>

### Optional.empty() - 값이 Null인 경우

* Optional은 Wrapper 클래스이기 때문에 값이 없을 수 있는데, 이때는 Optional.empty()로 생성할 수 있다.
```java
Optional<String> optional = Optional.empty();

System.out.println(optional); // Optional.empty
System.out.println(optional.isPresent()); // false
```
<br>

### Optional.of() - 값이 Null이 아닌 경우

* 어떤 데이터가 절대 null이 아니라면 Optional.of()로 생성할 수 있다.

* 만약에 Optional.of()로 Null을 저장하려고 하면 NPE가 발생된다.

```java
// Optional의 value는 절대 null이 아니다.
Optional<String> optional = Optional.of("MyName");
```
<br>

### Optional.ofNullbale() - 값이 Null일수도, 아닐수도 있는 경우

* 어떤 데이터가 null일 수도 있고 아닐 수도 있는 경우에서 Optional.ofNullbale로 생성할 수 있다.

```java
// Optional의 value는 값이 있을 수도 있고 null 일 수도 있다.
Optional<String> optional = Optional.ofNullable(getName());
String name = optional.orElse("anonymous"); // 값이 없다면 "anonymous" 를 리턴
```