---

layout: post
comments : true
title: 'Database ROWNUMBER'
subtitle: '조회되는 결과에 행 번호를 붙이는 키워드인 ROWNUM'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 49

---


> rownum

<br>

- 조회되는 결과에 행 번호를 붙이는 키워드

<br>

``` sql
SELECT ROWNUM, EMPNO, ENAME FROM EMP;

-- 전체 보기
SELECT ROWNUM, EMP.* FROM EMP;
```

<br>

ROWNUM 을 이용한 Top-N 분석

``` sql
SELECT * FROM (
	SELECT ROWNUM rnum, TMP.* FROM (
   		SELECT * FROM 테이블명 -- 조회하려는 대상지정
         ORDER BY 컬럼명 -- 정렬기준 설정
    ) TMP 
) R

WHERE RNUM BETWEEN 1 AND 4;
```

<br>

``` sql
-- 바쁘다 바빠 현대 사회~!

SELECT * FROM (
SELECT ROWNUM rnum, E.* FROM (
SELECT * FROM emp 
ORDER BY hiredate ASC) E
)
WHERE rnum BETWEEN 1 AND 3;

```


<br><br>