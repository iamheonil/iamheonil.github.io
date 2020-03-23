---

layout: post
comments : true
title: 'Database DML'
subtitle: 'Data Manipulation Language'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 40

---

 

> DML 
>
> SELECT 구문

<br>

- 테이블에 저장된 데이터를 조회할 때 사용하는 명령어
- 반드시 FROM 절이 뒤에 따라와야 한다.
- 테이블의 모든 컬럼을 이용해 전체 데이터(행)를 조회한다.
- EX) SELECT * FROM tablename;
  - EX) SELECT * FROM dept;
- 지정된 컬럼만 조회한다
  - EX) SELECT col1, col2 FROM tablename;
- 지정된 컬럼을 조회하고 정해진 별칭에 맞춰 출력한다.
  - EX) SELECT col1 AS "별칭", col2 AS "별칭" FROM tablename;
- AS 키워드를 생략하고 띄어쓰기만 구분하면 별칭이 된다.
  - EX) SELECT col1 "별칭", col2 "별칭" FROM tablename;

<br>

> FROM 절

<br>

- 조회 대상을 지정하는 절
- 테이블 TABLE
- 뷰 VIEW
- 인라인 뷰 Inline View, 서브쿼리

<br>

> WHERE 절

<br>

- 조건절이다.
- 조건에 만족하는 데이터(행)만 처리하도록 설정한다.
- SELECT, UPDATE, DELETE 구문에서 많이 사용된다.
- WHERE [조건절]
  - [조건절] : 컬럼명 연산자 조건값 의 형태로 작성한다.
    - ex) WHERE job = 'SALESMAN';
    - ex) WHERE name = 'SMITH'
    - ex) WHERE empno = '7782'
      - ' ' < 문자
      - = 는 자바의 == 와 동일한 연산자
      - SQL과 같은 스크립트 언어에는 대입과 연산 아무것도 존재하지 않는다.

<br>

연산자

- 비교(관계) 연산자
  - = 같다
  - != 같지 않다 // <> 같지 않다 // ^= 같지 않다
  - < 작다
  - '>' 크다
  - <= 작거나 같다
  - '>=' 크거나 같다
- 논리 연산자
  - && == AND 두 조건이 모두 만족할 때 TRUE
  - || == OR 두 조건 중 하나라도 만족할 때 TRUE
  - NOT 논리 부정
  - 자바처럼 &&, || 과 같이 쓰지 않고 AND, OR와 같이 영문으로 작성한다
- 기타 연산자
  - BETWEEN a AND b
    - a와 b 사이의 조건을 만족하면 출력한다.
    - a와 b 포함
      - ex) deptno BETWEEN 10 AND 20
      - ex ) sal BETWEEN 1000 AND 3000
        - (sal >= 1000 AND sal <= 3000) 과 같은 결과가 나오지만 가독성 향상을 위해.
    - NOT BETWEEN 
      - BETWEEN 의 부정문이다
        - FROM emp WHERE NOT (ename BETWEEN 'ALLEN' AND 'KING');
        - FROM emp WHERE ename NOT BETWEEN 'ALLEN' AND 'KING';
        - 두 구문 다 결과는 똑같다.
  - IN (list)
    - list 에 해당하는 값 중 하나라도 일치한다면 TRUE
      - ex) DEPTNO IN (10, 20) == (DEPTNO = 10 OR DEPTNO = 20)
      - OR 을 여러 번 사용하면 가독성이 떨어지니 IN (List) 를 사용하자는 것
      - NOT IN (list)
      - SELECT empno, ename FROM EMP WHERE NOT (empno IN(7369, 7521, 7654));
      - SELECT empno, ename FROM EMP WHERE empno NOT IN(7369, 7521, 7654);
      - 두 구문 다 결과는 똑같다
  - LIKE
    - 지정된 형식의 문자열 포맷(서식)으로 일치하는 조건
      - % : 여러 개의 문자, 또는 문자가 없는 경우
      - _ : 단일 문자, 반드시 한 글자가 존재해야 함
        - %, _ 는 LIKE 에서만 사용된다.
      - ex) ename LIKE 'B%';
        - B로 시작하는 모든 문자열
      - ex) ename LIKE '%B%';
        - % 와 % 사이에 B가 포함하는 문자열
      - ex) ename LIKE '%_B%';
        - B의 바로 전에 어떠한 글자가 존재하는 경우
    - NOT LIKE
      - 포함하지 않는 것 출력
        - SELECT empno, ename FROM EMP WHERE ENAME NOT LIKE '%_RD%';
          - %_RD% 로 끝나지 않는 사원들 모두 출력
  - IS NULL
    - 컬럼의 값이 NULL인지 검사하는 연산자
      - ex) SELECT * FROM emp WHERE mgr IS NULL;
    - 테이블의 데이터 중(null) 값은 데이터가 없음을 나타낸다.
    - WHERE mgr = null 형식으로 조건식을 사용하면 데이터가 존재하지 않는 공간과 null 데이터를 비교하는 구문이 된다. -> 데이터가 없는 공간은 아예 검색 대상에서 제외된다.
    - 부정문 IS NOT NULL

<br>

> DB 탐색(조회) 방법, SCAN

<br>

- 풀 스캔, Full SCAN
  - 테이블의 처음부터 끝까지 전부 탐색하는 방법
  - SELECT empno, ename FROM emp WHERE empno LIKE '7654';
- 인덱스 스캔, Index SCAN
  - 인덱스를 우선 조회하고 인덱스에 연결된 행을 찾아가는 탐색 방법
  - SELECT empno, ename FROM emp WHERE empno = '7654';
- 인덱스 스캔으로 탐색되지 않으면 풀 스캔한다.
- 서식없이 동등비교(equal)할 때는 Like 연산자를 사용하면 안된다.
- Like 는 풀 스캔을 무조건 발생 시키기 때문에 성능에 악영향을 미친다.



> SQL문 Quiz

<br>

``` sql
-- SELECT empno, ename, deptno FROM emp
-- WHERE	 구조를 이용하여 해결할 것

 -- 부서번호가 30이고 직무가 영업인 사원 조회
	ALLEN, WARD, MARTIN, TURNER
SELECT empno, ename, deptno FROM emp 
WHERE deptno = '30' AND JOB LIKE 'SALESMAN';


 -- 부서번호가 30이고 직무가 영업이 아닌 사원 조회
	BLAKE, JAMES
SELECT empno, ename, deptno FROM emp 
WHERE deptno = '30' AND JOB NOT LIKE 'SALESMAN';


 -- 부서번호가 30이 아니고 직무가 영업이 아닌 사원 조회
	SMITH, JONES, CLARK, KING, FORD, MILLER
SELECT empno, ename, deptno FROM emp 
WHERE deptno <> '30' AND JOB <> 'SALESMAN';

지양 - WHERE deptno NOT LIKE '30' AND JOB NOT LIKE 'SALESMAN';
LIKE 는 인덱스 스캔이 아닌 풀 스캔을 하기 때문


 -- 사원번호가 7782에서 7900 사이인 사원 조회
	CLARK, KING, TURNER, JAMES
SELECT empno, ename, deptno FROM emp 
WHERE empno BETWEEN 7782 AND 7900;


 -- 사원명이 'A'부터 'C'로 시작하는 사원 조회
	ALLEN, BLAKE, CLARK
SELECT empno, ename, deptno FROM emp 
WHERE ename >= 'A' AND ENAME < 'D';

지양 - SELECT empno, ename, deptno FROM emp WHERE ename BETWEEN 'A%' AND 'C%';
지양 - WHERE ename LIKE 'A%' OR ename LIKE 'B%' OR ename LIKE 'C%'
BETWEEN 의 %는 LIKE 의 % 처럼 인식하지 못하고 그냥 문자열 % 로 인식한다.


 -- 부서번호가 10 또는 30인 사원 조회 (IN 사용)
	ALLEN, WARD, MARTIN, BLAKE, CLARK, KING, TURNER, JAMES, MILLER
SELECT empno, ename, deptno FROM emp 
WHERE deptno IN ('10', '30');
```



<br><br>