# 과제
   
* try..catch
* throws
* throw

<br>

## try..catch

* try..catch이란?
    * try..catch문은 예외를 처리하기 위한 구문이다

* 구조
```
try {

    // 예외발생할 가능성이 있는 문장

}catch(Exception1 e1) {

    // Exception1이 발생했을 경우, 이를 처리하지 위한 문장을 적는다
    // 보통 이곳에 예외메서지를 출력하고 로그로 남김

}catch(Exception2 e2) {

    // Exception2이 발생했을 경우, 이를 처리하지 위한 문장을 적는다

}catch(ExceptionN eN) {

    // ExceptionN이 발생했을 경우, 이를 처리하기 위한 문장을 적는다

}finally{

    // 예외발생여부에 관게없이 항상 수행되어야 하는 문장을 적는다

}

```

    -try 문에서 Exception 예외가 발생할 경우 catch (Exception e) 로 빠져서 그 안의 실행문을 실행한다
    -마지막의 finally블럭은 try-catch문과 함께 예외발생 여부와 관계없이 "항상. 무조건" 실행도이어야할 코드를 적는다
    -예외 발생시 try -> catch -> finally순으로, 발생하지 않은 경우 try -> finally 순으로 실행된다

*finally 블록은 어떤 경우에 사용하냐? -> 보통은 자원이나 DB에 커넥션 한 경우,파일 닫기 등과 같은 "정리"코드를 넣는 데 사용된다*

* try..catch문 플로우

    * 예외가 try 블럭에서 발생한 경우   

        -발생한 예외와 일치하는 catch 문이 있는지 확인
        -일치하는 catch문이 있다면 catch 블럭 내의 문장을 모두 실행하고 try..catch문을 빠져나가서 그다음 문장을 수행
        -일치하는 catch문이 없다면 예외는 처리되지 못하고 에러 발생

    * 예외가 try 블럭 안에서 발생하지 않은 경우   

        1.catch블럭을 거치지 않고 전체 try..catch문을 빠져나가서 수행을 계속한다

    * 예외가 try 블럭 밖에서 발생한 경우   
        -예외는 아무 처리되지 못한 채 에러 발생

*Try..catch블럭에서 예외 발생시, 예외가 발생한 위치 이후에 있는 try블럭의 문장들은 수행도지 않으므로, try블럭에 포함시킬 코드의 범위를 잘 선택해야한다*

<br>

## throw / throws

* throw란?
    * throw는 예외를 강제로 발생시킨 후, 상위 블럭이나 catch문으로 예외를 던진다
       
```
package com.ssk.simpany,test;

public clas ExceptionTest {

    public static coid main(String[] args) {
        try {
            myException();
        }catch(Exception e) {
            System.out.println("MyClass에서 예외가 발생하였습니다.");
        }
    }

    static puvlic void myException(){
        try {
            // eception을 강제로 발생
            throw new Exception();
        }catch(Exception e) {
            e.printStackTrace();
            System.out.println("myException에서 예외가 발생하였습니다");
        }
    }
}
```
    -위 에제는 main 메소드에서 myException메소드를 호출하고, 여기서 throw를 통해 Exception을 강제로 발생 시키고 있다 -> 때문에 catch 블럭으로 처리가 위임되고, 여기서 예외를 처리하고 있다. 이는 콘솔 로그를 통해 알수있다
   
* throws란?
    * throws는 예외가 발생하면 상위메소드로 예외를 던진다
   
```
package com.ssk.simpany.test;

public class ExceptionTest {

        public static void main(String[] args) {

            try {
                myException();
            }catch(Exception e) {
                e.printStackTrace();
                System.out.println("MyClass에서 예외가 발생하였습니다");
            }
        }

        static puvlic void myException() throw Exception {
            
            throw new Exception();

        }
}
```
    -일반적으로 throws를 사용하면 try, catch 구문이 생성되지 않는 것을 확인할 수 있는데, 이 이유는 throw구문에 의해 예외에 대한 처리를 호출부로 위임하기 때문이다
    -throw를 통해 예외를 발생시키고 throws는 이 예외를 밖으로 던져버리고있다
