---

layout: post
comments : true
title: '마이바티스 selectKey 태그'
subtitle: 'MyBatis'
date: 2020-07-12
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 152

---

> MyBatis 의 selectKey 태그

<br>

- 자동 생성 키(auto increment)를 지원하지 않는 데이터베이스(ex. 오라클 DB)에서 사용하는 키 생성 태그
- &lt;insert> 태그 안에서 사용한다
- 주로 PK 값을 생성하는 데 사용되는 태그

<br>

- &lt;selectKey> 태그의 속성
  - order
    - BEFORE : insert 쿼리 수행 전에 selectKey 가 동작하도록 설정
    - AFTER : insert 쿼리 수행 후에 selectKey 가 동작하도록 설정
  - resultType
    - 조회결과 값의 데이터 타입 (자바 타입)
  - keyProperty
    - 결과값이 매핑될 프로퍼티이름 지정(parameterType 의 멤버 필드명)
  - statementType
    - Statement, PreparedStatement, Callable 중 선택할 수 있다
    - 기본값은 PreparedStatement 이다
    - Callable 은 PL/SQL 사용할 때 사용한다
    
<br><br>