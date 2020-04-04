---

layout: post
comments : true
title: 'Database 오라클의 3단계 설계'
subtitle: 'DB의 모델링 작업'
date: 2020-04-04
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 71

---

> 오라클의 3단계 설계(모델링 작업)

<br>

- 개념적 설계(모델링)
  - E-R 모델을 작성한다 (ERD)
  - 요구조건을 분석하여 DBMS에 독립적인 E-R 다이어그램을 작성한다.
  - 추상적인 개념을 표현한다.
- 논리적 설계(모델링)
  - 논리적인 자료 구조로 변환하는 과정(DBMS 의존적)
  - 테이블을 구성요소를 설계한다.
  - 실제 물리적인 요소까지 생각하지 않는다(테이블의 자료형, 저장구조 등)
- 물리적 설계(모델링)
  - 논리적 구조로 표현된 설계 결과물을 보며 물리적 구조로 변환하는 과정
  - 실제 DB에 저장될 구조, 경로, 인덱스, 자료형 크기, 순서 등을 결정한다.
  - DBMS가 받게될 영향까지 고려해야한다.

<br>
<br>