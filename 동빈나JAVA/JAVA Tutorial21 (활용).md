> 객체지향 기법의 활용 _ 게임 캐릭터 공격 프로젝트의 구현
>> Hero
```java
public class Hero {
	
	String name;
	
	public Hero(String name) { //생성자 만들기
		this.name = name;
	}
	
	public void attack() {
		System.out.println("주먹 지르기!");
	}

}
```
+ 부모클래스로써 가장 기본적인 틀(함수)을 갖는다
+ Hero 라는 클래스를 초기화 해줄수 있도록 생성자를 만든다
>> Warrior
```java
public class Warrior extends Hero {

	public Warrior(String name) {
		super(name);
	}

	public void groundCutting() {
		System.out.println("대지 가르기!");
	}
}
```
+부모클래스 Hero를 상속받는다.
+ **super(name);** 부모클래스의 변수를 초기화한다.
>> Archer
```java
public class Archer extends Hero {

	public Archer(String name) {
		super(name);
	}

	public void fireArrow() {
		System.out.println("불화살!");
	}
}

```
>> Wizard
```java
public class Wizard extends Hero {

	public Wizard(String name) {
		super(name);
	}

	public void freezing() {
		System.out.println("얼리기!");
	}
}
```
>> Main
```java
public class Main {

	public static void main(String[] args) {
		
		Hero[] heros = new Hero[3]; //배열
		
		heros[0] = new Warrior("전사"); //배열의 초기화, 다형성
		heros[1] = new Archer("궁수");
		heros[2] = new Wizard("마법사");
		
		for(int i = 0; i < heros.length; i++) {
			heros[i].attack();
			
			if(heros[i] instanceof Warrior) {
				Warrior temp = (Warrior) heros[i];
				temp.groundCutting();
			}
			else if(heros[i] instanceof Archer) {
				Archer temp = (Archer) heros[i];
				temp.fireArrow();
			}
			else if(heros[i] instanceof Wizard) {
				Wizard temp = (Wizard) heros[i];
				temp.freezing();
			}
		}
	}
}
```
+ **Hero[] heros = new Hero[3];** heros 라는 3칸짜리 배열을 만들어 준다
+ 배열을 모두 초기화해준다.
+ 반복문을 사용하여 각각의 스킬이 모두 사용될 수 있도록 한다.
+ **Warrior temp = (Warrior) heros[i];** heros[i] 를 Warrior로 형변환 해준후 temp 라는 변수에 넣어준다...?
+ **temp.groundCutting();** groundCutting 함수를 실행한다.
