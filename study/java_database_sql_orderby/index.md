---

layout: post
comments : true
title: 'Database ORDER BY'
subtitle: '데이터의 정렬'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 41

---

 

> ORDER BY

<br>

- SELECT 쿼리 결과를 정렬하기 위한 구문
- 정렬을 하기 위한 구문
- WHERE 절 다음에 위치한다.
- SELECT * FROM emp ORDER BY EMPNO;
- ORDER BY ename ASC;   -- 오름차순 정렬
  - ASC, ASCENDING
- ORDER BY ename DESC;  -- 내림차순 정렬
  - DESC, DESCENDING

<br>

ORDER BY 구문 형식

- ORDER BY 컬럼명1, 컬럼명2, ...;
- 컬럼명 뒤에 ASC 또는 DESC 를 추가한다
- SELECT * FROM emp ORDER BY deptno ASC, ename ASC, empno DESC; 와 같이 컬럼당 정해주는 것도 가능하다.
- SELECT empno, ename, comm FROM EMP ORDER BY COMM DESC NULLS LAST;
  - NULLS - NULL 들을 처리하는 구문, NULL 데이터가 정렬되는 순서를 바꾸려면 NULLS 키워드를 사용한다.
    - NULLS FIRST; NULL 데이터를 처음으로 보이게 한다 
      - ORDER BY comm ASC NULLS FIRST;
    - NULSS LAST; NULL 데이터를 마지막으로 보이게 한다
      - ORDER BY comm DESC NULLS LAST;
        - DESC NULLS LAST 를 많이 사용하는 편
- 조회되지 않는 컬럼을 이용해서도 정렬기준으로 삼을 수 있다.
  - SELECT empno, ename, comm FROM EMP ORDER BY sal DESC;


<br><br>