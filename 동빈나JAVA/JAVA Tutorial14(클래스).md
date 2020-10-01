> 클래스_객체 지향의 기본
>>+ 클래스는 객체 지향 프로그래밍에 있어 가장 기본이 된다.
>>+ 가장 대표적으로 많이 사용되는것이 Node클래스이다. (아마도 좌표를 사용할때?)
>>+ ex)자동차를 만든다고 할때 필요한 것들(색상,속력,좌석수 등)을 따로 클래스라는 곳에 만들어 놓고,
    Main 함수에서는 각 그것들(함수?변수?)을 사용하기만 하는걸 말하는것 같다.
    
> 코드_두 점 사이의 중점을 구하는 프로그램
>> Node
```java
public class Node {

	private int x;
	private int y;
	
	public int getX() { //private에 있는 x의 값을 가져오는 함수
		return x;	
	}
	
	public void setX(int x) { //x 값에 입력받은 매개변수 x값을 넣어주는 함수 
		this.x = x;
	}
	
	public int getY() {
		return y;
	}
	
	public void setY(int y) {
		this.y = y;
	}
	
	public Node(int x, int y) { //생성자. 값을 지정해주는 함수. 클래스와 동일한 이름을 갖는다.
		this.x = x;
		this.y = y;
	}
	
	public Node getCenter (Node other) { //getCenter를 사용하여 다른 Node와 비교해서 정중앙을 구한다.
		return new Node ((this.x + other.getX()) / 2, (this.y + other.getY()) / 2);
		//다른 node에 있는 x값, y값이랑 더하고 2로 나눠 정중앙 값을 구한다.
	}
}
```
+ Node라는 클래스의 특성상 변수 x와 y를 사용했다.(좌표를 나타냄)
+ 보안이 중요하기 때문에 private 형태로 만들어준다.
+ **public int getX()** 을 사용하여 x값을 가져와 사용할 수 있도록 해준다.
+ **public void setX(int x)** x 값을 정의해주는 부분으로 **this.x = x;** 는 x 값을 매개변수 값 x로 바꿔주는것을 의미한다.
+ 생성자를 만들어 준다 -> **public Node(int x, int y)**
+ 생성자는 x와 y의 값을 초기화 해주는 역할을 한다.
+ **public Node getCenter (Node other)** 기존 Node의 x,y을 다른 Node의 x,y 값과 비교하는 부분이다.

>> Main
```java
public class Main {

	public static void main(String[] args) {
		
		Node one = new Node(10, 20);
		Node two = new Node(30, 40);
		Node result = one.getCenter(two);
		System.out.println("x : " + result.getX() + ", y : " + result.getY());
	
	}
}
```
+ 두점의 값을 입력해서 실행하는 부분
+ **one.getCenter(two)** 두 좌표를 비교하는 함수를 실행시키는 부분

> 출력
```
x : 20, y : 30
```
+ 정말 솔직히 두루뭉실하게만 이해가 된다. 그 이유는 익숙치 않은 처음보는 개념들이 많이 나왔기 때문이다.
+ 대충 그런가보다 하고 넘어가기로 했다. (상속 다보고 왔는데도 뭔가 이해가 잘 안되는게 있다)
