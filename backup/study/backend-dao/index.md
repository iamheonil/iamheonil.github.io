---

layout: post
comments : true
title: 'BackEnd DAO 란?'
subtitle: 'DAO, Data Access Object'
date: 2020-05-16
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 120

---

> DAO, Data Access Object

<br>

- 데이터베이스의 데이터에 접근하기 위해 작성되는 객체
- 데이터베이스에 수행할 SQL 구문 하나를 하나의 메소드로 구현한다.

<br>

- Interface 와 Class 로 나눠 작성하는것이 좋다.
  - interface에서 구현된 메소드들의 목록을 간편히 확인할 수 있다.
  - interface에 메소드마다 주석을 작성해놓는 것이 좋다
    - 전체적인 개요를 한눈에 볼 수 있다.
  - class에는 실제 구현 코드를 작성한다.
  - interface는 개발하는 시점에 메소드 형식에 대한 가이드가 된다.
  
<br><br>
