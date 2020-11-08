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
---

```
mysql> USE opentutorials;
```
+ 표를 사용하기 위한 명령어
