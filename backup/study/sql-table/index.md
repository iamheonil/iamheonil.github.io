---

layout: post
comments : true
title: 'Database Table'
subtitle: '데이터베이스의 기본, 테이블'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 38

---

 

> 테이블, Table

<br>

- DB 내에서 실제 데이터를 관리, 저장하는 단위(객체)
- 표 형식을 가진다.
- 행(row)과 열(column)로 이루어져있다.
- 데이터는 행(row) 단위로 처리한다.
- 테이블은 소유자(owner)를 가지고 있다.
  - 소유자(Owner) - 데이터를 관리하는 데이터의 주인
  - 즉, 해당 객체를 생성한 사용자 계정
  - ex) scott.dept -> scott 이라는 Owner가 생성한 Dept 테이블
- 소유자는 자신의 테이블에 대한 모든 권한을 가지고 있다.
- 테이블에 대한 관리 권한을 다른 계정에 부여하면 해당 계정도 테이블에 대한 관리가 가능하다
- DBA(Database Administrator, 관리자 계정)는 권한에 상관없이, 소유자에 상관없이 모든 객체(테이블) 을 관리할 수 있다.
  - 오라클의 기본 DBA 계정 : SYS, SYSTEM


<br><br>