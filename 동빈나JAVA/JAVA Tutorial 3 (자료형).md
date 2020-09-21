### 동빈나 JAVA Tutorial - 3
> 자료형 (data type)
+ 원시 자료형
   - boolean
   - char
   - byte
   - short
   - int
   - long
   - float
   - double
+ 비원시 자료형
   - string
   - array
   - etc.
---
> 코드_평균 구하기
```
public class Main {

	public static void main(String[] args) {

		double a = 10.3;
		double b = 9.6;
		double c = 10.1;
		
		System.out.println((a + b + c) / 3);
		
	}

}
```
> 출력
```
10.0
```
---
> 코드_아스키코드 출력
```
public class Main {

	public static void main(String[] args) {

		for(char i = 'a'; i <= 'z'; i++)
		{
			System.out.println(i + " ");
		}
		
	}

}
```
> 출력
```
a b c d e f g h i j k l m n o p q r s t u v w x y z 
```
+ 반복문인 **for()** 문을 사용했다.
---
> 코드_10진수,8진수,16진수
```
public class Main {

	public static void main(String[] args) {

		int a = 200;
		
		System.out.println("10진수 : " + a);
		System.out.format("8진수 : %o\n", a);
		System.out.format("16진수 : %x", a);
		
	}

}
```
> 출력
```
10진수 : 200
8진수 : 310
16진수 : c8
```
+ __%o__ 는 형식지정자로 a의 값을 8진수 정수로 바꾸어준다.
+ __%x__ 는 형식지정자로 a의 값을 16진수 정수로 바꾸어준다.
+ __\n__ 은 줄바꿈을 의미한다.
---
> 코드_string의 substring 함수
```
public class Main {

	public static void main(String[] args) {

		String name = "Jhon Doe";
		System.out.println(name);
		System.out.println(name.substring(0, 1));
		System.out.println(name.substring(3, 6));
		System.out.println(name.substring(5, 8));
		System.out.println(name.substring(0, 4));
		
	}

}
```
> 출력
```
Jhon Doe
J
n D
Doe
Jhon
```    
+ __substring__ 은 string의 함수이다.
+ __name.substring(5, 8)__ 의 (5, 8)은 5번째 문자부터 8번째까지를 뜻한다.
