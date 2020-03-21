---

layout: post
comments : true
title: '오라클 11g R2 Express Edition 설치'
subtitle: ''
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 37

---

 

> 오라클 11g R2 Express Edition

(https://www.oracle.com)[오라클 홈페이지]

- DataBase

- 메뉴에서 Download 선택 -> Database 항목 선택
  - ('Download -> Customer Downloads -> DataBase -> 11g Release 2')
  - [Oracle Database 11g R2 Express](https://www.oracle.com/database/technologies/xe-prior-releases.html)
  - 제일 아래로 내려가 Oracle Database 11g R2 Express Edition for Windows x64 클릭
  - 라이센스 항목 체크하고 동의, 로그인 후 다운로드 시작

<br>

- 설치 완료 후 SQLDeveloper 설치
  - 메뉴에서 Download 선택 -> Database 항목 선택
  - ('Download -> Customer Downloads -> Developer Tools  -> SQL developer')
  - [SQL Developer 다운로드 목록 페이지](https://www.oracle.com/tools/downloads/sqldev-downloads.html)
  - Windows 64-bit with JDK 8 included 다운로드

<br>

오라클 DBMS 설치 확인

- 윈도우 콘솔창(CMD) 열기
- sqlplus /nolog 입력
- conn sys as sysdba - Enter Password - show user 순차적으로 입력하여 확인해보기
- USER is "SYS" 라고 출력 되면 설치 완료.
- conn system/1234 입력 - show user
- USER is "SYSTEM" 확인하기
- @ 만 콘솔창에 쓰되, 엔터는 누르지 말고
- C:\oraclexe\app\oracle\product\11.2.0\server\rdbms\admin 로 이동 Scott.sql 을 찾아 드래그 하여 커멘드창에 넣고 엔터.
- ALTER USER scott IDENTIFIED BY tiger;
- conn scott/tiger;
- show user -> USER is "SCOTT" 나오는 것 확인.
- SELECT * FROM dept; 입력 후 부서 정보가 나오는 것 확인.

<br>

정상 확인 후 SQL Developer 설정하기

- 실행 후 파일 - 새로 만들기 - 모든 항목 - 데이터베이스 접속(접속
- Name : Web 
- 사용자 이름 scott 
- 비밀번호 tiger
- 접속

<br>

오라클은 설치하게 된다면 부팅시 자동으로 프로세스에 올라가는데 이것이 성능 저하를 유발한다.

그래서 부팅시 오라클 서비스를 자동으로 켜지지 않게 설정 해주는 작업을 한다.

- 실행 - services.msc(서비스)
- OreacleServiceXE, OracleXETNSListener 두 개를 각각
- 더블클릭 - 시작유형 - 자동 - 수동으로 변경해준다.

설정을 마친 뒤 오라클 DB를 사용하려면 "Start Database" 프로그램 실행해야 함.

Start Database는 시작메뉴 - Oracle 시작메뉴 찾기 - Start Database, Stop Database 두 개가 동작을 제어한다.

도구 - 환경설정 - 글꼴 검색 - 글꼴 크기, 서체 수정

<br>

오라클 클라이언트 툴

- SQL * PLUS
  - Oracle DBMS에서 제공하는 기본 도구 Tool
  - 별도의 설치없이 사용 가능
  - CLI 환경 (Command Line Interface)
  - 윈도우 콘솔창(CMD)에서 sqlplus 라고 입력하거나 설치파일에서 run SQL Command Line 실행
  - 빠르지만 다루기가 쉽지 않다.
- SQL * Developer
  - 오라클에서 제공하는 추가적인 클라이언트 Tool
  - GUI(Graphical User Interface)환경


<br><br>