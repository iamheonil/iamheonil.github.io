---

layout: post
comments : true
title: 'Database Sequence'
subtitle: '데이터베이스 시퀀스에 대해서'
date: 2020-04-03
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 68

---

> Sequence

<br>

- 연속적인 숫자를 생성하는 객체
- 정수값으로 생성한다
- 생성된 숫자는 테이블의 행을 구분하는 PRIMARY KEY로 사용된다.
- 테이블 내에서 유일한 숫자를 자동으로 생성(Auto INCREMENT)
- 테이블마다 적용할 시퀀스를 각각 따로 생성해서 관리한다 (테이블이 5개면 시퀀스도 5개)

<br>

시퀀스 생성 구문

- CREATE SEQUENCE 시퀀스명;
  - 1부터 시작해서 1++
- 시퀀스 변경 Option
  - START WITH n
    - 시작 값을 설정 할 수 있다.
  - INCREMENT BY n
    - 증가 값을 설정 할 수 있다
  - MAXVALUE n | NOMAXVALUE
    - 최대값을 지정한다
  - MINVALUE n | NOMINVALUE
    - 최소값을 지정한다
  - CYCLE | NOCYCLE
    - 순환구조 여부를 지정한다
  - CACHE n | NOCACHE
    - 미리 생성할 숫자(캐시)의 갯수

<br>

시퀀스 사용 방법

- 시퀀스명.currval
  - 현재 시퀀스 값
- 시퀀스명.nextval
  - 다음 시퀀스 값

<br>

시퀀스 변경 구문

- ALTER SEQUENCE 시퀸스명;
  - INCREMENT BY n
    - 증가 값을 설정 할 수 있다
  - MAXVALUE n | NOMAXVALUE
    - 최대값을 지정한다
  - MINVALUE n | NOMINVALUE
    - 최소값을 지정한다
  - CYCLE | NOCYCLE
    - 순환구조 여부를 지정한다
  - CACHE n | NOCACHE
    - 미리 생성할 숫자(캐시)의 갯수
    - 캐쉬의 크기보다 CYCLE이 작다면 캐쉬 설정이 되지 않는다.
- CREATE SEQUENCE의 START WITH 빼고 전부 변경 가능하다.
- SEQUENCE의 현재 진행하는 값을 임의로 바꿀 수 없다.

<br>

시퀀스 삭제

- DROP SEQUENCE 시퀀스명

<br>

시퀀스 자료사전

- USER_SEQUENCES


<br><br>