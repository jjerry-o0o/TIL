### DATABASE - MySQL
+ 데이터를 관리해주는 프로그램을 데이터베이스라 한다.
+ 데이터베이스에는 관계형과 관계형이 아닌 그외 많은 것들이 있다.
+ SQL (Structured Query Language)

```
mysql> -uroot -p
```
+ -u 는 user를 의미한다
+ root 는 유저이름이기도 하고 전체 권한을 가진 관리자를 뜻한다.
+ -p 는 패스워드 이다.
+ 데이터베이스 서버에 들어온 단계
---

```
mysql> CREATE DATABASE opentutorials;
```
+ 데이터베이스/스키마 를 만드는 단계
+ 여기선 명령어를 모두 대문자로 쓰는듯 하다.
+ 명령어 끝에 세미콜론(;)은 필수다.
---

```
mysql> DROP DATABASE opentutorials;
```
+ 데이터베이스/스키마 를 삭제하는 명령어
+ 기존에 사용했던 명령어를 다시 사용할때 방향키 ↑를 눌러 불러올수 있다.
---

```
mysql> SHOW DATABASES;
```
+ 스키마를 보여지게 하는 명령어
+ DATABASES 로 복수형으로 적어준다
+ 아주 귀여운 표가 출력되는데 ...
+ ![.mysql](./DATABASE/2020-11-08 mysql.png)
  + 왜 나는 이미지 첨부가 안되는 걸까! ㅠ
---

```
mysql> USE opentutorials;
```
+ 표를 사용하기 위한 명령어
---

2020.11.09
```
$ mysql -uroot
mysql> USE opentutorials;
mysql> CREATE TABLE topic(
        id INT(11) NOT NULL AUTO_INCREMENT,   //c1 datatype(lenth) 의 형식으로 입력.
        title VARCHAR(100) NOT NULL,
        description TEXT NULL,
        created DATETIME NOT NULL,
        author VARCHAR(30) NULL,
        profile VARCHAR(100) NULL,
        PRIMARY KEY(id));
```
+ topic 이라는 이름의 테이블을 만든다
+ c1 datatype(lenth) 라는 형식으로 column(열,세로행)을 만들어준다.
  + c1 = 행의 이름 / datatype = 문자(TEXT,CHAR),정수(INT) 등 / (lenth) = 화면에 보여질 값의 길이
+ NOT NULL = 공백이 없게 한다. 는 것으로 꼭 값을 넣어야 되는 것을 뜻함
  + NULL = 공백 허용
+ AUTO_INCREMENT = 자동으로 id 값이 +1 되게 하는 것
+ PRIMARY KEY(id) = topic 이라는 테이블의 id 값이 메인키라는 것을 알려준다.
  + ex)각각의 행을 식별해야 할 때  id 값이 중복 되어지는 것을 막아준다.
