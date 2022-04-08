---

layout: post
comments : true
title: 'Database DCL'
subtitle: '데이터베이스의 문법 종류 중 하나인 DCL'
date: 2020-04-04
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 74

---

> DCL, Data Control Language

<br>

- 데이터 제어어
- GRANT, REVOKE, COMMIT, ROLLBACK

<br>

COMMIT 과 ROLLBACK 은 TCL 라고도 불린다.

- TCL : Transaction Control Language
- COMMIT - 트랜잭션 영구 반영
- ROLLBACK - 트랜잭션 영구 미반영

<br>

권한 구문

- GRANT : 권한 부여 SQL
- REVOKE : 권한 회수 SQL

<br>

> 권한, Privilege

<br>

- DBMS 객체에 대한 접근 또는 해당 객체에 사용할 수 있는 SQL 구문을 특정 사용자 계정에게 허가하는 것
- 사용자 계정마다 서로 다른 권한을 부여해 보안성을 확보한다.
- 시스템 권한(DBMS 객체에 대한), 객체 권한(객체에 사용할 수 있는 SQL 구문)이 있다.

<br> 시스템 권한

- DBMS 시스템 작업에 대한 권한
- DBMS 객체들에 대한 접근 권한
- 사용자 계정 생성, 수정, 삭제 / DB 접속 / 객체 생성, 삭제
- 시스템 권한은 주로 관리자 계정에 부여한다. (SYS, SYSTEM 가 아닌 다른 계정을 생성해서 부여한다)

<br>

대표적인 시스템 권한

- CREATE SESSION : DB 접근 권한
- CREATE TABLE : 테이블 생성 권한
- ALTER TABLE : 테이블 수정 권한
- DROP TABLE : 테이블 삭제 권한
- CREATE SEQUENCE : 시퀀스 생성 권한
- CREATE USER : 사용자계정 생성
- CREATE VIEW : 뷰 생성
- CREATE ROLE : 롤 생성

<br>

시스템 권한 자료사전

- DBA_SYS_PRIVS : 관리자 계정으로 부여한 시스템 권한
- USER_SYS_PRIVS : 사용자 계정으로 부여한 시스템 권한

<br>

시스템 권한 부여하는 구문

- GRANT 권한종류 TO 사용자계정;

<br>

시스템 권한 회수하는 구문

- REVOKE 권한종류 FROM 사용자계정;

<br>

객체 권한

- 데이터베이스 객체(테이블, 뷰, 인덱스, 프로시저, 함수 등)에 대한 특정 작업을 수행할 수 있는 권한
- 객체의 소유자(Owner)는 별도의 권한 설정없이 해당 객체에 대한 모든 접근이 허용된다.
- 테이블 객체의 객체 권한들은 DML(SELECT, INSERT, UPDATE, DELETE)이다.

<br>

대표적인 객체 권한

- SELECT : 객체 조회 권한
- INSERT : 삽입
- UPDATE : 변경
- DELETE : 삭제
- GRANT : 권한부여 권한
- INDEX : 인덱싱 권한
- RENAME : 객체 이름 변경 권한

<br>

객체 권한 자료사전

- DBA_TAB_PRIVS : 관리자급 객체 권한
- USER_TAB_PRIVS : 사용자급 객체 권한

<br>

객체 권한 부여 구문

- GRANT 객체권한 ON 객체 TO 사용자계정명;
  - ex ) GRANT SELECT, INSERT ON DEPT TO TEST;

<br>

객체 권한 회수 구문

- REVOKE 객체권한 ON 객체 FROM 사용자계정명;
  - REVOKE SELECT, INSERT ON DEPT FROM TEST;

<br>

롤, ROLE

- 권한들의 집합
- 여러 개의 권한을 한번에 부여하거나 회수할 수 있게 해준다.
- CREATE ROLE 권한을 가지고 있어야 생성할 수 있다.
- 권한을 롤에 부여하고, 롤을 사용자에 부여하는 방식으로 사용한다.
- 롤을 롤에 부여하는 것도 가능하다.

<br>

롤 관련 자료사전

- DBA_ROLE_PRIVS : 관리자 계정으로 생성한 ROLE 자료사전
- USER_ROLE_PRIVS : 사용자 계정으로 생성한 ROLE 자료사전

<br>

테이블 스페이스, tablespace

- 테이블이 저장되는 공간(파일)

<br><br>