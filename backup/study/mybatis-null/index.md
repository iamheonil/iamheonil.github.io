---

layout: post
comments : true
title: 'MyBatis 에서 NULL 값 Insert 하는 방법'
subtitle: ''
date: 2020-07-14
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 156

---
> 마이바티스에서 NULL 값 처리하기

<br>

- INSERT, UPDATE 문을 작성할 때 NULL 값을 입력하거나 수정해야 할 때가 있을 때
- 마이바티스에서는 NULL  값을 입력하려고 할 때 JDBCType 을 명시해줘야한다
  - 타입을 명시하지 않으면 "부적합한 열 유형 : 1111" 같은 에러메시지가 발생한다

<br>

## NULL 값 처리하기

1. Mapper XML 파일에서 SQL 쿼리를 작성할 때 파라미터 값에 각각 데이터 타입을 명시한다

   <br>

``` xml
<insert id="insert2" parameterType="hashmap">
		INSERT INTO Emp(empno, ename, job) VALUES (#{e1}, #{e2}, #{e3, jdbcType = VARCHAR })
</insert>
```

​		<br>

#### jdbcType 로 넣을 수 있는 값

- VARCHAR
- DATE
- TIMESTAMP
- INTEGER
- CHAR
- DOUBLE
- NULL

<br>

2. Configuration XML 파일에서 &lt;settings> 를 이용하여 전역 설정하기

``` xml
<configuration>

	<!-- DB 접속 정보를 Properties 파일에서 추출해오기 -->
	<properties resource="mybatis/db.properties" />
	
	<!-- 마이바티스의 동작을 제어하는 설정 태그 = <Settings> -->
	<!-- properties 밑에, typeAliases 위에 위치해야한다 -->
	<settings>
		<setting name="jdbcTypeForNull" value="NULL"/>
	</settings>
  
  <!-- properties 아래에, typeAlias 위에 위치해야 오류가 발생하지 않는다 -->
 	<!-- TypeAlias -->
	
</configuration>
```

<br>

#### SELECT 태그에서 resultType 으로 설정할 수 있는 값 (키워드)

- DB 조회결과(ResultSet) 를 Java 의 어떤 데이터 타입으로 변환하여 사용할 것인지 설정하는 속성값
- 실제 DTO(객체)는 패키지네임을 포함하는 풀네임으로 적용할 수 있다
  - typeAlias 적용이 가능하다
- 미리 정의되어 있는 키워드를 사용할 수 있다
- org.apache.ibatis.type.TypeAliasRegistry 클래스에 명시되어 있다

<br>

- #### 키워드 - 자바 타입

- string - java.lang.String

- date - java.util.Date

- map - java.util.map

- hashmap - java.util.HashMap

- list - java.util.List

- arraylist - java.util.ArrayList

- ResultSet - java.Sql.ResultSet

------------

- 기본 데이터 타입
- int - java.lang.Integer
- integer - java.lang.Integer
- _int - int
- _integer - int
- int[] - java.lang.Integer[]
- _int[] - int[]
- byte - 자바 기본 타입 이름에 '_(언더바)' 가 안 붙어있으면 Wrapper 클래스 타입
- short
- long
- float
- double
- boolean
- _byte - 자바 기본 타입 이름에 '_(언더바)' 가 붙어있으면 기본 데이터 타입
- _short
- _long
- _float
- _double
- _boolean

<br><br>