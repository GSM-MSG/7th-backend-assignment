# 과제

* 생성자
* getter
* setter

<br>

* * *

* 생성자란?
    * 객체가 생성될 때 자동을 실행되는 특수한 메서드
    * 생성자는 초기값 세팅을 할 때 필요하다
    * 생성자에서 초기값을 세팅해줬어도 엔제든 값을 바꿀 수 있는것과 같다

* 특징
    1. 리턴형을 명시하지 않는다
    2. 클래스와 이름이 동일핟
    3. 오버로딩이 가능하다
    4. 피라미터가 존재하면 파라미터로 맴버 변수의 값을 초기화한다
    5. 생성자를 선언하지 않으면 컴파일에서 자동으로 기본 생성자가 생성된다

* 선언방법
    ```
    class Student {
        Student() {} // 매개변수가 없는 생성자
        
        Student(String name, int number) {} // 매개변수가 있는 생성자
    }
    ```
* 코드 1 (기본 생성자)
```
public class Book {
    private String title;
    private String author;

    public book() {}

    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }
} // 클래스() {} 꼴
```
   
    -자바에서 생성자는 이렇게 생겼다
    -위에는 기본 생성자이고 밑에는 따로 세팅을 해준 생성자이다
    -이름이 같지만, 매개변수가 다르기 때문에 다른 생성자이다(오버로딩)
   
* 코드 2 (매개변수가 있는 생성자)
```
public class Book {
    private String title;
    private String author;

    public Book(){}

    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }
}
```
    -매개변수가 있는 생성자를 살펴보면, 선언해줬던 맴버 변수를 매개값으로 받아서 사용한다

* this. 의미
    * this.는 자기 자신을 가리킨다는 뜻이다
    * 자기 자신을 알려주는 역할을 한다(다른 생성자를 가리키는 역할도 한다는데, 아직 안배웠다)

* 게터세터 메소드
```
public void setTitle(String title) {
    this.title = title;
}

public String getTitle() {
    return title;
}
```
    -세터 메소드는 메소드 이름 앞에 set이 붙어있고, 게터 메소드는 이름 앞에 get이 붙어있다(안붙여도 상관없다)
    -세터 메소드는 this.가 들어있고, 게터 메소드는 return이 들어있다(얘는 없으면 안된다)

* 세터 메소드
```
private String title;
private String author;

public void setTitle(String title) {
    this.title = title;
}

public String getTitle() {
    return title;
}

public static void main(String[] args) {
    Book book1 = new Book();

    Book book2 = new Book("asd", "adsf);

    book2.setTitle("asdfd");

    System.out.println(book2.getTitle()+book2.getAuthor());
}
```
    -세터는 값을 set해주는 역할을 하낟
    -세터는 값을 설정해주는 역할을 한다
    -맴버변수 title을 사용할 수 있게 해준다
    -매개변수를 사용할 수 있게 해서, "asdfd"라는 값을 set해줄 수 있게 되었다

* 게터 메소드
```
private String title;
private String author;

public void setTitle(String title) {
    this.title = title;
}

public String getTitle() {
    return title;
}

public static void main(String[] args) {
    Book book1 = new Book();

    Book book2 = new Book("asd", "adsf);

    book2.setTitle("asdfd");

    System.out.println(book2.getTitle()+book2.getAuthor());
}
```
    -게터는 값을 get해주는 역할이다
    -게터는 값을 이동시켜주는 역할
    -아무것도 없는 title 객체를 이동시켜줘서 값을 return받아준다
    -위 코드에서는 세터가 넣어준 값 "asdfd"를 return 받아줬다

* private으로 필드를 선언하고 제어하는 까닭
     * 데이터를 외부에서 접근하지 않도록 막고, 메서드를 통해서 데이터에 접근 하도록 한다. 클래스 맴버 변수를 private로 접근 제한자를 설정한 후 getter/setter를 통해 맴버 변수의 값을 변경, 호출하게 된다. 이렇게 프로그래밍하는 이유는 객체의 무결성을 보장하기 위해서이다
