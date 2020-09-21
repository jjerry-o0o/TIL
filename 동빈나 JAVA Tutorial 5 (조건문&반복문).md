### 동빈나 JAVA Tutorial - 5
> 코드_특정 문자 찾기
```
public class Main {

	public static void main(String[] args) {
		
		 String a = "I love You.";
		 if(a.contains("Love"))
		 {
			 //포함하는 경우 실행되는 부분
			 System.out.println("Me Too.");
		 }
		 else {
			 //포함하지 않는 경우 실행되는 부분
			 System.out.println("I Hate You.");
		 }

	}

}
```
> 출력
```
I Hate You.
```
+ String 은 비원시 자료형이기 때문에 **contains** 라는 내부적인 함수를 갖는다.
+ **contains** 함수는 a라는 변수가 특정문자를 포함하고 있는지 검사해주는 함수이다.(대소문자 구분)
---
> 코드_학점
```
public class Main {

	public static void main(String[] args) {
	
		int score = 95;
		
		if(score >= 90)
		{
			System.out.println("A+입니다.");
		}
		else if(score >= 80)
		{
			System.out.println("B+입니다.");
		}
		else if(score >= 70)
		{
			System.out.println("C+입니다.");
		}
		else
		{
			System.out.println("F입니다.");
		}
	}

}
```
> 출력
```
A+입니다.
```
+ 마지막에는 **else** 만 쓴다.
+ **if, else if, else** 를 사용하는것을 **if문** 이라 한다
---
> 코드_문자열,정수형 비교
```
public class Main {

	public static void main(String[] args) {
	
		String a = "Man";
		int b = 0;
		
		// 자바는 String을 비교할 때 equal()을 이용합니다.
		// 그 이유는 String은 다른 자료형과 다른 문자열 자료형이기 때문입니다.
		if(a.equals("Man"))
		{
			System.out.println("남자입니다.");
		}
		else
		{
			System.out.println("남자가 아닙니다.");
		}
		
		if(b == 3)
		{
			System.out.println("b는 3입니다.");
		}
		else
		{
			System.out.println("3이 아닙니다.");
		}
		
		if(a.equalsIgnoreCase("man") && b == 0)
		{
			System.out.println("참입니다.");
		}
		else
		{
			System.out.println("거짓입니다.");
		}
	}

}
```
> 출력
```
남자입니다.
3이 아닙니다.
참입니다.
```
+ **equalsIgnoreCase** 함수는 대소문자를 무시하고 비교해주는 함수이다.
---
> 코드_while 반복문_1부터 1000까지 더하기
```
public class Main {

	public static void main(String[] args) {
	
		int i = 1, sum = 0;
		while(i <= 1000)
		{
			sum += i++;
		}
		System.out.println("1부터 1000까지의 합은 " + sum + "입니다.");
	}

}
```
> 출력
```
1부터 1000까지의 합은 500500입니다.
```
+ 초기화는 한줄에 같이 할 수도 있다.
---
> 코드_for문_별찍기(삼각)
```
public class Main {

	final static int N = 5;
	
	public static void main(String[] args) {
	
		for(int i = N; i > 0; i--)
		{
			for(int j = i; j > 0; j--)
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
★★★★★
★★★★
★★★
★★
★
```
+ **for문** 은 초기화 부분, 조건 부분, 연산 부분으로 구성되어 있다.
+ **for(int i = N; i > 0; i--)** -> i는 N(5)부터 시작해서 0보다 i값이 큰 동안 i-1을 하면서 반복된다.
+ **for(int j = i; j > 0; j--)** j값이 5일때 부터 반복하고 j가 0이 됐을때 반복문을 나와 **System.out.println();** 줄바꿈을 진행한 후 i--가 적용된 값 4부터 반복문이 진행된다.
---
> 코드_별찍기(원)
```
public class Main {

	final static int N = 4;
	
	public static void main(String[] args) {
	
		// 원의 방정식 : x^2 + y^2 = r^2
		for(int i = -N; i <= N; i++)
		{
			for(int j = -N; j <= N; j++)
			{
				if(i * i + j * j <= N * N)
				{
					System.out.print("★");
				}
				else
				{
					System.out.print("☆");
				}
			}
			System.out.println();
		}
	
	}

}
```
> 출력
```
☆☆☆☆★☆☆☆☆
☆☆★★★★★☆☆
☆★★★★★★★☆
☆★★★★★★★☆
★★★★★★★★★
☆★★★★★★★☆
☆★★★★★★★☆
☆☆★★★★★☆☆
☆☆☆☆★☆☆☆☆
```
+ 원의 방정식을 활용한 별찍기
+ 좌표 사용, 모눈종이를 생각하면 됨
+ j는 x축, i는 y축
+ 이해가 안된다.
---
> 코드_break문
```
public class Main {
	
	public static void main(String[] args) {

		int count = 0;
		
		for(;;)
		{
			System.out.println("제리바보");
			count++;
			if(count == 3)
			{
				break;
			}
		}
		
	}

}
```
> 출력
```
제리바보
제리바보
제리바보
```
+ **for(;;)** 무한 루프를 의미한다.
+ **break문** 은 가장 가까운 반복문에서 탈출시켜준다.
