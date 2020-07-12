---

layout: post
comments : true
title: '마이바티스 resultMap 태그'
subtitle: 'MyBatis'
date: 2020-07-12
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 151

---

> MyBatis 의 resultMap 태그

<br>

- 마이바티스 Mapper 에서 사용할 수 있는 태그 중 하나

- 테이블의 컬럼명과 DTO 의 멤버필드명이 다를 때 조회결과(ResultSet)를 매핑하는 태그

- 조회된 컬럼명과 멤버필드명이 같으면 자동으로 매핑되지만 다르다면 resultMap 을 활용해야한다

- &lt;resultMap>을 사용하지 않는다면 SQL 의 Alias(별칭 붙이기) 를 이용할 수도 있다

  <br>

  ``` sql
  SELECT board_no AS boardno FROM TABLENAME
  ```

  <br>

- &lt;resultMap> 태그의 속성

  - id : 생성하는 resultMap 의 이름을 지정하는 속성
    - DTO 클래스의 이름으로 명명하는 경우가 많다
  - type : resultMap 으로 매핑될 실제로 존재하는 DTO 클래스를 설정하는 속성
    - 패키지까지 포함한 풀네임으로 명명하는 경우가 많다

- &lt;resutMap> 태그의 하위 태그

  - &lt;id> : 키값에 해당하는 컬럼을 지정할 때 사용
  - &lt;result> : 키값이 아닌 컬럼을 지정할 때 사용
    - 둘 다 column 속성으로 컬럼명, property 속성으로 필드명을 명시한다
  - &lt;constructor> : 생성자 지정 태그
    - &lt;resultMap> 으로 매핑된 결과에 초기값을 넣을 때 사용한다
  - &lt;association> : &lt;resultMap> 의 1:1 관계의 객체를 설정할 때 사용한다
  - &lt;collection> : &lt;resultMap> 의 일대다 관계의 객체를 설정할 때 사용한다 

<br>

``` java
// 1:1 관계
class Board {
  int boardno;
  BoardFile file;
}

// 일대다 관계
class Board {
  int boardno;
  BoardFile[] file;
}
```



<br><br>