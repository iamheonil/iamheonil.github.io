---

layout: post
comments : true
title: 'Database ERD'
subtitle: ''
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 57

---

> UPDATE

<br>

- 테이블의 데이터(행)을 수정하는 구문
- 특정 행의 컬럼 값을 변경할 수 있다.

<br>

``` sql
--- UPDATE 구문 형식

UPDATE TABLENAME
SET COL1 = 값1, COL2 = 값2, COL3 = 값3 ...
WHERE 조건절;

-- WHERE 키워드 없이 사용하면 모든 행이 변경되기 때문에, DELETE 문과 마찬가지로 조건절을 붙여주는것이 좋다.
```



<br><br>