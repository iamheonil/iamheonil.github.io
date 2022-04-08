---

layout: post
comments : true
title: 'Database MERGE'
subtitle: 'DML 문법 중 하나인 오라클의 고유 문법 MERGE'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 57

---

> DML
>
> MERGE

<br>

- 오라클 전용 문법
- SELECT 수행 결과에 따라 UPDATE 또는 DELETE 또는 INSERT 를 수행한다.
- SELECT 조회 결과가 '존재하면' UPDATE 또는 DELETE 수행한다.
- SELECT 조회 결과가 '존재하지' 않으면 INSERT 를 수행한다.

<br>

``` sql
-- MERGE 구문 형식

MERGE INTO TABLENAME
USING (
	SELECT 절 - 인라인 뷰(서브 쿼리)
)
ON (조건절)
WHEN MATCHED THEN 구문
WHEN NOT MATCHED THEN 구문;

-- INTO : 삽입, 갱신, 삭제가 이루어지는 테이블
-- USING : 조건 비교할 소스테이블 또는 인라인 뷰(서브쿼리)
-- ON : WHEN 절에서 반응하는 조건을 부여하는 절
-- WHEN MATCHED : ON절의 조건에 만족하는 USING절 테이블의 데이터가 존재하면 수행,
--				UPDATE, DELETE 를 수행한다.

-- WHEN NOT MATCHED : ON절의 조건에 만족하는 USING절 테이블의 데이터가 없으면 수행,
--				 INSERT 를 수행한다.
```



<br><br>