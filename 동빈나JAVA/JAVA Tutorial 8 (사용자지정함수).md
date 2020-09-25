> 코드_3개의 수 최대공약수 구하기
```java
public class Main {
	
	// 반환형, 함수명, 매개변수
	public static int function(int a, int b, int c) {
		int min;
		if(a > b)
		{
			if(b > c)
			{
				min = c;
			}
			else
			{
				min = b;
			}
		}
		else
		{
			if(a > c)
			{
				min = c;
			}
			else
			{
				min = a;
			}
		}
		for(int i = min; i > 0; i--)
		{
			if(a % i == 0 && b % i == 0 && c % i == 0)
			{
				return i;
			}
		}
			
		return -1;
	}
	
	public static void main(String[] args) {
		
		System.out.println("(400, 300, 750)의 최대 공약수 : " + function(400,300,750));
		
	}

}
```
> 출력
```
(400, 300, 750)의 최대 공약수 : 50
```
+ 함수는 public static 쓰고 나서 반환형, 함수이름, 매개변수를 써주면 된다.
+ 우선 위 코드는 3가지 정수 중 가장 작은 정수를 구하고 그 최소값으로 3가지 수를 모두 0이 나올때까지 -1 해가면서 반복해 최대공약수를 구하는 방법이다.
   + 3가지 수의 최소값을 구한 뒤 -1 ㅎ가면서 모두 0이 나올때까지 나누기 한다는게 아주 낯설다.
+ / 대신 %를 쓰는 이유는 나머지가 0이어야 되기 때문이다. (/는 몫의 값만 구해진다)
