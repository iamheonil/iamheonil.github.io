---

layout: post
comments : true
title: 'Database 주석, Comment'
subtitle: '데이터베이스의 주석'
date: 2020-04-04
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 72

---

> 데이터베이스 주석, Comment

<br>

- 테이블 또는 컬럼에 대한 설명을 작성하는 방법
- 작성된 주석은 자료사전에 들어가게 되므로 확인하기 위해서는 자료사전을 조회해야한다.

<br>

- 주석 생성 구문

  - 테이블 주석

  <br>

  ```sql
  COMMENT ON TABLE 테이블명 IS '테이블설명';
  ```

  <br>

  - 컬럼 주석

  <br>

  ```sql
  COMMENT ON COLUMN 테이블명.컬럼명 IS '컬럼설명';
  ```

  <br>

  - 주석의 자료사전 조회
    - 테이블 주석 : user_tab_comments
    - 컬럼 주석 : user_col_commnets

<br><br>