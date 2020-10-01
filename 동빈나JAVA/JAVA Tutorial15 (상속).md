> 상속
>>+ 다른 클래스가 가지고 있는 정보를 가져와 사용하는 것
>>+ 같은 내용을 번복해서 쓸 필요 없어 효율적이다.

> 코드_Person을 상속받는 Student 클래스를 만들고 이를 이용하여 객체를 생성한다.
>> Person
```java
public class Person {
	
	private String name;
	private int age;
	private int height;
	private int weight;

	 public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
	public int getHeight() {
		return height;
	}
	public void setHeight(int height) {
		this.height = height;
	}
	public int getWeight() {
		return weight;
	}
	public void setWeight(int weight) {
		this.weight = weight;
	}
	
	public Person(String name, int age, int height, int weight) {
		super();
		this.name = name;
		this.age = age;
		this.height = height;
		this.weight = weight;
	}
}
```
+ 언제나 항상 get method와 set method를 가지기 때문에 자동실행으로 진행한다.(source-Generate Getters and Setters...)
+ 생성자도 만들어준다.(Source-Generate Constructors from Superclass...)

>> Student
```java
public class Student extends Person {

	private String studentID;
	private int grade;
	private double GPA;
	
	public String getStudentID() {
		return studentID;
	}
	public void setStudentID(String studentID) {
		this.studentID = studentID;
	}
	public int getGrade() {
		return grade;
	}
	public void setGrade(int grade) {
		this.grade = grade;
	}
	public double getGPA() {
		return GPA;
	}
	public void setGPA(double gPA) {
		GPA = gPA;
	}
	
	public Student(String name, int age, int height, int weight, String studentID, int grade, double gPA) {
		super(name, age, height, weight);
		this.studentID = studentID;
		this.grade = grade;
		GPA = gPA;
	}
	
	public void show() {
		System.out.println("---------------------");
		System.out.println("학생 이름 : " + getName());
		System.out.println("학생 나이 : " + getAge());
		System.out.println("학생 키 : " + getHeight());
		System.out.println("학생 몸무게 : " + getWeight());
		System.out.println("학번 : " + getStudentID());
		System.out.println("학년 : " + getGrade());
		System.out.println("학점 : " + getGPA());
	}	
}
```
+ **extends Person** Person 클래스를 상속받는다는 것을 의미한다.
+ **super(name, age, height, weight);** 부모클래스가 가지고 있는 생성자를 실행하겠다는 것을 의미한다.
+ **public void show()** 출력을 위한 함수

> Main
```java
public class Main {

	public static void main(String[] args) {
		
		Student student1 = new Student("홍길동", 20, 175, 70, "20170101", 1, 4.5);
		Student student2 = new Student("이순신", 30, 170, 80, "20090505", 4, 3.0);
		student1.show();
		student2.show();
	}
}
```
> 출력
```
---------------------
학생 이름 : 홍길동
학생 나이 : 20
학생 키 : 175
학생 몸무게 : 70
학번 : 20170101
학년 : 1
학점 : 4.5
---------------------
학생 이름 : 이순신
학생 나이 : 30
학생 키 : 170
학생 몸무게 : 80
학번 : 20090505
학년 : 4
학점 : 3.0
```
