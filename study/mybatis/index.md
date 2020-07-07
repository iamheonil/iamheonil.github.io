---

layout: post
comments : true
title: '마이바티스 프레임워크에 대하여'
subtitle: 'MyBatis'
date: 2020-07-08
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 150

---

> MyBatis, Spring 프레임워크

<br>

- 마이바티스 프레임워크
  - 퍼시스턴스 계층 프레임워크(Persistence Layer)
  - DAO - DB 를 연결하는 구조(JDBC)
  - JDBC 관련 개발을 편하게 만들어준다
  - JDBC 프레임워크, 데이터베이스 관리 프레임워크
- 스프링 프레임워크
  - Java 언어를 이용한 프로그램 개발 프레임워크
  - MVC 패턴 기반의 프레임워크

--------------------

> MyBatis

<br>

### [마이바티스 홈페이지 (한국어 번역)](https://mybatis.org/mybatis-3/ko/index.html)

<br>

- 데이터베이스와 자바객체(DAO)를 연결(매핑)해주는 JDBC 자동화 프레임워크
- JDBC 를 편하게 사용할 수 있게 해준다
- JDBC 동작 코드들을 캡슐화하여 제공한다
  - Connection, PrepareStatement -> SQL 쿼리들을 DB에 전송 -> 결과 -> close

<br>

- 마이바티스의 장점
  - SQL 코드와 프로그램 코드를 분리하여 관리할 수 있다
- 마이바티스의 단점
  - 코드가 캡슐화 되어 있어 개발자가 내부동작을 확인하기 어렵다
- iBatis 는 MyBatis 의 예전 이름이다
  - iBatis 는 Apache Foundation 에서 프로젝트로 존재하던 것
  - MyBatis 는 전체 프로젝트가 Google 에 넘어가면서 이름을 바꾼 것
  - iBatis : JDK 1.4 이전 버전
  - MyBatis : JDK 1.5 이후 버전

<br>

- 마이바티스 기본 세팅
  - 라이브 러리 설치
    - mybatis-x.x.x.jar
    - ojdbcX.jar
- 마이바티스 설정파일 작성(XML 파일)
  - configuration XML 파일 (마이바티스의 DB 접속 설정 파일)
    - mybatis/mybatis-config.xml
  - 마이바티스 Connection Factory 클래스 작성
    - 마이바티스를 이용한 DB 연결 객체를 생성하는 클래스 (싱글톤 적용)
    - SqlSessionFactory 클래스의 인스턴스를 싱글톤으로 생성하고 관리한다
      - SqlSession 클래스
        - DB쿼리(SQL) 작업 수행 객체
      - SqlSessionFactory 클래스
        - 설정 항목을 불러와 SQL 세션 객체를 생성하는 객체
      - SqlSessionFactoryBuilder 클래스
        - 설정 파일(XML)을 불러와 SqlSessionFactory 객체를 생성하는 객체
- DAO 파일 (interface 만) 작성하기
  - 마이바티스와 연결되는 자바 객체
- Mapper 파일 작성하기 (XML)
  - 마이바티스에 적용할 쿼리 매퍼 파일
- DTO 파일 작성 (class)
  - 테이블 정보를 전달하거나 전달받는 객체 (도메인 객체 혹은 모델 객체)
- Controller 파일 작성 (실행 클래스, main())
  - SqlSessionFactory 클래스를 이용하여 SqlSession 객체를 생성한다
  - SqlSession 객체를 이용하여 DB 쿼리를 수행한다 (마이바티스 동작을 수행시킨다)



<br><br>