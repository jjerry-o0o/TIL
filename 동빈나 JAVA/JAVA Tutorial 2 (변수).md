### 동빈나 JAVA Tutorial - 2
> 코드_변수(Variable)_변할 수 있는 수
```
public class Main {
	
	public static void main(String[] args) {
		
		int intType = 100;
		double doubleType = 150.5;
		String stringType = "Jerry";
		
		System.out.println(intType);
		System.out.println(doubleType);
		System.out.println(stringType);
		
	}

}
```
>출력
```
100
150.5
Jerry
```
+ int는 정수, double은 실수, string은 문자열 자료형을 나타낼때 사용된다.
+ __int intType = 100;__ 에서 *int*는 자료형, *intType*은 변수의 이름이다.
+ __System.out.println(intType);__ 에서 *intType*은 변수의 이름을 의미한다.
+ println의 ln은 줄발꿈을 의미한다.


  
---
> 코드_상수(Constant)_항상 같은 수
>> 원의 넓이 구하기
```
public class Main {
	
	final static double PI = 3.141592;	
	
	public static void main(String[] args) {
		
		int r = 30;
		System.out.println(r * r * PI);
		
	}

}
```
> 출력
```
2827.4328
```
+ __final static double PI = 3.141592;__ PI라는 이름의 실수형(double) 상수(final)를 선언
+ 상수는 __public static void main(String[] args)__ 메인함수 바깥에 선언
---
> 코드_오버플로
```
public class Main {
	
	final static int INT_MAX = 2147483647;	
	
	public static void main(String[] args) {
		
		int a = INT_MAX;
		System.out.println(a + 1);
		
	}

}
```
> 출력
```
-2147483648
```
+ 정수형 _int_의 최댓값은 2147483647이고 최소값은 -2147483648이다.
+ 최댓값을 넘어가게되면 최소값으로 돌아가 이어서 진행된다. 이를 **오버플로**라 한다.
+ ex) 2147483647 + 8 = -2147483641
---
> 코드_사칙연산
```
public class Main {
		
	public static void main(String[] args) {
		
		int a = 1;
		int b = 2;

		System.out.println("a + b = " + (a + b));
		System.out.println("a - b = " + (a - b));
		System.out.println("a * b = " + (a * b));
		System.out.println("a / b = " + (a / b));
		
	}

}
```
>출력
```
a + b = 3
a - b = -1
a * b = 2
a / b = 0
```
+ __"a + b = "__ 부분은 문자형을 출력하는 부분이다.
+ 문자형과 자료형을 이어주기 위해 **+** 를 사용한다.
+ 나누기는 몫 만을 출력한다.
---
> 코드_반올림
```public class Main {
		
	public static void main(String[] args) {
		
		double b = 0.6;
		int a = (int) (b + 0.5);
		System.out.println(a);
	}

}
```
> 출력
```
1
```
+ 실수값 앞에 **(int)** 를 작성하여 형변환을 통해 정수값이 출력 되도록 할 수 있다.
+ 실제 값은 1.1이지만 형변환으로 정수값인 1만 출력되어지게 된다.
