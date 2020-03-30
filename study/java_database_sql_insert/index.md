---

layout: post
comments : true
title: 'Database Insert'
subtitle: 'DML 문법 중 하나인 INSERT'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 55

---

> DML 문법
>
> INSERT

- 테이블에 새로운 데이터(행)를 추가할 때 사용하는 SQL

<br>

``` sql
-- 문법 형식
INSERT INTO TABLENAME(COL1, COL2, COL3, COL4 ...)
VALUES(DATA1, DATA2, DATA3, DATA4, ...);
-- 컬럼수와 VALUES 순서가 맞아야하고, 지정된 데이터타입(유형)도 맞춰서 넣어야 한다. 

-- 문법 형식 2
INSERT INTO TABLENAME
VALUES(DATA1, DATA2, DATA3, DATA4, ...);
-- 컬럼을 입력하지 않아도 된다, 모든 컬럼의 값을 순서대로 입력해야한다.

-- 문법 형식 3
INSERT INTO TABLENAME
SELECT DATA1, DATA2, DATA3, DATA4, ...
FROM DUAL;
-- 2번 형식과 흡사한데 SELECT 구문을 사용한다.

-- 문법 형식 3_1
INSERT INTO TABLENAME (COL1, COL2 ...)
SELECT COL1, COL2 FROM TABLENAME
WHERE 조건;
```

<br>

unique constraint (SCOTT.PK_EMP) violated 오류

- PK 에는 NOT NULL 과 Unique 제약사항이 설정되어 있다. 따라서 중복 된 값을 또 삽입하게 되면 오류가 발생한다.

<br>

> INSERT ALL

<br>

- 한번에 여러 행을 삽입할 수 있게 해주는 DML 쿼리
- SELECT 구문의 결과를 조건에 따라 INSERT 되도록 하는 구문
- 여러 개의 INSERT 구문으로 작성해야할 쿼리를 하나로 합칠 수 있다.

<br>

```sql
-- 문법 형식
INSERT ALL
WHEN 조건
	THEN INTO TABLENAME(COL)
	VALUES (datalist)
SELECT ;

INSERT ALL
2. WHEN 조건
	3.	THEN INTO TABLENAME(COL)
		VALUES (datalist)
	[WHEN절 여러 번 사용 가능]
1. SELECT 절;
```

- THEN INTO 절의 컬럼명, VALUES절 생략 가능함.
- 컬럼명, VALUES절 생략 시 SELECT절에서 조회한 모든 데이터(모든 컬럼)의 값을 삽입한다.
- 

<br><br>