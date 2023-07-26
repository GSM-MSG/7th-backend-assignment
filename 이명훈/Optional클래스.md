# 과제 
  
* Optional 클래스

<br>

## Optional 클래스

* Optional 클래스란?
    * Optional이라는 의미에서도 알수 있다싶이, "존재할수도 있지만 안 할 수도 있는 객체". 즉 "Null이 될수도 있는 객체"를 감싸고 있는 Wrapper 클래스를 말한다
    ```
    public final class Optional<T> {
        /**
        * Common instance for {@code empty}.
        */
        private static final Optional<?> EMPTY = new Optional<>();

        /**
        * If non-null, the value; if null, indicates no value is present
        */
        private final T value;
    }
    ```
    -Optional 클래스를 살펴 본다면, Optional<T>는 제네릭 클래스로 T 타입의 객체를 감싸는 래퍼 클래스이다 -> 따라서 Optional 타입의 객체는 모든 타입의 참조변수를 담을 수 있다
   
* 사용하는 이유
    * Optional 클래스를 다루는 이유는 null 값을 다루기 위해서이다.
    문제 1. 런타임에 NPE 예외 발생할 수 있다
    문제 2. NPE를 방어하기 위해서 null 체크 때문에 코드 가독성과 유지 보수성이 떨어진다

    *위의 문제를 해결하기 위해서 함수형 언어에서 해법을 찾아 적용한것이 바로 Optional 클래스라고 한다*
   
* 사용하므로서 얻는 장점
    * NPE를 유발할 수 있는 null을 직접  다루지 않아도 된다
    * if문으로 null 체크를 하지 않고 Optional에 정의된 메소드를 통해서 간단히 처리할 수 있다
    * 명시적으로 해당 변수가 null일 수도 있다는 가능성을 표현 가능하다

* NPE란
    * NullPointerException(NPE)
    * 데이터 값을 받아올 때 가장 쉽게 마주할 수 있는 오류
    * 보통 객체 값이 null이거나 초기화가 안되어있는 인스턴스르 사용하면서 NPE를 마주하게 된다 -> 이러한 오류를 피하기 위해 항상 Null 체크가 필요하다
