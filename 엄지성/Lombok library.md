## Lombok이란?

* Java의 라이브러리로 반복되는 메소드를 어노테이션을 사용해서 자동으로 작성해주는 라이브러리!!

* DTO, Model, Entity의 경우 여러 속성이 존재하고 이들이 가지는 프로퍼티에 대해 Getter,Setter 등을 매번 작성해야하는 경우를 자동으로 만들어주는 라이브러리

### 작동 원리

1. 자바 컴파일러는 소스파일을 파싱하여 AST트리를 만든다.

2. Lombok은 Annotation Processor에 따라 AST트리를 동적으로 수정하고 새 노드를 추가하고 마지막으로 바이트 코드를 분석과 생성을 한다.
    * Annotation Processor
        > 자바 컴파일러 플러그인의 일종으로, 어노테이션에 대한 코드베이스를 검사, 수정, 생성하는 훅이다.

3. 마지막으로 자바 컴파일러는 Lombok Annotation Processor에 의해 수정된 AST를 기반으로 바이트 코드를 생성한다.



* Lombok library를 추가하면 
    ```java
    dependencies {
        compileOnly 'org.projectlombok:lombok'
        annotationProcessor 'org.projectlombok:lombok'
    }
    ```
---
## 사용법

1. **@Getter, @Setter**
* get메소드와 set메소드를 굳이 생성할 필요 없이 어노테이션을 사용하면 필드에 getter, setter를 간단하게 자동으로 생성한다.
    ```java
    import lombok.Getter;
    import lombok.Setter;

    @Getter
    @Setter
    public class Person {
        private String name;
        private int age;
    }
    ```

2. **@ToString**
* 기본적으로는 클래스 이름과 각 필드에 대한 값을 출력한다.

* 출력을 원하지 않는 변수에 @ToString.Exclude 어노테이션을 추가해주면 출력을 안 할 수 있다.
    ```java
    import lombok.ToString;

    @ToString
    public class Book {
        private String title;
        private String author;
        private int pages;

        public Book(String title, String author, int pages) {
            this.title = title;
            this.author = author;
            this.pages = pages;
        }
    }
    ```

3. **@Data**

* 모든 필드에 대해 `@ToString`, `@Getter`를, 모든 non-final 필드에 대해 `@Setter`를 설정하고 `@RequiredArgsConstructor`를 설정해주는 단축 어노테이션

