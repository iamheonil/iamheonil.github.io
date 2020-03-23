---

layout: post
comments : true
title: 'Database SQL'
subtitle: 'Structured Query Language'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 39

---

 

> SQL, Structured Query Language

<br>

- 구조적 질의 언어
- 데이터베이스의 자료에 대한 검색(조회), 관리, DB생성, DB수정, DBMS객체 관리 등을 수행할 수 있는 언어
- 주로 CRUD 작업을 수행한다.
  - Create, Read, Update, Delete
- 스크립트 언어 : 명령어 문장을 읽으면서 곧바로 동작하는 언어

<br>

> SQL의 용도에 따른 분류

<br>

- DML
  - Data Manipulation Language
    - Manipulation - 조작하다
    - 데이터 조작어
    - 테이블의 데이터를 조작(CRUD, 조회, 삽입, 변경, 삭제) 하는 명령어
    - 데이터를 처리할 때 사용하는 SQL
    - SELECT, INSERT, UPDATE, DELETE
- DDL
  - Data Definition Language
    - 데이터 정의어
    - 데이터베이스의 구조를 정의, 조작하는 SQL
    - CREATE, ALTER, DROP
    - 조회(Read)에 해당하는 구문은 없고 데이터사전을 SELECT하여 만들어진(변경된) 구조를 확인해야 한다.
    - 데이터사전, 자료사전, Data Dictionary
      - 데이터베이스의 정보를 기독해둔 특수한 테이블
    - 데이터베이스의 구조에 대한 정보를 기록한다.
    - DDL이 수행될 때마다 DBMS가 알아서 알맞은 데이터 사전에 반영한다.
    - 스키마, Schema
      - 데이터베이스의 구조
    - 메타 데이터, Metadata
      - 자료에 대한 특성을 설명하는 데이터
      - 데이터에 대한 구조를 설명할 때 주로 사용되는 용어
- DCL
  - Data Control Language
    - 데이터 제어어
    - 보안성, 데이터의 무결성, 병행 작업, 수행 제어 등을 정의하는 SQL
    - DBA가 데이터베이스를 관리하는 목적으로 사용한다.
      - 권한 관련 명령어
        - GRANT, REVOKE
      - 트랜잭션 관련 명령어
        - COMMIT, ROLLBACK(DML과 관련있는 명령어)


<br><br>