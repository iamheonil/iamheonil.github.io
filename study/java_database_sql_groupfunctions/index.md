---

layout: post
comments : true
title: 'Database Group Function'
subtitle: '오라클의 그룹함수'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 46

---

 
> 그룹 함수, Group Function

<br>

- 복수 행 함수
- 테이블의 여러 행들의 데이터를 그룹화하여 하나의 결과로 도출하는 함수
- 주로 테이블 데이터의 통계처리를 수행한다.
- COUNT
  - 데이터를 가지고 있는 행 수를 반환
  - NULL 값은 무시한다.
  - NULL 값을 가지는 컬럼은 전체 행 수에 포함되지 않는다.
- SUM
  - 합계
- AVG
  - 평균
- MAX
  - 최대, 최고 값
- MIN
  - 최소, 최저 값

<br>

GROUP BY 절

- 데이터(행) 들을 원하는 기준으로 그룹화할 때 사용하는 절
- 그룹함수를 사용할 때 적용한다
- 컬럼을 기준으로 같은 값을 가지고 있는 행끼리 그룹화 한다.
- 구문 형식
  - GROUP BY 컬럼명1, 컬럼명2..
  - SELECT 절에서 그룹 함수 외의 다른 컬럼을 같이 조회하려면 GROUP BY 절에 그룹 함수를 제외한 모든 컬럼을 넣어줘야 한다.

<br>

HAVING 절

- GROUP BY 절 다음에 올 수 있는 조건절
- WHERE 절과 기능이 같다.
- WHERE 절은 그룹함수를 사용할 수 없고 그룹함수의 결과를 조건식으로 사용하고 싶다면 HAVING절을 사용해야 한다.

<br>

SELECT 구문 작성 순서

1. SELECT
2. FROM
3. WHERE
4. GROUP BY
5. HAVING
6. ORDER BY

<br>

SELECT 구문 수행 순서

1. FROM - 조회 될 대상 테이블을 확인한다.
2. WHERE - 검색 조건에 맞게 조회대상(행)을 지정한다.
3. GROUP BY - 컬럼의 값을 이용, 같은 값을 가지는 경우에만 그루핑
4. HAVING - 그룹함수를 이용한 조건절 수행
5. SELECT - 보여질 컬럼(열)을 지정한다.
6. ORDER BY - 보여지는 조건들을 오름차순, 내림차순에 맞게 정렬한다.
   - 수행 순서에 따라 Alias(별칭)도 반영된다.
   - SELECT에서 지정한 Alias 는 ORDER BY 에서 사용 가능하지만, WHERE 에서는 사용 불가능
   - WHERE 절에서 그룹함수는 사용할 수 없다.(WHERE가 GROUP BY 전에 수행된다.)

<br><br>