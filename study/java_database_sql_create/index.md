---

layout: post
comments : true
title: 'Database Create'
subtitle: 'DDL의 구문들중 CREATE & DROP'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 54

---

> DDL
>
> CREATE & DROP

<br>

``` sql
-- 테이블의 결과를 복사하여 테이블을 생성하는 구문

CREATE TABLE 생성할 TABLENAME
AS
SELECT * FROM 복사할 TABLENAME;
```

<br>

CREATE & DROP

- CREATE, DROP 은 COMMIT, ROLLBACK 이 불가능하다.

<br><br>