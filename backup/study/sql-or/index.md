---

layout: post
comments : true
title: 'Database OR'
subtitle: 'OR 연산자(||)'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 43

---


> 데이터 연결 연산자, || (OR)

<br>

- 두 개의 데이터를 하나의 문자열로 연결하여 표현하는 연산자
- 자바에서는 '+' 가 이 역할을 수행했었다.
- 문자 || 문자
- 문자 || 숫자
- 문자 || 날짜
- 오라클 SQL에서 문자열은 ' '으로 감싸서 표현한다.

<br>

``` sql
SELECT ename job AS EMPLOYEE FROM emp;
-- 위의 코드로 실행하면 ename과 job이 공백 없이 출력되기 때문에 가독성에 좋지 않다.

SELECT ename || ' is ' || job AS EMPLOYEE FROM emp;
-- 그래서 || || 의 사이에 문자열을 추가해준다.
```

<br>

``` sql
-- SMITH's job is CLERK 라는 형식으로 출력해주려면
SELECT ename || '''s job is ' || job AS EMPLOYEE FROM emp;
-- '' 를 일반 문자열로 인식하기 때문에 '을 하나 더 넣어서 "'" 도 문자열로 인식하게 해준다.
```

<br><br>