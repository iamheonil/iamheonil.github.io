---

layout: post
comments : true
title: 'Database SubQuery'
subtitle: '오라클 SubQuery에 대하여'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 48

---

 
> 서브쿼리, SubQuery

<br>

- SQL 구문 안에 포함된 또 다른 SQL 구문
- 메인쿼리와 서브쿼리(내부쿼리)로 지칭한다.
- 서브쿼리는 ( ) 괄호로 묶어서 표현한다.

<br>

서브쿼리의 종류 - 적용하는 위치에 따른 분류

- 스칼라 서브쿼리
  - SELECT 절에서 컬럼 대신 사용되는 서브쿼리
- 인라인 뷰
  - FROM 절에서 조회 대상으로 사용되는 서브쿼리
- 서브쿼리
  - 주로 WHERE 절에서 사용되는 서브쿼리

<br>

서브쿼리의 종류 - 서브쿼리 수행 결과의 형태에 따른 분류

- 단일 행 서브쿼리
  - 조회 결과가 하나의 행으로 나오는 것
- 다중 행 서브쿼리
  - 조회 결과가 여러개의 행으로 나오는 것
- 다중 열 서브쿼리
  - 조회 결과라 여러 컬럼(행이 아닌 열) 으로 나오는 것


<br><br>