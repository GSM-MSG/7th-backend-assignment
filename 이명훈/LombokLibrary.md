# 과제

* Lombok Library

<br>

## Lombok Library이란?

* Lombok이란
    * Java 라이브러리로 반복되는 getter, setter, toString등의 메서드 작성 코드를 줄여주는 코드 다이어트 라이브러리이다, 이는 코드 자체가 반복되는 메서드로 인한 복잡함을 줄여주는 역할을 수행한다

## Lombok에서 자주 사용화는 어노테이션

* @Getter : 해당 어노테이션을 선언하면 자동으로 getXXX() 메서드를 사용 가능하게 해준다
* @Setter : 해당 어노테이션을 선언하면 자동으로 setXXX() 메서드를 사용 가능하게 해준다
* @Data : 해당 어노테이션을 선언하면 getter(), setter(), equals(), hasCode(), toString() 메서드 사용 가능하게 해준다(@Getter @Setter @toString @EqaulsAndHashCode @RequiredArgsConstructor을 자동 생성해준다)
* @toString : 해당 어노테이션을 선언하면 toString() 메서드를 사용 가능하게 해준다
* @AllArgsCOnstructor : 해당 어노테이션을 선언하면 '모든' 인자를 가지는 생성자를 구성한다
* @RequriedArgsConstructor : 해당 어노테이션을 선언하면 '필수' 인지를 가지는 생성자를 구성한다
* @NoArgsConstructor : 해당 어노테이션을 선언하면 '인자가 없는' 생성자를 구성한다

## is- 접두사로 시작하는 변수

* 변수명이 is- 접두사로 시작하는 변수 일 경우
-lombok으로 getter / setter를 사용하면 is에 대해서 인식을 안 한다
-예를 들어서 is Active라는 칼럼이 잇다면 setlsActive()나 getlsActive()가 아닌 setActive(), getActive로 사용이 된다
