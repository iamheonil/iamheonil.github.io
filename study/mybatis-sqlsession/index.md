---

layout: post
comments : true
title: '마이바티스 Sqlsession 실행 메소드'
subtitle: 'MyBatis'
date: 2020-07-12
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 153

---

> 마이바티스의 SqlSession 객체의 구문을 실행하는 메소드

<br>

- &lt;T> T selectOne(String statement, Object Parameter)
  - 하나의 객체를 리턴하는 조회 구문 수행 메소드
- &lt;E> List&lt;E> selectList(String statement, Object Parameter)
  - 한 개 이상의 객체를 리턴하는 조회 구문 수행 메소드
- &lt;K, V> Map&lt;K, V> selectMap (String, statement, Object Parameter, String mapKey)
  - 결과 데이터를 Map 으로 변환하기 위해 제공되는 메소드
- &lt;T> Cursor&lt;T> selectCursor(String statement, Object Parameter)
  - 결과 데이터를 Cursor 객체로 반환하는 메소드

- int insert(String statement, Object parameter)
- int update(String statement, Object parameter)
- int delete(String statement, Object parameter)
  - 반환 데이터는 SQL 구문에 의해 영향을 받은 레코드(행) 수를 나타낸다
- 위 모든 메소드들은 Object parameter 없이 호출될 수 있도록 오버로딩 되어있음

<br>

> 마이바티스 매퍼의 쿼리 수행 태그

<br>

- &lt;select>, &lt;insert>, &lt;update>, &lt;delete> 태그
- 수행할 SQL 쿼리에 맞게 태그를 골라 작성하면 된다
- 쿼리와 똑같지 않은 태그를 사용해도 실행은 되지만 되도록 일치시키도록 한다

<br>

- 공통 속성
  - id
    - 해당 매퍼 파일(XML) 에서 유일한 값으로 설정한다
    - 해당 네임스페이스에서 구분자(식별값) 역할을 수행한다
    - DAO 인터페이스의 추상메소드의 이름과 같은 이름으로 작성하도록 한다
  - parameterType
    - 쿼리 수행에 필요한 전달 파라미터의 데이터타입을 명시하는 속성
  - flushCache
    - 구문이 실행될 때마다 캐시를 지울 것인지 설정하는 항목(기본값은 false)
  - timeout
    - 데이터베이스 처리 결과를 기다리는 최대 시간
  - statementType
    - 쿼리 수행방식에 대한 설정
    - Statement, PreparedStatement(기본값), Callable 중 선택

<br>

- &lt;select> 요소 전용 속성
  - resultType
    - SELECT 수행 결과(ResultSet)를 처리할 데이터타입 (실제 데이터 타입) 참조형(DTO) 이라면 패키지까지 포함하여 풀네임으로 작성한다
  - resultMap
    - SELECT 수행 결과(ResultSet)를 처리할 &lt;resultMap> 태그를 이용하여 생성한 id를 이용한다
  - useCache
    - 구문의 결과를 캐시에 저장할 것인지 설정하는 항목 (기본값은 true)
  - fetchSize
    - SELECT 결과를 한번에 가져올 크기(개수)를 설정하는 속성
    - 기본값은 10이다
    - 대용량 데이터 처리가 필요하면 1000개 정도 설정하는 편이다
      - 메모리와 연관되어있기때문에 연구와 고민을 해봐야한다
  - resultSetType
    - 조회 결과값을 읽어오는 동작에 대한 설정
    - DB에 커서객체 동작을 설정한다
      - FORWARD_ONLY
      - SCROLL_SENSITIVE
      - SCROLL_INSENSITIVE
      - 위의 3가지 기능은 사용할 필요가 없다

#### 실제로 사용하는 기능은 id, parameterType, resultType, resultMap 4가지이다

<br>

### 마이바티스의 Cache 에 대하여

- 두가지 내장 캐시가 존재한다
  - Local Session Cache (1nd Level)
  - Second Level Cache (2nd Level)

<br>

- Local Session Cache
  - Session Level Cache 라고도 한다
  - SqlSesison 객체마다 가지고 있는 캐시
  - 개발자가 임의로 기능을 해제할 수 없다
- Second Level Cache
  - Mapper 의 namespace 마다 존재하는 캐시
  
  
<br><br>