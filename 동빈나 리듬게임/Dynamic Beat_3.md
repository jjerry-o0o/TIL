### 인트로 음악 삽입하기

> Dynamic Beat
>> DynamicBeat.java
```java
package dynamic_beat_3;

import java.awt.Graphics;
import java.awt.Image;

import javax.swing.ImageIcon;
import javax.swing.JFrame;

public class DynamicBeat extends JFrame {
	
	private Image screenImage;
	private Graphics screenGraphic; //더블버퍼링을 하기 위해서 전체 화면에 대한 이미지를 담는 인스턴스
	
	private Image introBackground; //introBackground.jpg 파일을 담는 객체
	
	public DynamicBeat() { //생성자
		setTitle("Dynamic Beat");
		setSize(Main.SCREEN_WIDTH, Main.SCREEN_HEIGHT);
		setResizable(false);
		setLocationRelativeTo(null);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setVisible(true);
		
		introBackground = new ImageIcon(Main.class.getResource("../images/introBackground.jpg")).getImage();
		// introBackground 라는 변수에 (메인클래스에서 리소스를 가져와서(../경로에 있는))이미지 파일 초기화하는 부분
		Music introMusic = new Music("introMusic.mp3", true);
		introMusic.start();
	}
	
	public void paint(Graphics g) { //메소드,함수
		screenImage = createImage(Main.SCREEN_WIDTH, Main.SCREEN_HEIGHT); //1280*720 사이즈의 이미지를 만들어 screenImage에 넣어준다.
		screenGraphic = screenImage.getGraphics(); //그래픽 개체를 얻어온다.
		screenDraw(screenGraphic); //이미지를 그려준다
		g.drawImage(screenImage, 0, 0, null); //0,0의 위치에 그려준다
	}
	
	public void screenDraw(Graphics g) { //메소드,함수
		g.drawImage(introBackground, 0, 0, null); //이미지파일을 screenImage의 0,0의위치에 이미지를 그려준다
		this.repaint(); //paint 함수를 다시 해줌으로써 그림을 계속 그려준다..?
	}

}
```
>> Music.java
```java
package dynamic_beat_3;

import java.io.BufferedInputStream;
import java.io.File;
import java.io.FileInputStream;

import javazoom.jl.player.Player;

public class Music extends Thread {
	
	private Player player;
	private boolean isLoop;
	private File file;
	private FileInputStream fis;
	private BufferedInputStream bis;
	
	public Music(String name, boolean isLoop) {
		try {
			this.isLoop = isLoop;
			file = new File(Main.class.getResource("../music/" + name).toURI());
			fis = new FileInputStream(file);
			bis = new BufferedInputStream(fis);
			player = new Player(bis);
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}
	}
	
	public int getTime() {
		if (player == null)
			return 0;
		return player.getPosition();
	}
	
	public void close() {
		isLoop = false;
		player.close();
		this.interrupt();
	}
	
	@Override
	public void run() {
		try {
			do {
				player.play();
				fis = new FileInputStream(file);
				bis = new BufferedInputStream(fis);
				player = new Player(bis);
			} while (isLoop);
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}
	}
	

}
```
>> Main.java
```java
  package dynamic_beat_3;

public class Main {
	
	public static final int SCREEN_WIDTH = 1200;
	public static final int SCREEN_HEIGHT = 720; //상수는 대문자를 사용

	public static void main(String[] args) {
		
		new DynamicBeat();

	}

}

```
- 여기까지 다 했는데 에러가 떠버렸다. 그래도 실행은 된다.
- 에러유형 **'The type java.lang.Object cannot be resolved. it is indirectly referenced from required. class files**
  - 구글에 찾아보니 컴파일 환경이 잡히지 않아서...? Java Build Path 에 들어가서 jr 어쩌구의 위치를 잘 잡아줘야 하는 것 같다.
  - 근데 나도 하려구 했는데 적용이 안된다!!! 
---
- 위에 에러 고쳤는데 이젠 다른게 안된다.
  - java.lang.ClaxxNotFoundException 아니 사람들이 고치라는 방법 다해봤는데도 오류가 안고쳐진다;
