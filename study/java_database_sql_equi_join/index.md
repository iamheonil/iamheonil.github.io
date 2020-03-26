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

- 카테시안 곱(Cartesian Product)을 얻을 때 사용한다.
  - 테이블들의 조인 결과로 조회 가능한 모든 경우의 수를 출력한 것
  - ex) 4개의 컬럼, 3개의 행을 가지는 Table1
  - ex) 7개의 컬럼, 5개의 행을 가지는 Table2
  - T1과 T2의 카테시안 곱을 생성하면 11개의 컬럼과 15개의 행을 결과로 가진다.
- 개념만 알아둬도 상관 없을 정도.

<br>

> NATURAL JOIN

<br>

- 조인 조건 없이 EQUI JOIN(등가조인)을 수행한다.
- 조인 조건이 되는 컬럼을 자동으로 설정한다.
- 단, 조인 조건을 개발자가 마음대로 제어하는 데 어려움이 있다.
- 자등으로 지정하기에 NATURAL JOIN 도 안 쓰는걸 추천한다.



<br>

> OUTER JOIN

<br>

- 조인 컬럼 중에서 한 쪽이 값을 가지고 있지 않을 때 사용하는 조인이다.
- NULL 값이 포함된 컬럼을 조인 결과에 추가해 준다.

``` sql
-- ORACLE 전용 OUTER JOIN 구문

SELECT EMPNO, ENAME, D.deptno, D.dname
FROM EMP E, DEPT D
WHERE E.DEPTNO(+) = D.DEPTNO
ORDER BY DEPTNO, EMPNO;
```



<br>



``` sql
-- ANSI 전용 OUTER JOIN 구문

SELECT EMPNO, ENAME, D.deptno, D.dname
FROM EMP E
RIGHT OUTER JOIN DEPT D
ON E.DEPTNO = D.DEPTNO
ORDER BY DEPTNO, EMPNO;
```



<br>



Oracle 전용과 ANSI OUTER JOIN의 차이

- 오라클 전용 문법에서는 조인 조건에서 (+) 연산자를 사용한다.
- ANSI 표준 문법에서는 OUTER JOIN 구문을 사용한다.
- FROM 절의 테이블 나열 순서와 조인조건의 컬럼의 순서를 똑같이 배치한다.
- 조인조건에서 왼쪽의 컬럼에 (+) 연산자가 있으면 RIGHT OUTER JOIN으로 변환
- 조인조건에서 오른쪽 컬럼에 (+) 연산자가 있으면 LEFT OUTER JOIN 으로 변환한다.

<br>

FULL OUTER JOIN

- ANSI 표준 구문에만 존재한다.
- 조인되는 테이블 양측 모두 NULL을 가지는 컬럼이 있을 때 사용한다.

<br><br>