> 문제_팩토리얼 구하는 함수
>> 혼자 생각해보기
```java
public class Main {

	public static int factorial(int n) {
		for(int i = 1; i <= n; i++) {
			 int i * (int i + 1)
		}
		return n;
	}
  
	public static void main(String[] args) {
		System.out.println(factorial(5));
	}
}
```
+ 뭔가 여기서 이렇게저렇게 하나만 고치면 될 것 같은데 잘 모르겠다.
---
> 코딩
```java
public class Main {

	public static int factorial(int number) {
		int sum = 1;
		for(int i = 2; i <= number; i++)
		{
			 sum *= i;
		}
		return sum;
	}
	
	public static void main(String[] args) {
		
		
		System.out.println("10 팩토리얼은 " + factorial(10));

	}

}
```
> 출력
```
10 팩토리얼은 3628800
```
+ 위에서 못찾은 뭔가가 **int sum** 이었다.
+ sum 변수를 만들어 i와 연산하는 것. 똑똑하다.
---
> 코드_재귀함수 (함수 안에 자기 함수가 또 들어가 있는것)
```java
public class Main {

	public static int factorial(int number) {
		if(number == 1)
			return 1;
		else
			return number * factorial(number -1);
		}
	
	public static void main(String[] args) {
		
		System.out.println("10 팩토리얼은 " + factorial(10));

	}

}
```
> 출력
```
10 팩토리얼은 3628800
```
+ 재귀함수 정말 엄청나다. 상자 안에 상자 안에 상자가 들어있는 것 같은 풀이다.
+ **return number * factorial(number -1);** 는 10*9! 라고 풀이하면 된다.
> 머릿속 도안 구상할때
```
- 5 * 4!
- 5 * 4 * 3!
- 5 * 4 * 3 * 2!
- 5 * 4 * 3 * 2 * 1
- 1*2 = 2
- 2*3 = 6
- 6*4 = 24
- 24*5 = 120
```
+ factorial(5)를 실행하기 위해 f(4)가 필요하고, f(4)는 f(3)이 ··· 필요하다
+ 그렇게 다 찾아내려와 f(1)이 1되면 함수가 종료되고 다 찾은 값은 차근차근 곱해나간다.
+ f(1) * f(2) -> 2 * f(3) -> 6 * f(4) 24 * f(5) 
