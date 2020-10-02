> 추상(absreact)
+ 미완성 클래스이다
+ 새로운 클래스를 작성하는데 밑바탕이 되어준다.

> Player_abstract
```java
abstract class Player { // abstract를 써줌으로써 추상 클래스라는 것을 알려준다.
	abstract void play(String songName);
	abstract void pause();
	abstract void stop();
}
```
> Main
```java
public class Main extends Player {

	public static void main(String[] args) {
		Main main = new Main();
		main.play("Joakim Karud - Mighty Love");
		main.pause();
		main.stop();
	}

	@Override
	void play(String songName) {		
		System.out.println(songName + " 곡을 재생합니다. ");		
	}

	@Override
	void pause() {
		System.out.println("곡을 일시정지합니다. ");	
	}

	@Override
	void stop() {
		System.out.println("곡을 정지합니다.");
	}
}
```
+ Player를 상속 받을수 있게 한다 **extends Player**
  + 느낌표가 생기는데 이는 Add unimplemented methods를 클릭한다.
  + 아직 구현되지 않은 함수들을 구현할 것을 의미한다.(Player 추상클래스의 method들)
+ **Main main = new Main();** 이부분은 완벽하게 이해되진 않았지만.
  + Main 함수에서는 static 형태인 것만 사용할 수 있는데 Player 추상클래스에서 온 애들은 static이 아니라서 아예 main 이라는 instance를 만들어주고 그걸로 사용하는것 같다. 잘 모르겠다.
> 출력
```
Joakim Karud - Mighty Love 곡을 재생합니다. 
곡을 일시정지합니다. 
곡을 정지합니다.
```
-----------------------
> Animal_abstract'
```java
abstract class Animal {
	abstract void crying();
}
```
> Dog_extends Animal
```java
public class Dog extends Animal {

	@Override
	void crying() {
		System.out.println("월! 월!");	
	}
}
```
> Cat_extends Animal
```java
public class Cat extends Animal {

	@Override
	void crying() {
		System.out.println("냐오옹~");
	}
}
```
> Main
```java
public class Main {

	public static void main(String[] args) {

		Dog dog = new Dog();
		Cat cat = new Cat();
		dog.crying();
		cat.crying();	
	}	
}
```
+ Animal을 상속받은 모든 클래스들은 crying 함수를 반드시 실행해야한다.
+ Dog와 Cat은 crying을 구현한다.
+ 위에서도 그렇고 여기서도 그렇고 instace 가 이해되지 않았었는데 [생활코딩](https://www.youtube.com/watch?v=Y370ydbIb7Y) 강좌보고 이해가 됐다.
  + dog라는 변수에 기존에 만들어둔 Dog라는 함수를 복제해서 넣는 것을 의미한다 **Dog dog = new Dog();**
  + 나선생님 강좌에서 이런거 써먹은적이 어디있었던가 하면서 찾다보니 scanner 가 같은 구조였다. **Scanner sc = new Scanner(System.in);**
  + 이걸 이해하고 나니 scanner 에서 나왔던 다른 코드들도 더욱 잘 이해됐다. ex)sc.nextInt(); , sc.close();
> 출력
```
월! 월!
냐오옹~
```
+ 아주 귀엽다.
