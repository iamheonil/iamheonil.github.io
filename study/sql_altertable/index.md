---

layout: post
comments : true
title: 'Database ALTER TABLE'
subtitle: '테이블의 구조, 컬럼을 변경하는 구문'
date: 2020-04-02
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 64

---

> ALTER TABLE

<br>

- 테이블 구조(Schema)를 변경하는 구문
- 테이블을 지정해서 어떤 변경사항을 적용할 것인지에 따라 추가 구문이 달라진다.
- 수행 목적에 따라 구문의 키워드가 달라진다.
  - ADD 		- 테이블의 구조(스키마) 추가
  - MODIFY   - 테이블의 구조(스키마) 변경
  - DROP	   - 테이블의 구조(스키마) 삭제

<br>

- 새로운 컬럼 추가
  - 마지막 컬럼으로 추가된다. (COLUMN_ID도 맨 마지막 숫자를 부여 받는다.)
  - 이미 존재하는 컬럼들 중간에 추가할 수 없다. (Oracle은 불가능 다른 DB는 가능)

``` sql
ALTER TABLE tablename
ADD (컬럼명 데이터타입);
```

<br>

- 컬럼 데이터타입 변경
  - 데이터 타입을 바꾸거나 크기를 변경할 수 있다.
  - 데이터 타입에 종속된 제약조건을 변경할 수 있다.(NOT NULL 등)
  - 해당 컬럼에 데이터가 있을 때 없을 때 동작이 다르다
    - 데이터 있음
      - 타입 : 변경 안됨
      - 크기 : 변경 가능, 단 존재하는 데이터보다 변경 할 크기가 커야한다.
    - 데이터 없음
      - 타입 : 변경 가능
      - 크기 : 변경 가능
    - 예외 - CHAR 와 VARCHAR2 는 이미 데이터가 있어도 서로 변경 가능

``` SQL
ALTER TABLE tablename
MODIFY (컬럼명 데이터타입);
```

<br>

- 컬럼 삭제 
  - 테이블의 컬럼 삭제는 테이블단위로 LOCK이 걸린다(다른 사용자, 다른 조인 되어있던 테이블이 해당 테이블을 이용할 수 없음)
  - 서비스 중에 컬럼을 함부로 DROP 해서는 안된다.
    - ALTER TABLE TABLENAME SET UNUSED(컬럼명);
      - 물리적으로 삭제하지 않고 컬럼을 사용할 수 없게 만든다
      - 컬럼 비 활성화
      - 복구 불가능함
    - ALTER TABLE TABLENAME DROP UNUSED COLUMNS;
      - 위의 Un Used 된 컬럼들을 데이터베이스에서 영구적으로 삭제한다

``` sql
ALTER TABLE tablename
DROP COLUMN 컬럼명;

-- Un Used

ALTER TABLE TABLENAME SET UNUSED(컬럼명);

ALTER TABLE TABLENAME DROP UNUSED COLUMNS;
```

<br>

- 테이블 이름 변경
  - 컬럼명 변경

``` sql
-- 테이블
ALTER TABLE TABLENAME RENAME TO NEW_TABLENAME;



-- 컬럼
ALTER TABLE TABLENAME RENAME COLUMN 기존컬럼명 TO 새컬럼명;
```


<br><br>