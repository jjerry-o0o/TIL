> Dynamic Beat
>> DynamicBeat.java
```java
package dynamic_beat_2;

import java.awt.Graphics;
import java.awt.Image;

import javax.swing.ImageIcon;
import javax.swing.JFrame;

public class DynamicBeat extends JFrame {
	
	private Image screenImage;
	private Graphics screenGraphic; //더블버퍼링을 하기 위해서 전체 화면에 대한 이미지를 담는 인스턴스
	
	private Image introBackground; //introBackground.jpg 이미지 파일을 담는 객체
	
	public DynamicBeat() { //생성자
		setTitle("Dynamic Beat");
		setSize(Main.SCREEN_WIDTH, Main.SCREEN_HEIGHT);
		setResizable(false);
		setLocationRelativeTo(null);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setVisible(true);
		
		introBackground = new ImageIcon(Main.class.getResource("../images/introBackground.jpg")).getImage();
		// introBackground 라는 변수에 (메인클래스에서 리소스를 가져와서(../경로에 있는))이미지 파일 초기화하는 부분
	}
	
	public void paint(Graphics g) { //메소드,함수
		screenImage = createImage(Main.SCREEN_WIDTH, Main.SCREEN_HEIGHT); //1280*720 사이즈의 이미지를 만들어 screenImage에 넣어준다.
		screenGraphic = screenImage.getGraphics(); //그래픽 개체를 얻어온다.
		screenDraw(screenGraphic); //이미지를 그려준다(아래에 있는 함수)
		g.drawImage(screenImage, 0, 0, null); //0,0의 위치에 그려준다
	}
	
	public void screenDraw(Graphics g) { //메소드,함수
		g.drawImage(introBackground, 0, 0, null); //이미지파일을 screenImage의 0,0의위치에 이미지를 그려준다
		this.repaint(); //paint 함수를 다시 실행해줌으로써 그림을 계속 그려준다..?
	}

}
```
>> Main.java
```java
  package dynamic_beat_2;

public class Main {
	
	public static final int SCREEN_WIDTH = 1200;
	public static final int SCREEN_HEIGHT = 720; //상수는 대문자를 사용

	public static void main(String[] args) {
		
		new DynamicBeat();

	}

}

```

- 배경화면에 쓰인 이미지는 wallpaperswide/com 에서 다운받았다
- 더블버퍼링이란 프로그램 기법을 사용했다.
  - 내가 이해하기론 원래는 앞 화면에서 바로 이미지를 띄워 로딩이 보여지는데 이걸 막기 위해 뒤 화면에서 미리 따로 이미지를 준비하고 앞 화면엔 로딩이 끝난 화면에 보여지도록 하는..? 그런 개념이었다.
  - 게임 등에 자주 사용되는 기법이다
- **public void paint(Graphics g)** 에서 paint라는 함수는 JFrame을 상속받은 GUI 게임에서 가장 첫번째로 화면을 그려주는 함수로 약속 되어있고 바뀌지 않는다.

