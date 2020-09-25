> 코드_이름출력
```java
public class Main {

	public static void main(String[] args) {

		System.out.println("Jerry"); 

	}

}
```
> 출력
```
Jerry
```
---
> 코드_연산자
```java
public class Main {

	public static void main(String[] args) {
		
		System.out.println(10 + 10);
		System.out.println(30 * 30);
		System.out.println(20 - 5);
		System.out.println(40 / 3);
		System.out.println(395 % 18);

	}

}
```
> 출력
```
20
900
15
13
17
```
---
> 코드_별찍기 네모네모(Jerry ver.)
```java
public class Main {

	final static int N = 5;
	
	public static void main(String[] args) {
		
		// 별 원찍기 했던거 응용
		// 중첩 for문
		for(int i = -N; i < N; i++)
		{
			for(int j = -N; j < N; j++)
			{
				System.out.print("★");
			}
			System.out.println();
		}
		

	}

}
```
> 출력
```
★★★★★★★★★★
★★★★★★★★★★
★★★★★★★★★★
★★★★★★★★★★
★★★★★★★★★★
★★★★★★★★★★
★★★★★★★★★★
★★★★★★★★★★
★★★★★★★★★★
★★★★★★★★★★
```
+ 일단 이건 N값의 두배 크기인 정사각형이 만들어진다. (내가 원하는건 입력값의 크기만한 네모가 나오는 거였다)
+ **for(int i = -N; i < N; i++)** 이 부분에서 원찍기 할때는 **i <= N** 이길래 똑같이 했다가 2N+1 만한 사이즈가 나오길래 = 을 지워서 반복되는 횟수를 줄였다.
   + 이걸로 보아 원찍기에는 =이 들어간 이유가 홀수반지름 원이 더 이쁘기 때문인게 아닐까 하고 생각했다.
---

> 코드_별찍기 네모네모(동빈나 ver.)
```java
public class Main {
	
	public static void main(String[] args) {
		
		for(int i = 0; i < 10; i++)
		{
			for(int j = 0; j < 10; j++)
			{
				System.out.print("★");
			}
			System.out.println();
		}
		

	}

}
```
> 출력
```
위와 동일
```
+ 내가 한것도... 맞는것 같다....
+ 동빈나 코드가 내가 말한 입력값만한 네모가 나오는 코드이긴 한데 한번만 입력하면 되는 코드를 만들고 싶다
