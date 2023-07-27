> Exception에 이어서

## try..catch

> `try..catch`문은 예외가 발생할 수 있는 코드 블록을 감싸서 예외가 발생하면 이를 처리하는 데 사용된다.

> 예외가 발생하면 실행 흐름이 `catch`블록으로 이동하여 예외를 처리한다.

```java
try {
    // 예외가 발생할 수 있는 코드 블록
    // 예를 들면, 파일을 읽는 작업이나 네트워크 연결 등
} catch (ExceptionType1 ex1) {
    // ExceptionType1이 발생한 경우 처리하는 블록
} catch (ExceptionType2 ex2) {
    // ExceptionType2가 발생한 경우 처리하는 블록
} catch (Exception ex) {
    // 기타 예외가 발생한 경우 처리하는 블록
} finally {
    // (선택사항) 예외 발생 여부와 상관없이 항상 실행되는 블록
}
```
---
## throws

> `throws`키워드는 메서드가 해당 예외를 호출한 곳으로 던질 수 있다고 선언하는 데 사용한다. 메서드가 예외를 직접 처리하지 않고, 호출자에게 처리 책임을 넘기는 경우 사용한다.

```java
public void someMethod() throws SomeException {
    // 예외가 발생할 수 있는 코드
    // 예를 들면, 파일을 읽는 작업이나 네트워크 연결 등
    if (someErrorCondition) {
        throw new SomeException("Error message"); // 예외 발생
    }
}
```
---
## throw

> `throw`키워드는 예외를 명시적으로 발생시키는 데 사용된다. 예외를 직접 처리하는 것이 아니라, 예외를 발생시켜 예외 처리를 수행하도록 하는 역할이다.

```java
public void someMethod() {
    // 예외가 발생할 수 있는 코드
    // 예를 들면, 유효성 검사나 예외 상황 처리
    if (someErrorCondition) {
        throw new SomeException("Error message"); // 예외 발생
    }
}
```

### 장점

* 예외 처리를 통해 프로그램 실행 중에 발생할 수 있는 예외 상황을 감지하고, 이를 적절히 처리함으로써 안정성을 높일 수 있다.