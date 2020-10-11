> 다형성 (Polymorphism)
>> Fruit
```java
public class Fruit {

	String name;
	int price;
	int fresh;
	
	public void show() {
		System.out.println("이름 : " + name);
		System.out.println("가격 : " + price);
		System.out.println("신선도 : " + fresh);
	}
}
```
>> Peach
```java
public class Peach extends Fruit {
	
	public Peach() {
		price = 1500;
		name = "복숭아";
		fresh = 75;
	}

}
```
>> Banana
```java
public class Banana extends Fruit {
	
	public Banana() {
		price = 1000;
		name = "바나나";
		fresh = 80;
	}

}
```
>> Main
```java
public class Main {

	public static void main(String[] args) {
		
		Fruit fruit = new Banana();
		fruit.show();

	}

}
```
>> 출력
```
이름 : 바나나
가격 : 1000
신선도 : 80
```
+ 부모 클래스에 변수로써 자식 클래스의 instance를 넣을 수 있다 **Fruit fruit = new Banana();**

---

> 실제 사용예시
>> Main
```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		Scanner scanner = new Scanner(System.in);
		System.out.print("바나나 : 1, 복숭아 : 2 ?");
		int input = scanner.nextInt();
		Fruit fruit;
    
		if(input == 1) {
			fruit = new Banana();
			fruit.show();
		}
		else if(input == 2) {
			fruit = new Peach();
			fruit.show();
		}
	}

}
```
1. 값을 입력받을 수 있게 scanner를 선언해준다.
2. **Fruit fruit;** 이건 Fruit 클래스를 변수 fruit에 넣는다는 건가?
3. **fruit = new Banana();** 그런다음 fruit 변수에 Banana 클래스를 넣고 
4. **fruit.show();** 그 값을 보여준다. 는 것 같다.
> 정리
>+ Fruit 라는 하나의 틀을 가진 부모 클래스를 만들어준다.
>+ Peach, Banana 와 같이 부모 클래스를 상속받아 그 틀에 값이 들어간 자식 클래스를 만들어 준다.
>+ Main 클래스에서 사용시 자식클래스를 변수로 불러와 사용한다.
>+ 유동적으로 값이 바뀔수 있다는 점이 장점이다.
