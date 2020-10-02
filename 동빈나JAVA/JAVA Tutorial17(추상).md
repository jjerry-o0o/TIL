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
+ 
