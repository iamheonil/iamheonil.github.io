---

layout: post
comments : true
title: 'JDBC, Java DataBase Connectivity란'
subtitle: 'JDBC, Java DataBase Connectivity'
date: 2020-05-14
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 117

---

> JDBC, Java DataBase Connectivity

<br>

- 자바에서 데이터베이스에 접속/관리할 수 있게 해주는 드라이버(API)
- 자바로 작성된 프로그램으로 DB와 관련된 작업을 처리할 수 있도록 제공되는 기능(코드)들을 모아놓은 것
- OJDBC - Oracle 에서 제공하는 오라클 DB를 관리할 수 있도록 도와주는 JDBC이다.

<br>

OJDBC & Oracle 버전

- OJDBC6 - JDK 6 이상 - 오라클 11gR2 -- 나는 이것을 사용한다.
- OJDBC5 - JDK 5 이상
- OJDBC14 - JDK 1.4 이상
- OJDBC13 - JDK 1.3 이상
- OJDBC12 - JDK 1.2 이상

<br>

> 자바 프로젝트에 OJDBC 설치하기(적용하기)

<br>

1. Dynamic Web Project에서 ojdbc6.jar 를 복사하여 추가한다.
   - WebContent\WEB-INF\lib\ 폴더에 ojdbc6.jar 파일을 복사, 붙여넣기 -> 자동으로 연결된다.
2. 자바프로젝트에서 라이브러리로 ojdbc6.jar 선택하여 추가하기
   - 프로젝트 이름에서 우클릭
   - Build Path - Configure Build Path... 클릭
   - Libraries 탭 선택
   - 오른쪽 버튼 중에서 ADD JARs 버튼 (프로젝트 파일 내에 경로와 파일을 선택)
   - 오른쪽 버튼 중에서 ADD External JARs 버튼 (프로젝트 밖 파일)
     - 되도록 첫번째 방법인 ADD JARs 로 해결하는것이 바람직하다.

<br>

> JDBC 사용 방법

<br>

   	1. JDBC 드라이버를 로드한다.
   	2. DB 접속(연결, Connection)
   	3. SQL 쿼리 수행
   	4. 조회된 결과 처리
   	5. 연결 종료

<br><br>