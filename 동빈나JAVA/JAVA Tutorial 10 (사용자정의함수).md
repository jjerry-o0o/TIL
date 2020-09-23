> 문제_약수중 k번째로 작은 수 찾기
>> 생각해보기,미리 정리해보기 (강의 한번 본 상태)
>>+ A라는 수와 k번째에 들어갈 k값을 매개변수로 받는 함수 만들기
>>+ A 값의 약수 구하기 - A 값을 나눴을때 나머지가 0으로 떨어지는 수 구하기 (for문 사용/i값 사용)
>>+ i값(약수)가 구해질 때마다 k값 카운팅(k--)
>>+ return i..?

> 코드
```
public class Main {

	public static int function(int number, int k) {
		for(int i = 1; i <= number; i++)
		{
			if(number % i == 0)
			{
				k--;
				if(k == 0)
				{
					return i;
				}
			}
		}
		return -1;		
	}
	
	public static void main(String[] args) {
		int result = function(3050, 10);
		if(result == -1)
		{
			System.out.println("3050의 10번째 약수는 없습니다.");
		}
		else
		{
			System.out.println("3050의 10번째 약수는 " + result + "입니다.");
		}	
	}
}
```
> 출력
```
3050의 10번째 약수는 610입니다.
```
+ **for(int i = 1; i <= number; i++)** 는 i라는 약수를 구하는 반복문이다
+ **if(number % i == 0)** 몫의 값이 구해지는 / 나누기 대신 나머지값이 구해지는 % 나누기를 사용한다.
+ **System.out.println("3050의 10번째 약수는 " + result + "입니다.");** 에서 i가 아닌 result를 넣는 이유는 아마도 i가 function 함수에서만 사용하는 변수이기 때문이다.
---
> 문제_문자열에서 마지막 단어를 반환하는 함수 만들기
>> 생각해보기 (영상보기전)
>>+ 문자열을 매개변수로 받는 함수 만들기?
>>+ string 자료형 강의때 나온 substring 함수 사용..?
>>+ 글자수 세는 변수를 만드나?

> 코드
```
public class Main {

	public static char function(String input) {
		return input.charAt(input.length() -1);
	}
	
	public static void main(String[] args) {
		System.out.println("Hello World의 마지막 단어는 " + function("Hello World"));
	}
}
```
> 출력
```
Hello World의 마지막 단어는 d
```
+ string은 내부적으로 다양한 함수를 가지고 있다.
+ **charAt** 라는 함수는 n번째의 글자를 하나 가져오는 함수이다.
+ **charAt(input.length() -1)** -> input이라는 변수에 들어간 문장의 길이에서 -1을 한 위치의 글자를 하나 가져온다.
+ 위에서 -1을 한 이유는 **charAt** 함수가 문장을 0부터 세기 때문
---
> 코드_가장 큰 값 구하기_max()함수 이용
```
public class Main {

	public static int max(int a, int b) {
		return (a > b) ? a : b;
	}
	
	public static int function(int a, int b, int c) {
		int result = max(a, b);
		result = max(result, c);
		return result;
	}

	public static void main(String[] args) {
		
		System.out.println("(345, 567 789) 중에서 가장 큰 값은" + function(345, 567, 789));
		
	}
}
```
> 출력
```
(345, 567 789) 중에서 가장 큰 값은789
```
+ 3항 연산자 (조건 ? 참 : 거짓) 이용
+ 3항 연산자를 이용한 함수를 활용해서 a,b,c 수를 a : b 비교하고, b : c 비교해서 가장 큰 수 찾기
