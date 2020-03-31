---

layout: post
comments : true
title: 'Database Constraints'
subtitle: 'Database 제약사항, 제약조건'
date: 2020-04-01
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 62

---

> 제약사항, 제약조건, Constraints

<br>

- 테이블에 부적절한 데이터가 입력되는 것을 방지하는 목적으로 테이블 컬럼에 설정하는 필터 조건
- 데이터의 무결성(Integrity)을 유지한다. [데이터 무결성이란?](https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0_%EB%AC%B4%EA%B2%B0%EC%84%B1), 프로그램이 생명주기(Life Cycle)를 거치는 동안 데이터가 정확하고 일관성있는 값을 유지하고 그 값이 보장되는 성격

<br>

제약사항 지정 방식

1. CREATE TABLE 구문에 컬럼과 함께 지정하는 방법(컬럼 레벨에서 지정)
2. 생성된 테이블에 ALTER TABLE 구문을 이용하여 추가적으로 반영하는 방식(테이블 레벨에서 지정)

<br>

제약사항의 종류

- NOT NULL
  - 데이터에 NULL 이 있으면 안된다.
  - 컬럼의 데이터타입과 연계되어 적용되는 제약사항
  - 'ALTER TABLE TABLENAME MODIFY COL 수정할 제약사항' 와 같은 구문을 이용한다
- UNIQUE
  - 데이터의 중복을 허용하지 않는다.
  - 데이터의 유일성을 확보한다.
  - 인덱스를 자동으로 생성한다.
  - UNIQUE가 설정된 컬럼은 테이블의 UNIQUE KEY 라고 부른다.(유일 키, UK)
  - CREATE TABLE CONS_04(DATA VARCHAR2(10) CONSTRAINT CONS_UK UNIQUE); 
  - CREATE TABLE CONS_05(DATA VARCHAR2(10), CONSTRAINT CONS05_UK UNIQUE(DATA)
  - 'ALTER TABLE TABLENAME ADD CONSTRAINT 제약사항이름 UNIQUE(컬럼명)' 과 같은 구문을 사용한다.
- CHECK
  - 컬럼에 들어갈 수 있는 데이터의 범위를 지정하는 제약사항
  - WHERE 절의 조건문과 같은 내용을 제약조건으로 적용시킨다.
  - SEARCH_CONDITION으로 적용된다.
- DEFAULT
  - 데이터를 입력하지 않고 INSERT 할 때 입력될 기본 값을 지정하는 제약사항
  - NOT NULL 처럼 컬럼의 추가 정보로 등록된다
  - 제약사항 항목으로 부여되지 않는다
    - USER_CONSTRAINTS 로 확인 불가능하다. (제약조건 정보)
    - USER_TAB_COLUMNS 로 확인 가능하다. (테이블 컬럼 정보)
  - NULL 을 INSERT 하고 사용하면 동작하지 않는다.
  - 모든 컬럼에 DEFALUT 를 지정해줬다고 값을 안 넣고 실행하는것은 불가능하다. 하나의 컬럼이라도 데이터가 INSERT 되어야 나머지 컬럼의 DEFALUT 값도 INSERT 된다.

<br>

- PRIMARY KEY
  - 기본 키
  - 테이블을 대표하는 컬럼으로 지정하는 키
  - NOT NULL, UNIQUE 제약사항의 특성이 자동으로 부여됨
  - NOT NULL, UNIQUE 가 별도의 항목으로 제약사항이 생성되지는 않는다
  - PRIMARY KEY 자체가 NOT NULL 이며 UNIQUE 이다.
  - UNIQUE 속성때문에 인덱스가 자동으로 생성된다.
  - 외래키(FK)가 참조할 수 있는 자격이 생긴다.
    - 컬럼에 제약조건 이름을 명시하며 지정하기
    - 컬럼에 제약조건 이름없이 지정하기
    - 컬럼 설정 이후에 CONSTRAINT 키워드로 지정하기
    - 테이블 생성 이후 ALTER TABLE 로 지정하기
  - 두 개 이상 PRIMARY KEY 를 지정하는것도 가능하다.
  - ALTER TABLE CONS_13 ADD CONSTRAINT CONS_13_PK PRIMARY KEY(TRADE_DATE, TRADE_NO);

<br>

- FOREIGN KEY
  - 외래 키
  - 기본 키(PK)를 참조하는 컬럼 또는 컬럼'들'
  - 참조하고 있는 PK와 데이터타입이 일치해야한다.
  - 참조무결성 원칙을 지켜야한다.
    - 외래 키는 기본 키로 존재하는 값을 가져야한다.
    - 외래 키가 참조하고 있는 기본 키는 삭제할 수 없다.
    - 외래 키들을 전부 지우고 기본 키를 삭제할 수 있다.
    - 외래 키의 값을 NULL 로 바꿔도 된다.
  - 외래 키 지정 구문 마지막에 넣을 수 있는 옵션
    - ON DELETE SET NULL
      - PK가 삭제되면 NULL 로 변환됨
    - ON DELETE CASCADE
      - PK가 삭제되면 FK도 삭제됨
  - 외래 키 지정 방식
    - 컬럼 설정 이후에 CONSTRAINT 로 지정하기
    - 테이블 생성 후에 ALTER TABLE 로 지정하기


<br><br>