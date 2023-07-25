## 생성자란
* 생성자는 인스턴스가 생성될 때 호출되는 '인스턴스 초기화 메서드'이다.

* 인스턴스 변수의 초기화 작업에 주로 사용되며, 인스턴스 생성 시에 실행되어야 할 작업을 위해서도 사용된다.

* 메서드처럼 클래스 내에 선언되며, 구조도 메서드와 유사하지만 리턴값이 없다.

### 조건
* 생성자의 이름은 클래스의 이름과 같아야 한다.

* 생성자는 리턴값이 없어야 한다.

### 생성방법
```java
class Constructor {
  // 매개변수가 없는 생성자
  Constructor() {
  	// ...
  }

  // 매개변수가 있는 생성자
  Constructor(int a, int b) {
  	// ...
  }
}
```
---
## 기본 생성자
* 명시적으로 생성자를 정의하지 않고도 인스턴스를 생성할 수 있다.
```java
// 기본 생성자는 아무 매개변수도 없고 내용도 없는 간단한 생성자이다.
class Example {
	// 클래스에 명시적으로 구현된 생성자가 없다면 이와 같은 기본 생성자가 추가되어 컴파일된다.
	Example() {}
}
```
---
## 매개변수가 있는 생성자
* 생성자도 다른 메서들과 같이 매개변수를 선언하여 사용할 수 있다.

```java
class Example {
  int value1;
  int value2;

  Example() {}

  Example(int a, int b) {
    value1 = a;
    value2 = b;
  }
}
```
---
## this(),this
* 생성자의 이름으로 클래스 이름 대신 this키워드를 사용!

* 한 생성자에서 다른 생성자를 호출할 때는 반드시 첫 줄에서만 호출이 가능하다.

```java
class Exampled {
  int value1;
  int value2;

  Exampled(int value1, int value2) {
    this.value1 = value1;
    this.value2 = value2;
  }
}
```
---
## 생성자를 이용한 인스턴스의 복사

* 현재 사용하고 있는 인스턴스의 ㄱ밧을 복사하여 이와 같은 값을 가지는 인스턴스를 만들 때 생성자를 사용가능!

```java
class Example {
  int value1;
  int value2;

  Example(int value1, int value2) {
    this.value1 = value1;
    this.value2 = value2;
  }

  Example(Example ex) {
	this(ex.value1, ex.value2);
  }
}
```
---
## getter and setter

* private를 관리하는 메서드!

* private할 때 다른 클래스에서 접근하려면 해당 클래스 ㅇ나의 메서드를 통해서만 가능하다.

* getter는 private를 외부로 꺼내는 메서드

* setter는 private에 값을 넣는 메서드

### **getter**
* 내부의 멤버변수에 저장된 값을 외부로 리턴

* 메개변수는 없고, 리턴값만 있는 메서드로 정의

* 메서드명은 주로getXXX() 메서드 형식으로 지정한다.

* XXX는 해당 멤버변수의 변수명을 사용

### **setter**
* 외부로부터 데이터를 전달받아 멤버변수에 저장

* 매개변수만 있고, 리턴값은 없는 메서드로 정의한다.
---
## getter, setter 사용이유

* private를 관리할 메서드에게 공통된 이름을 가지게 되면 관리하기가 편해지기 때문이다.
---
## getter과 setter의 규칙
* private 변수를 다른 클래스에 꺼내는 메서드는 get + 변수명(첫글자는 대문자)

* private 변수에 값을 초기화하는 메서드는 set + 변수명(첫글자는 대문자)

```java
class A {
	private int num = 10;

	public int getNum() {
		return a;
	}

	public void setNum(int a) {
		this.a = a;
	} 
}
```