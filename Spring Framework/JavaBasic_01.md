> kr.co.softcampus.beans(package)
>> HelloWorldEn.java
```java
package kr.co.softcampus.beans;

public class HelloWorldEn {
	
	public void sayHello() {
		System.out.println("HI~~~");
	}
}
```
>> HelloWorldKo.java
```java
package kr.co.softcampus.beans;

public class HelloWorldKo {
	
	public void sayHello() {
		System.out.println("안녕하세요");
	}
}
```
> kr.co.softcampus.main(package)
>> MainClass.java
```java
package kr.co.softcampus.main;

import kr.co.softcampus.beans.HelloWorldEn;

public class MainClass {

	public static void main(String[] args) {
		
		HelloWorldEn hello1 = new HelloWorldEn(); //객체 생성, 객체의 주소값을 가지고 있는 참조변수를 만들어준다.
		callMethod(hello1); //메소드 호출
		
		HelloWorldEn hello2 = new HelloWorldEn();
		callMethod(hello2);
	}
	
	public static void callMethod(HelloWorldEn hello) { //위에서 만든 객체의 주소값을 받아서 작업하는 메소드
		hello.sayHello();
	}

}
```
- 스프링 프레임워크를 공부하기전 자바의 문제점에 대해 알아보자
- 위 코드를 실행해보면 'Hi~~~'가 두번 출력되어지는데 이를 '안녕하세요'가 출력되도록 수정하려면, 모든 **HelloWorldEn** 을 수정해야된다.
- 5번이나 손이 가고, import도 다시 해줘야한다->유지보수가 불편하다.
