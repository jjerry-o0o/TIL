> Interface
+ 인터페이스(Interface)는 추상 클래스와 비슷하지만 좀 더 설계적이고 다중상속을 구현하게 해준다.
+ 사전에 정의된 추상 메소드와 상수만 가질 수 있다.
+ 실질적인 코드는 작성되지 않는다 ex) System.out.frintln("Hello world");
+ 추상 클래스보다 요구되는 설계의 기준이 높고 체계적이다
>> Dog
```java
public interface Dog {
	
	abstract void crying();
	public void show();

}
```
+ 사용될 함수들만 선언할 수 있다.
+ 함수 안에 세부 내용(코드들)은 넣을 수 없다.
>> Main
```java
public class Main implements Dog {

	public static void main(String[] args) {
		Main main = new Main();
		main.crying();
		main.show();
	}

	@Override
	public void crying() {
		System.out.println("월! 월!");
	}

	@Override
	public void show() {
		System.out.println("Hello World!");
	}
}
```
+ extends 상속이 아닌 implements 를 사용한다.
---
> 다중상속
>> Dog
```java
public interface Dog {
	
	abstract void crying();
	public void one();

}
```
>> Cat
```java
public interface Cat {
	
	abstract void crying();
	public void two();

}
```
> Main
```java
public class Main implements Dog, Cat {

	public static void main(String[] args) {

		Main main = new Main();
		main.crying();
		main.one();
		main.two();
		
	}

	@Override
	public void crying() {

		System.out.println("월! 월!");
		
	}

	@Override
	public void one() {

		System.out.println("One!");
		
	}

	@Override
	public void two() {

		System.out.println("Two!");
		
	}

}
```
> 출력
```
월! 월!
one!
two!
```
+ Dog 와 Cat 에 나온 메소드들을 모두 Main에서 구현해주어야 한다.
+ 추상클래스는 다중상속이 안되지만 인터페이스는 가능하다.
