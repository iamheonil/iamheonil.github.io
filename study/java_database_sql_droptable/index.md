---

layout: post
comments : true
title: 'Database Drop Table'
subtitle: '데이터의 삭제'
date: 2020-04-02
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 65

---

> DROP TABLE

<br>

- DROP TABLE TABLENAME
  - DDL
  - ROLLBACK 이 불가능하다
  - '테이블 자체'를 삭제한다
- TRUNCATE TABLE TABLENAME
  - DDL
  - ROLLBACK 이 불가능하다
  - '테이블의 데이터'를 삭제한다
  - 테이블의 스키마를 유지한다
- DELETE TABLE TABLENAME
  - DML
  - ROLLBACK 이 가능하다
  - 테이블의 데이터를 삭제한다

<br>

TRUNCATE 와 DELETE의 차이점
<br>

``` sql

--	TRUNCATE							DELETE
--	DDL									DML
--	데이터가 차지하던 물리적 공간 삭제		   데이터가 차지하던 공간을 빈 공간으로 만듬.
--	(용량이 줄어든다)					    (용량이 유지된다)



-- 일반적인 데이터 삭제에는 DELETE를 사용하고 
-- 테이블 전체 데이터를 초기화(삭제)할 때에는 TRUNCATE를 사용한다.

```


<br><br>