> FINAL_최종
+ 절대 변하지 않는 것으로 만들고 싶을 때 사용
+ 이 키워드는 변수, 메소드, 클래스에 모두 사용할 수 있다.

> Final _ 변수
```java
public class Main{

	public static void main(String[] args) {
		final int number = 10;
		number = 5;
		System.out.println(number);	
	}
}
```
+ **number = 5;**  final 이 붙은 변수이기 때문에 오류가 뜨고 실행 되지 않는다.
---
> Final _ 메소드
>> Parent
```java
public class Parent {
	
	public void show() {
		System.out.println("Hi");
	}
}
```
>> Main
```java
public class Main extends Parent {

	public static void main(String[] args) {
		Main main = new Main();
		main.show();
	}
}
```
+ Parent 를 상속받아 Hi 를 출력하게 된다.
>> Main _ overriding
```java
public class Main extends Parent {
	
	public void show() { // overriding (함수의 재정의)
		System.out.println("Hello");
	}

	public static void main(String[] args) {

		Main main = new Main();
		main.show();
	}
}
```
+ 기존에 Parent 를 상속받아 Hi 를 출력하였으나 overriding 되어 Hello 를 출력하게 된다.
>> Parent _ method _ final
```java
public class Parent {
	
	public final void show() {
		System.out.println("Hi");
	}
}
```
+ show 함수에 final 이 붙게되면서 Main 클래스의 overriding 부분엔 오류가 나타나게 된다.
---
> Final _ 클래스
>> Parent _ class _ final
```java
final class Parent {
	
	public final void show() {
		System.out.println("Hi");
	}
}
```
+ Parent 클래스에 final 을 붙히게 되면 더이상 상속이 안되기 때문에 Main 클래스에 오류가 나타나게 된다.
