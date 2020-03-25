---

layout: post
comments : true
title: 'Oracle to_number'
subtitle: '오라클 형변환 to_number()'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 45

---

 
> to_number

<br>

```sql
SELECT 
'123.67' "THIS IS CHAR",
TO_NUMBER('123.67') "THIS IS CHAR -> NUMBER",
TO_NUMBER('123.67', '99999.99') "형식을 지정", 
--to_number('123.67', '99999.9') "소숫점 지정 오류"
TO_NUMBER('123.67', '99999.99') "소숫점 지정 신중"
FROM DUAL;

SELECT 
67890 "1",
'67890' + 11111 "2",
TO_NUMBER('67890') + 11111 "3",
--'67,890' + 11111 "4" 
TO_NUMBER('67,890', '999,999') + 11111 "5"
FROM DUAL;

SELECT
'$78,789' "1",
to_number('$78,789', '$999,999,999') + 10000 "2"
FROM DUAL;
```

<br>



> to_date

<br>

``` sql
--to_date
SELECT
--'19/10/07' + 5 "1"
to_date('19/10/07') + 30 "2"
FROM DUAL;

SELECT
'12 1 11' "1",
to_date('12 1 11', 'DD/MM/YY') "2",
to_date('12 1 11', 'MM/DD/YY') "규칙에 맞게 작성하기"
FROM DUAL;
```

<br>



> 기타 단일 행 함수

<br>

- NVL

  - 매개변수가 NULL인지 판단하여 NULL이라면 원하는 값으로 변환하는 함수

    - NVL(데이터, 원하는 값)

    - ``` sql
      SELECT EMPNO, ENAME, 
      NVL(COMM, 0) COMM
      FROM EMP
      ORDER BY COMM DESC, ENAME;
      ```

<br>

- NVL2

  - 매개변수가 NULL인지 판단하여 NULL이라면 원하는 값으로 변환하는 함수,

  - NULL 이 아닐 경우도 원하는 값으로 변환할 수 있다.

    - NVL2(데이터, NULL이 아닐 경우 반환 값, NULL일 경우 반환 값)

    - ``` sql
      SELECT 
      EMPNO, ENAME, 
      NVL2(COMM, sal + comm, sal) PAY
      FROM EMP
      ORDER BY PAY DESC, ENAME;
      -- null 데이터는 존재하지 않는 데이터로 생각해서
      -- 연산, 함수의 데이터 등으로 사용하면 아무것도 수행하지 않는다.
      ```

<br>

- NULLIF

  - 두 개의 값이 같은지 비교하여 같으면 NULL 반환, 다르면 첫번째 매개변수를 반환

    - NULLIF(첫번째 값, 두번째 값)

    - ```sql
      SELECT
          NULLIF(10, 20) "1",	-- 10 반환
          NULLIF(20, 10) "2",	-- 20 반환
          NULLIF(10, 10) "3"	-- (null) 반환
      FROM DUAL;
      
      -----------------
      
      
      SELECT EMPNO, ENAME, JOB,
          
          NULLIF(JOB, 'SALESMAN') N_IF,
          NVL(NULLIF(JOB, 'SALESMAN'), '영업') "NEW JOB"
      
      FROM EMP;
      ```

<br>

- DECODE

  - 비교값을 여러개 나열해서 비교결과를 반환하는 함수

    - DECODE(기준 값, 비교 값1, 반환 값1, 비교 값2, 반환 값2, default 값) 

    - DEFAULT 는 생략 가능.

    - 기준 값과 비교 값이 같을 때 비교 값 바로 다음에 오는 반환 값을 반환한다.

    - ``` sql
      SELECT EMPNO, ENAME, DEPTNO,
      DECODE(
      DEPTNO, 
      10, '회계팀', 
      20, '연구팀', 
      30, '영업팀', 
      40, '운영팀',
      '부서없음') DECODE
      FROM emp;
      ```

<br>

- CASE 구문

  - DECODE 함수와 비슷한 동작을 하는 구문

  - CASE ~ WHEN THEN ~ END 로 구성된다.

  - WHEN THEN 절 조건에 따른 반환값을 설정

  - WHEN THEN 절의 마지막에 ELSE 구문을 추가할 수 있다.

  - ```sql
    SELECT EMPNO, ENAME, DEPTNO,
        CASE DEPTNO
            WHEN 10 THEN '회계팀'
            WHEN 20 THEN '연구팀'
            WHEN 30 THEN '영업팀'
            WHEN 40 THEN '운영팀'
        ELSE
            '부서없음'    
        END "CASE문"
    FROM EMP;
    
    SELECT EMPNO, ENAME, DEPTNO,
        CASE
            WHEN JOB=UPPER('president') THEN '사장'
            WHEN DEPTNO = 10 THEN '회계팀'
            WHEN DEPTNO = 20 THEN '연구팀'
            WHEN DEPTNO = 30 THEN '영업팀'
            WHEN DEPTNO = 40 THEN '운영팀'
        ELSE '부서없음'    
        END "CASE문"
    FROM EMP;
    
    -- 자바의 If문과 같이 비교 값의 작성 순서도 매우 중요하니
    -- 유의하여 작성할 것.
    ```

<br><br>