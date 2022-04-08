---

layout: post
comments : true
title: 'JDBC, Execute 메소드의 종류'
subtitle: 'Execute Method'
date: 2020-05-16
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 118

---

> Execute 메소드의 종류

<br>

- 매개변수로 전달받은 SQL 구문을 수행하는 메소드
  - ResultSet executeQuery(String sql);
    - SELECT Query 결과를 ResultSet 으로 반환, ResultSet에는 조회된 모든 행을 담고 있다.
    - ResultSet객체.next() 호출할 때마다 결과집합의 각 행을 나타낸다.
  - int executeUpdate(String sql);
    - 영향받은 행의 수를 int형으로 반환
    - 주로 INSERT, UPDATE, DELETE를 수행할 때 사용한다.
  - boolean execute(String sql);
    - 반환 값 : true, false
      - true - ResultSet 객체를 반환하는 쿼리를 수행했을 때(SELECT)
      - false - ResultSet 객체를 반환하지 않는 쿼리를 수행했을 때
      - 주로 DDL(CREATE, ALTER, DROP)을 수행할 때 사용한다.

<br><br>