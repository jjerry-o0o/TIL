> Teacher (Person을 상속받는 클래스)
```java
public class Teacher extends Person {

	private String teacherID;
	private int monthSalary;
	private int workedYear;
	
	public String getTeacherID() {
		return teacherID;
	}
	public void setTeacherID(String teacherID) {
		this.teacherID = teacherID;
	}
	public int getMonthSalary() {
		return monthSalary;
	}
	public void setMonthSalary(int monthSalary) {
		this.monthSalary = monthSalary;
	}
	public int getWorkedYear() {
		return workedYear;
	}
	public void setWorkedYear(int workedYear) {
		this.workedYear = workedYear;
	}
	
	public Teacher(String name, int age, int height, int weight, String teacherID, int monthSalary, int workedYear) {
		super(name, age, height, weight);
		this.teacherID = teacherID;
		this.monthSalary = monthSalary;
		this.workedYear = workedYear;		
	}

	public void show() {
		System.out.println("----------------------");
		System.out.println("교사 이름 : " + getName());
		System.out.println("교사 나이 : " + getAge());
		System.out.println("교사 키 : " + getHeight());
		System.out.println("교사 몸무게 : " + getWeight());
		System.out.println("교직원 번호 : " + getTeacherID());
		System.out.println("교사 월급 : " + getMonthSalary());
		System.out.println("교사 연차 : " + getWorkedYear());		
	}	
}
```
+ Teacher 클래스에서 사용할 변수를 private 로 만든다.(teacherID, monthSalary, workedYear)
+ 자동으로 get 함수, set 함수를 만들어준다.
+ 자동으로 생성자도 만들어준다.
+ 출력해주는 함수도 만들어준다. **public void show()**

> Main
```java
public class Main {

	public static void main(String[] args) {
		
		Teacher teacher1 = new Teacher("John Doe", 25, 180, 120, "ABC201", 3000000, 5);
		teacher1.show();
	}
}
```
> 출력
```
----------------------
교사 이름 : John Doe
교사 나이 : 25
교사 키 : 180
교사 몸무게 : 120
교직원 번호 : ABC201
교사 월급 : 3000000
교사 연차 : 5
```
---------------------------------------------------------------
> 상속+배열
>>+ 실제로는 값이 많기 때문에 배열을 많이 사용한다.

> Main_배열추가
```java
public class Main {

	public static void main(String[] args) {
		
		Student[] students = new Student[3];
		for(int i = 0; i < 3; i++) {
			students[i] = new Student("홍길동", 20, 175, 70, i + "", 1, 4.5);
			students[i].show();
		}

	}

}
```
+ 실제 사용시에는 모든 값이 다르겠지만 지금은 학번( **i+""** ) 부분만 값이 바뀌도록 진행하였다.
> 출력
```
---------------------
학생 이름 : 홍길동
학생 나이 : 20
학생 키 : 175
학생 몸무게 : 70
학번 : 0
학년 : 1
학점 : 4.5
---------------------
학생 이름 : 홍길동
학생 나이 : 20
학생 키 : 175
학생 몸무게 : 70
학번 : 1
학년 : 1
학점 : 4.5
---------------------
학생 이름 : 홍길동
학생 나이 : 20
학생 키 : 175
학생 몸무게 : 70
학번 : 2
학년 : 1
학점 : 4.5
```
+ 학번이 모두 다른걸 알 수 있다.
-------------------------------------------------------------
> 코드_사용자로부터 값을 입력받을때
```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		System.out.print("총 몇 명의 학생이 존재합니까? ");
		int number = scan.nextInt();
		Student[] students = new Student[number];
		for(int i = 0; i < number; i++)
		{
			String name;
			int age;
			int height;
			int weight;
			String studentID;
			int grade;
			double gPA;
			
			System.out.print("학생의 이름을 입력하세요 : ");
			name = scan.next();
			System.out.print("학생의 나이를 입력하세요 : ");
			age = scan.nextInt();
			System.out.print("학생의 키를 입력하세요 : ");
			height = scan.nextInt();
			System.out.print("학생의 몸무게를 입력하세요 : ");
			weight = scan.nextInt();
			System.out.print("학생의 학번을 입력하세요 : ");
			studentID = scan.next();
			System.out.print("학생의 학년을 입력하세요 : ");
			grade = scan.nextInt();
			System.out.print("학생의 학점을 입력하세요 : ");
			gPA = scan.nextDouble();
			students[i] = new Student(name, age, height, weight, studentID, grade, gPA);
		}
		for(int i = 0; i < number; i++)
		{
			students[i].show();
		}
	}
}
```
+ 값을 입력받을수 있는 scanner를 사용한다. import도 해준다.
+ 입력받은 값 number 만한 크기의 배열을 만들어준다. **Student[] students = new Student[number];**
+ 배열의 크기만큼 반복하는 반복문을 만든다
  + 반목문 안에서 사용할 모든 변수를 만들어준다.
  + 모든 변수에 값을 입력받아 넣어줄수 있도록 한다.
  + 초기화를 해준다. **Student(name, age, height, weight, studentID, grade, gPA);**
  + 입력받은 값을 배열에 각각의 원소로써 넣어줄 수 있도록 해준다. **students[i] = new Student(---);**
+ 모든 정보를 출력할 수 있도록 한다. **students[i].show();**

> 출력
```
---------------------
학생 이름 : 란제리
학생 나이 : 3
학생 키 : 50
학생 몸무게 : 3
학번 : 20180401
학년 : 3
학점 : 3.7
---------------------
학생 이름 : 김동동
학생 나이 : 2
학생 키 : 70
학생 몸무게 : 5
학번 : 20190713
학년 : 2
학점 : 4.2
---------------------
학생 이름 : 우유
학생 나이 : 2
학생 키 : 120
학생 몸무게 : 7
학번 : 20191225
학년 : 2
학점 : 4.5
```
+ 점점 진도를 나가기 무서워진다...
