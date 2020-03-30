---

layout: post
comments : true
title: 'Database DDL'
subtitle: 'DDL, 데이터 정의어란?'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 59

---

> DDL, Data Definition Language, 데이터 정의어

<br>

- DB 객체
  - 테이블, 사용자 계정, 뷰, 인덱스, 시퀀스 등을 생성, 변경, 삭제하는 SQL
- 구문
  - CREATE, ALTER, DROP
    - 생성, 변경, 삭제

<br>

테이블, Table, TB

- 데이터베이스의 데이터를 저장하는 단위
- 행(row, record), 열(column, col, 컬럼)으로 구성된 객체
- 연관성있는 데이터끼리 독립적인 테이블로 구성한다.
- 테이블들끼리 관계를 맺어 연관성을 확보한다(Primary Key - Foreign Key)
- 관계 : Relation, Relationship
- 개체 : Entity (Table)
- ER, Entity - Relation
  - 개체 - 관계, 테이블들이 관계를 짓고 있는 것
- RDB, Relation Database, 관계형 데이터베이스
  - 테이블들의 관계를 기반으로 이루어진 DB

<br>

CREATE TABLE - 테이블 생성 구문

``` sql
-- CREATE 구문 1
CREATE TABLE TABLENAME(
    컬럼명1 자료형1,
   	컬럼명2 자료형2,
   	컬럼명3 자료형3,
   	컬럼명4 자료형4
    ...
);

-- CREATE 구문 2
CREATE TABLE TABLENAME
AS
SELECT 구문;
```

- 컬럼명은 해당 테이블 내에서 중복불가
- 컬럼은 반드시 자료형이 명시되어야 한다.



<br><br>