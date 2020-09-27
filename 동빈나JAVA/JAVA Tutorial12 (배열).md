> 코드_배열(가장 큰 수 구하기)
```java
import java.util.Scanner;

public class Main {
	
	public static int max(int a, int b) {
		return (a > b) ? a : b;
	}

	public static void main(String[] args) {
		
		Scanner scanner = new Scanner(System.in);
		System.out.print("생성할 배열의 크기를 입력하세요 : ");
		int number = scanner.nextInt();
		int[] array = new int[number];
		for(int i = 0; i < number; i++)
		{
			System.out.print("배열에 입력할 정수를 하나씩 입력하세요(양수) : ");
			array[i] = scanner.nextInt();
		}
		int result = -1;
		for(int i = 0; i < number; i++)
		{
			result = max(result, array[i]);
		}
		System.out.println("입력한 모든 정수 중에서 가장 큰 값은 : " + result + "입니다.");
	}
}
```
> 출력
```
생성할 배열의 크기를 입력하세요 : 5
배열에 입력할 정수를 하나씩 입력하세요(양수) : 7
배열에 입력할 정수를 하나씩 입력하세요(양수) : 10
배열에 입력할 정수를 하나씩 입력하세요(양수) : 5
배열에 입력할 정수를 하나씩 입력하세요(양수) : 4
배열에 입력할 정수를 하나씩 입력하세요(양수) : 3
입력한 모든 정수 중에서 가장 큰 값은 : 10입니다.
```
+ 배열은 다음과 같이 선언하여 생성한다 **int[] array = new int[100];**
+ **Scanner scanner = new Scanner(System.in);** 값을 입력받아 scanner 라는 변수에 저장한다.
+ **int number = scanner.nextInt();** number 변수를 입력받은 값이 저장된 scanner 값으로 초기화한다.
   + 사용자가 입력한 값은 최종적으로 number에 저장되어진다.
+ **int[] array = new int[number];** 배열은 number의 값과 같은 크기로 만들어지게 된다.
+ **for(int i = 0; i < number; i++)** 배열은 0부터 시작되기 때문에 i를 0으로 초기화하고 <= 이 아닌 <로 한다.
+ **array[i] = scanner.nextInt();** 배열의 0번째 부터 값을 입력받아 넣어준다.
+ max 함수를 실행할때 result 값이 -1인 이유는 입력받은 값(정수)들보다 무조건 작아야 되기 때문이다.
   + i(배열의 인덱스) 값이 하나씩 증가하면서 max 함수에 의해 처리(비교)된다.
   + -1:7 -> 7:10 -> 10:5 ···
---
> 코드_랜덤 정수 100개의 평균을 구하는 프로그램
```java
public class Main {
	
	public static void main(String[] args) {
		
		int array[] = new int[100];
		for(int i = 0; i < 100; i++)
		{
			array[i] = (int) (Math.random() * 100 + 1);
		}
		int sum = 0;
		for(int i = 0; i < 100; i++)
		{
			sum += array[i];
		}
		System.out.println("100개의 랜덤 정수의 평균 값은 " + sum / 100 + "입니다.");
	}
}
```
> 출력
```
100개의 랜덤 정수의 평균 값은 51입니다. // 50에 가까운 평균값이 랜덤하게 나옴
```
+ **int array[] = new int[100];** 크기 100의 배열을 만들어준다.
+ **(Math.random() * 100 + 1)** -> (0 ~ 0.xxx 까지의 랜덤수 * 100 + 1) -> 0 ~ 100.xxx까지의 랜덤수+1 -> 1 ~ 101.xxx 까지의 랜덤수
   + 앞에 **(int)** 가 붙어 정수형만 배열에 담겨지게 된다.
+ **sum += array[i];** sum에 모든 배열의 원소를 더한다.
