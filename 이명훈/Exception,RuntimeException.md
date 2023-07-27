# 과제    
   
* Exception
* RuntimeException

<br>

# Exception, RuntimeException   
    
* 오류와 예외
   * 자바에서는 오류를 오류(Error)와 예외(Exception)으로 나눈다
   * 오류는 시스템이 종료되어야 할 수준과 같이 수습할 수 없는 심각한 문제를 의미한다. 이는 개발자가 미리 예측하여 방지할 수없다
   * 예외는 개발자가 구현한 로직에서 발생한 실수나 사용자의 영향에 의해 발생한다. 이는 개발자가 미리 예측하여 방지할 수 있기 때문에 상황에 맞는 예외 처리를 해야한다

* 에러와 예외
   
    * 에러
        1. 컴퓨터 하드웨어의 동작의 오작동 또는 고장으로 인해 응용프로그램 실행 오류가 발생하는 것을 자바에서는 에러라고 한다
        2. 에러는 JVM 실행에 문제가 있다는 것이므로 JVM 위에서 실행되는 프로그램을 아무리 견고하게 만들어도 결국 실행 불능 상태가 되어버린다   

    * 예외
        1. 자바에서는 에러 이외에 예외이라고 부르는 오류가 있다
        2. 예외란 사용자의 잘못된 조작 또는 개발자의 잘못된 코딩으로 인해 발생하는 프로그램 오류를 말한다
        3. 예외가 발생되면 프로그램은 곧바로 종료된다는 점에서 에러와 동일하다 

* Exception(예외) / RuntimeException(실행 예외)이란?
    * 에외에은 두가지 종류가 있다. 하나는 일반 예외(Exception)이고, 다른 하나는 실행 예외(RuntimeException)이다   

    * Exception(일반 예외)
        -일반 예외는 컴파일 체크 예외라고도 하는데, 자바 소스를 컴파일하는 고정에서 예외 처리 코드가 필요한지 검사하기 때문이다 -> 만약 예외 처리 코드가 없다면 컴파일 오류가 발생하게 된다   

    * RuntimeException(실행 예외)
        -실행 예외는 컴파일하는 과정에서 예외 코드를 검사하지 않는 예외를 말한다 -> 컴파일 시 예외 처리를 확인하는 차이일 뿐, 두가지 예외 모두 예외 처리가 필요하다   

    *일반 예외와 실행 예외 클래스를 구별하는 방법은 일반 예외는 Exception을 상속 받지만 RuntimeException을 상속받지 않는 클래스들이다*

* 자주 발생하는 실행 예외의 대표적인 케이스
   
    1. NullPointerException(NPE)
        
        * 상당히 많이 출몰하는 에러이다
        * 이 에러는 객체 참조가 없는 상태, 즉 null 값을 가지고 있는 참조 변수로 객체 접근 연산자인 도트(.)를 사용했을때 발생한다 -> 즉, 해당 객체가 null인 상태에서의 접근을 했을때 해당 값이 null에 대한 접근을 하여 발생하는 에러로 객체가 없는 상태에서 객체를 사용하려 하였으니 해당 객체는 없는 상태이기 때문에 발생하는 에러라고 볼 수 있다   

        -예시 코드
        ```
        public class NullPointerexceptionExample {
                public static void main(String[] args) {
                String data = null;
                System.out.println(data.toString());
            }
        }
        ```
           
        -결과
        ```
        Exception in thread "main" java.lang.nullPointerException
                at section7.NullPointerExceptionExample.main(NullPointerExceptionExample.java:6)
        ```
        -data라는 변수에 null값을 세팅을 했기 때문에 출력부분에서 data.toString()을 통해 해당 객체의 toString()값을 출력하고 싶었으나 해당 객체는 null이기 때문에 null에는 toString() 사용할 수 없기 때문에 NullPointerException 에러가 발생하는 것을 확인 할 수 있다

## throwable class

* throwable class란?
   * 자바의 최상위 클래스인 Object 클래스를 제외하고 예외 클래스의 최상위 클래스는 Throwable 클래스이다 
