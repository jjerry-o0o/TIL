> 코드_입출력
```
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		System.out.print("정수를 입력하세요 : ");
		int i = sc.nextInt();
		System.out.println("입력된 정수는 " + i + "입니다.");
		sc.close();
	}

}
```
> 출력
```
정수를 입력하세요 : 5
입력된 정수는 5입니다.
```
+ **Scanner sc = new Scanner(System.in);** 에서 **sc**는 변수이름 **new Scanner(System.in)** 는 초기화해준 값, **(System.in)** 은 입력받게되는 값을 의미한다.
+ Scanner는 자바에서 제공하는 library에 있기 떄문에 가져오기 위해서 import를 해줘야 한다.
+ Scanner는 하나의 클래스로 볼수 있고, 때문에 함수를 가지고 있다
+ **sc.nextInt()** 는 입력받은 값을 i에 넣겠다는 뜻이다
+ 끝에 **sc.close();** 를 넣어줌으로써 입출력 및 프로그램을 종료해준다.

> 코드_file 입출력
```
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		File file = new File("input.txt");
		try {
			Scanner sc = new Scanner(file);
			while(sc.hasNextInt())
			{
				System.out.println(sc.nextInt() * 100);
			}
      sc.close();
		} catch (FileNotFoundException e) {
			System.out.println("파일을 읽어오는 도중에 오류가 발생했습니다.");
		}

	}

}
```
> File(input.txt)
```
70 580 30 102 503
```
> 출력
```
7000
58000
3000
10200
50300
```
+ File과 Scanner를 클래스로 보기 때문에 import를 해준다.
+ **File file = new File("input.txt");** file변수가 input.txt 를 읽어와서 처리한다라는 의미
+ new Scanner(file) 에 **file** 이 들어가는 이유는 file이 가진 값을 입력받을 것이기 때문
+ **FileNotFoundException** 파일을 읽어올수 없을때의 예외처리를 필수적으로 정의를 해줘야함 **try/catch** 문 사용
