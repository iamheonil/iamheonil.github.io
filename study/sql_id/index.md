---

layout: post
comments : true
title: 'Database DBA계정과 설명'
subtitle: 'DBA & 사용자 계정의 종류와 설명'
date: 2020-04-04
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 69

---

> 오라클의 기본계정, 시스템(관리자) 계정

<br>

오라클의 기본 계정

<br>

관리자 계정

- SYS
  - 자료사전들의 Owner이다.
  - DUAL 테이블의 Owner이다.
  - DB를 생성할 수 있다.
- SYSTEM
  - DB 생성 권한이 없다.

DB에 관련된 모든 권한을 가지고 있으며, 둘의 권한은 같다.

<br>

사용자 계정

- SCOTT
  - 테스트용 Dummy데이터를 가지고 있다.
  - 오라클에서 사용하는 SQL문을 연습/학습하는 용도로 사용한다.
- HR
  - SCOTT처럼 테스트 데이터를 가지고 있는 계정
  - 오라클에서 사용하는 SQL문을 연습/학습하는 용도로 사용한다.

<br>
<br>