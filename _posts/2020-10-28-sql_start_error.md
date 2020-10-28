---
title :  "Mysql 접속오류"
categories : sql
   
---

<br/>
<br/>
<br/>
<br/>
#mysql 실행시 오류

ERROR 2003 (HY000): Can'y connect to MySQL server on 'localhost' (10061) 

이런 메세지가 뜨며 MYSQL 커널이 열리지 않는 문제가 발생했다.

root계정으로 들어가서 비밀번호가 다 일치하는 데 계속 입력할 때마다 강제 종료당하던가 오류메세지로 거부당한다. 

#해결방법

서비스 -> MYSQL 찾아서 시작 -> (비밀번호 오류 시) 커널에<br/> ```mysqld --skip-grant-tables``` <br/> -> ```mysql -u root mysql``` (접속완료) ->
```update user set authentication_string=password('my_password') where user='root';``` <br/> 

이 과정으로 꺼져있는 sql서버를 시작하고 들어가서 비번없이 접속이 가능하다. 
<br/>
<br/>
<br/>
<br/>
<br/>

**오늘의 교훈 : 꺼진 sql도 다시보고 오류문을 잘 읽자.**

