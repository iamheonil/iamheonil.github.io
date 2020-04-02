---

layout: post
comments : true
title: 'Database View'
subtitle: '데이터베이스 View 구문에 관하여'
date: 2020-04-03
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 67

---

> VIEW

<br>

- 복잡한 쿼리를 간단하게 표현하려는 목적을 가지고 있다.
- 접근 할 수 있는 데이터의 범위(컬럼)를 축소시키는 용도로 사용할 때도 있다.
- 테이블에서 조회되는 컬럼을 제한할 수 있다.
- 조회결과를 저장하지 않는다, VIEW 는 SELECT 쿼리 (Sub Query)를 텍스트로 저장하고 있다.
- VIEW 는 이름만 봐서는 TABLE 인지 VIEW 인지 구분할 수 없다.
- 자료사전들은 대부분 VIEW 이다.
- VIEW 를 통해서 원본 테이블에 조회, 삽입, 수정, 삭제가 가능하다.

<br>

뷰 생성 구문

## CREATE [OR REPLACE] [FORCE | NOFORCE] VIEW VIEWNAME AS ()

## [WITH CHECK OPTION] ;

- CREATE VIEW viewname AS ( 서브 쿼리 작성 )
  - 뷰만 생성한다.
- CREATE OR REPLACE VIEW viewname AS ( 서브 쿼리 작성 )
  - 이름과 일치하는 뷰가 존재한다면 수정하고 없다면 생성한다.
  - 대부분 OR REPLACE 를 사용한다.
- (Option)
  - FORCE
    - 서브쿼리의 조회대상(테이블)이 존재하지 않아도 뷰를 생성한다.
  - NOFORCE
    - 서브쿼리의 조회대상이 존재하지 않으면 뷰를 생성하지 않는다
    - FORCE 와 NOFORCE 둘 다 적지 않으면 NOFORCE로 동작한다.
  - WITH CHECK OPTION [CONSTRAINT 제약조건]
    - 제약조건에 맞는 데이터만 삽입, 수정 가능하게 설정
    - CONSTRAINT 키워드로 제약조건을 넣지 않으면 서브쿼리로 조회할 수 있는 데이터만 삽입, 수정 가능
  - WITH READ ONLY
    - 조회 전용 뷰로 설정

<br>

뷰 삭제 구문

- DROP VIEW viewname;

<br>

뷰 관련 자료사전

- USER_VIEWS
  - 만들어진 뷰에 대한 정보가 담겨있는 자료사전
  - SELECT * FROM USER_VIEWS;


<br><br>