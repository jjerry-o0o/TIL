> 문제_n번째 피보나치 수열 값 구하기
> 코드_반복함수
```java
public class Main {

	public static int fibonacci(int number) {
		int one = 1;
		int two = 1;
		int result = -1;
		if (number == 1)
		{
			return one;
		}
		else if (number == 2)
		{
			return two;
		}
		else
		{
			for(int i = 2; i < number; i++)
			{
				result = one + two;
				one = two;
				two = result;
			}
		}
		return result;		
	}
	
	public static void main(String[] args) {

		System.out.println("피보나치 수열의 10번째 원소는" + fibonacci(10) + "입니다.");
		
	}

}
```
> 출력
```
피보나치 수열의 10번째 원소는55입니다.
```
+ 앞의 1번째 2번째 수를 더해 나열한 피보나치 수열
+ 앞의 **1번째 수** , **2번째 수** 를 표현하기 위한 **int one** 과 **int two** 
+ 각각 1로 초기화한 이유는 피보나치 수열에서 가장작은수가 1과 1이기 때문인것 같다. (1,1,2,3,5,8···)
+ **for(int i = 2; i < number; i++)** 부분에서 i를 2로 초기화한 이유는 위 반복문에서 number = 1, number = 2일때의 값을 구했고 <= 가 아니라 < 이기 때문인것 같다.
   + **for(int i = 3; i <= number; i++)** 로 해봤는데 같은 결과가 나왔다.
+ 해설을 듣다 보니 for 반복문 부분만 있어도 되는게 아닌가? 라고 생각이 들어서 if문 부분을 지워봤는데
   + number의 값이 1이거나 2일때의 값이 구해지지 않았다.
---
> 코드_재귀함수
```java
public class Main {

	public static int fibonacci(int number) {
		if(number == 1)
		{
			return 1;
		}
		else if(number == 2)
		{
			return 1;
		}
		else
		{
			return fibonacci(number - 1) + fibonacci(number - 2);
		}
	}
	
	public static void main(String[] args) {

		System.out.println("피보나치 수열의 10번째 원소는" + fibonacci(10) + "입니다.");
		
	}

}
```
> 출력
```
피보나치 수열의 10번째 원소는55입니다.
```
+ 어찌 이런일이... 재귀함수는 항상 신선하고 놀랍다.
+ 하지만 이렇게 값을 구할경우 중간에 동일한 함수를 계산하게 되는 과정이 나오기 때문에 상당히 비효율적이게 된다
   + f(10) = f(9) + f(8) = f(8) + f(7) + f(7) + f(6) // f(8) 중복, f(7) 중복
+ f(47)까지 입력해봤는데 number가 높아질수록 계산이 상당히 느려지는게 보였다!
