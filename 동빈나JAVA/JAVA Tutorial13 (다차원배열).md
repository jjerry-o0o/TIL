> 코드_10*10 배열에 0~10 정수 랜덤 데이터를 넣고 배열 출력
```java
public class Main {

	public static void main(String[] args) {
		
		int N = 10;
		int[][] array = new int[N][N];
		for(int i = 0; i < N; i++)
		{
			for(int j = 0; j < N; j++)
			{
				array[i][j] = (int)(Math.random() * 10);
			}
		}
		for(int i = 0; i < N; i++)
		{
			for(int j = 0; j < N; j++)
			{
				System.out.print(array[i][j] + " ");
			}
			System.out.println();
		}
	}
}
```
> 출력
```
5 4 6 0 4 3 9 7 3 4 
5 1 3 4 0 3 5 1 6 4 
7 5 5 1 1 1 0 9 4 6 
5 2 3 2 7 1 7 2 5 4 
4 5 2 3 3 5 6 5 9 0 
6 5 2 6 9 5 9 4 4 0 
9 2 0 7 1 4 4 2 1 3 
0 5 3 0 6 0 1 5 0 3 
6 8 3 0 9 7 5 8 1 2 
4 6 8 8 1 6 5 0 9 0
```
+ int N 은 행과 열의 길이이다.
+ 다차원 배열 만드는 문법 **int[][] array = new int[N][N];**
+ 두개의 이중for문으로 행과 열을 처리할 수 있도록 한다 (별찍기 원모양에서도 나왔던거)
+ 0 ~ 9까지의 랜덤 정수를 넣기 때문에 10을 곱하고 1은 더하지 않는다. 
+ 행(가로) 부분에서만 정수를 입력하고 열(세로)은 줄바꿈만 진행한다.
+ 위의 이중for문에서 값을 입력받아 배열을 만들고 아래 이중for문에서 배열을 화면에 출력한다.
