---

layout: post
comments : true
title: 'Database EquiJoin'
subtitle: '오라클의 조인 중 하나인 EquiJoin(이퀴조인, 등가조인)'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 47

---

 
> 조인의 종류
>
> 순서는 Oracle 문법 - ANSI 문법 - Oracle 문법 - ANSI 문법

<br>

> EQUI JOIN, 등가 조인

<br>

- 오라클 전용 구문
- 조인의 기본이 되며, FROM절에 조인 대상 테이블들을 ','(COMMA)로 나열한다.
- 조인 대상 테이블들의 공통데이터를 가지는 컬럼을 이용해 조인한다(WHERE 조건 = 조건)
- 조인 컬럼이 같은 값을 가질 때 조회될 수 있도록 WHERE 절에서 조인 조건을 적용한다.
- 가장 많이 사용되는 구문 형식이다.

<br>

> ANSI 표준 INNER JOIN, 내부 조인

<br>

- EQUI JOIN과 같은 결과를 얻는다.
- 구문 형식

<br>

``` sql
FROM 기본테이블
INNER JOIN 조인테이블
		ON 조인조건절
```

<br>

- INNER JOIN 키워드에서 INNER를 생략하고 JOIN만 사용해도 된다.

<br>

> NON - EQUI JOIN, 비등가 조인

<br>

``` sql
SELECT ENAME, SAL, GRADE 
FROM EMP E, salgrade S
WHERE SAL BETWEEN losal AND hisal
ORDER BY GRADE, SAL, ENAME;
```

<br>

- EQUI JOIN과 문법은 같으나 조인 조건의 연산자가 '='(Equal)이 아닌 경우
- 연산자 대신 BETWEEN 등이 들어간다.

<br>

> SELF JOIN

<br>

``` sql
SELECT 
    
    E.empno, E.ename, E.mgr,
    M.empno, M.ename
    
FROM EMP E, EMP M
WHERE E.MGR = M.EMPNO;
```

<br>

- 하나의 테이블로 자기 자신 테이블과 조인하는 것

<br>

>ANSI 표준 SELF JOIN

<br>

``` sql
SELECT 
    
    E.empno, E.ename, E.mgr,
    M.empno, M.ename
    
FROM EMP E
INNER JOIN EMP M
ON E.MGR = M.EMPNO;
```

<br>

> CROSS JOIN

<br>

> NATURAL JOIN

<br>

> OUTER JOIN

<br>


<br><br>