---

layout: post
comments : true
title: 'Database Join'
subtitle: 'Join의 정의와 상식'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 46

---


> 조인, JOIN

<br>

- 2개 이상의 테이블을 한번에 SELECT 하기 위해 사용한다.
- Primary Key 와 Foreign Key를 이용하여 조인 조건을 설정한다.
  - 조인 조건 : 두 개 이상의 테이블을 결합할 때 사용하는 조건
- Primary Key 
  - 기본키(PK)
  - 테이블의 각 행들을 구분하기 위한 식별값으로 쓰이는 컬럼
  - 기본키 무결성 원칙
    - 해당 컬럼은 테이블에서 고유한 값이어야 한다. - UNIQUE
    - 해당 컬럼은 NULL 값을 가질 수 없다. NOT NULL
- Foreign Key
  - 외래키(FK)
  - 다른 테이블의 컬럼을 참조하고 있는 컬럼
  - 다른 테이블의 Primary Key를 참조한다.
  - 외래키 무결성 원칙
    - 참조 테이블에 기본키가 존재하는 값만 가질 수 있다.
- 조인의 문법 종류
  - 오라클 전용 문법
  - ANSI 표준 문법
    - ANSI - American National Standards Institude
      - 문자 인코딩(ASCII) 를 만듬.
    - ISO에 속해있다
      - ISO - Internation Standard Organization
      - 국제 표준화 기구
      - OSI 7계층 모형
    - IEEE(Institute of Electrical and Electronics Engineers)
      - 전기, 전자 기술자 학회
      - IEEE 802.3
      - IEEE 802.11

<br><br>