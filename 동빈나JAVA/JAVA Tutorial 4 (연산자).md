### 동빈나 JAVA Tutorial - 4
> 코드_몇분 몇초?
```java
public class Main {

	final static int SECOND = 1000;
	
	public static void main(String[] args) {
		
		int minute = SECOND / 60;
		int second = SECOND % 60;
		
		System.out.println(minute + "분 " + second + "초");
		
	}
}
```
> 출력
```
16분 40초
```
+ minute 는 / 연산자를 사용해 몫의 값만 갖는다.
+ second 는 % 연산자를 사용해 나머지 값을 갖는다.
---
> 코드_증감연산자
```java
public class Main {

	public static void main(String[] args) {
		
		int a = 10;
		System.out.println("현재의 a는 " + a + "입니다.");
		a++;
		System.out.println("현재의 a는 " + a + "입니다.");
		System.out.println("현재의 a는 " + ++a + "입니다.");
		System.out.println("현재의 a는 " + a++ + "입니다.");
		System.out.println("현재의 a는 " + a + "입니다.");

	}
}
```
> 출력
```
현재의 a는 10입니다.
현재의 a는 11입니다.
현재의 a는 12입니다.
현재의 a는 12입니다. 
현재의 a는 13입니다.
```
+ a++은 a값을 출력하고 난 뒤에 +1이 됩니다.
---
>코드_==,>,<,&&,||,! 연산자
```java
public class Main {

	public static void main(String[] args) {
		
		int a = 50;
		int b = 50;
		
		System.out.println("a와 b가 같은가요? " + (a == b));
		System.out.println("a가 b보다 큰가요? " + (a > b));
		System.out.println("a가 b보다 작은가요? " + (a < b));
		System.out.println("a와 b가 같은면서 a가 30보다 큰가요? " + ((a == b) && (a > 30)));
		System.out.println("a가 50이 아닌가요? " + !(a == 50));
	}
}
```
> 출력
```
a와 b가 같은가요? true
a가 b보다 큰가요? false
a가 b보다 작은가요? false
a와 b가 같은면서 a가 30보다 큰가요? true
a가 50이 아닌가요? false
```
+ 각 연산마다 괄호로 묶어줘야 한다.
---
> 코드_3항 연산자 (조건 ? 참 : 거짓)
```java
public class Main {

	public static void main(String[] args) {
		
		int x = 50;
		int y = 60;
		
		System.out.println("최댓값은 " + max(x, y) + "입니다.");
		
	}
	
	// 반환형, 함수 이름, 매개 변수
	static int max(int a, int b) {
		int result = (a > b) ? a : b;
		return result;
	}
}
```
> 출력
```
최댓값은 60입니다.
```
+ 함수는 반환형 (**int**), 함수이름 (**max**), 매개변수 **(int a, int b)**로 구성된다.
+ **return** 은 **result** 의 값을 반환한다.
+ **max(x, y)** 는 max라는 함수에 x(50), y(60) 이라는 값을 매개변수로 넣어주는 것을 뜻한다.
+ static은 클래스 전반적으로 사용되는 함수로 메인 메소드에서 max함수를 사용하기 위해선 앞에 static을 붙혀줘야한다.
---
> 코드_pow()_거듭제곱 연산자
```java
public class Main {

	public static void main(String[] args) {

		double a = Math.pow(3.0, 20.0);
		System.out.println("3의 20제곱은" + (int) a + "입니다.");
		
	}

}
```
> 출력
```
3의 20제곱은2147483647입니다.
```
+ **Math.pow** 는 Math라는 클래스에 있는 pow(거듭제곱)라는 함수를 뜻한다.
+ **(int)** 로 인해 값은 정수형으로 변환되어 출력된다.
---
> 코드_+= 연산자
```java
public class Main {

	public static void main(String[] args) {

		int i = 20;
		int o = 30;
		i = i + 1;
		o += 1;
		System.out.println(i);
		System.out.println(o);
		System.out.println((100 < i) && (i < 200));
		
	}

}
```
> 출력
```
21
31
false
```
+ **+=** 연산자는 i = i + 1; 을 간략화한 연산자이다.
+ **(100<i<200)** 과 같은 연산은 오류가 나기 때문에 각각 괄호로 묶어주어야 한다.
