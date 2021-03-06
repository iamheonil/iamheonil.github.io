---

layout: post
comments : true
title: '유스케이스'
subtitle: 'UseCase'
date: 2020-06-21
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 148

---

> 유스케이스

<br>

- 액터(행위자)
  - 사용자 액터
  - 시스템 액터
- 유스케이스
  - 액터 입장에서 바라보는 시스템의 기능
- 커뮤니케이션(관계)
  - 연관 관계
    - 액터 - 유스케이스의 상호작용
    - --------------- 와 같은 실선으로 표시
  - 포함 관계
    - . - - - - - <&lt;include>>- - - - - -> 
  - 확장 관계
    - . - - - - - <&lt;extends>>- - - - - ->
  - 일반화 관계
    - .----------------------------------|>
    - 유사한 유스케이스들을 추상화하여 하나의 유스케이스로 그룹지은 관계
    - 공통 기능을 수행하는 액터를 추상화하여 하나의 액터로 그룹지운 관계

<br>

### &lt;&lt;include>> : 필수 사항

- 수행기능 - - -<&lt;include>>- - -> 필수기능

<br>

### &lt;&lt;extends>> : 선택 사항

- 수행기능 <- - -<&lt;include>>- - - 선택기능

#### 화살표 그리는 기준을 잘 잡아서 그려야한다.

<br>

#### 요구사항의 기능적 요소, 비기능적 요소

- 프로그램 개발에 모두 필수적으로 필요하다
- 둘 다 중요하다!
- 기능적 요소는 액터가 수행하는 기능들을 말한다
  - 글쓰기, 첨부파일 추가하기 등
- 비기능적 요소는 프로그램의 품질이나, 속성들을 뜻한다
  - 사진첨부 제한용량
  - 다국어 지원(UTF-8 인코딩 설정 등)
  - 음성 지원

<br>

### UML, Unified Modeling Language

- 소프트웨어 공학에서 사용되는 표준화된 범용 모델링 언어
- 소프트웨어의 개념적은 부분을 다이어그램으로 그리기 위해 사용된다
- 시각적으로 소프트웨어를 표현한다.

<br>

#### UML의 필요성

- 의사소통 하기 좋다
- 대규모 프로젝트의 구조에 대한 로드맵을 만들 때 유용하다
- 개발할 시스템 구축에 대한 기초를 마련할 수 있다
- 백엔드 문서용으로 적절하다

<br>

#### 개발 기술 환경을 정의할 때 고려해야할 사항

1. 운영체제
   - 하드웨어와 소프트웨어의 리소스를 관리하고 컴퓨터 프로그램을 위한 공통 서비스를 제공하는 소프트웨어
     - Windows - Microsoft
       - 중소규모, 개인 PC, 태블릿, 임베디드
     - Unix - IBM, HP, Sun
       - 대용량 처리, 안정성이 좋다, NAS, 데이터가 많을때 사용한다
     - Linux - Linus Tovalds
       - 중-대규모 서버
     - Android - Google
       - 스마트폰, 태블릿
2. DBMS
   - 사용자나 어플리케이션이 데이터베이스와 상호작용할 수 있도록 만들어진 SW
   - 데이터베이스의 생성, 조회, 변경 등의 관리가 주요 기능이다
   - Oracle, MySQL, MSSQL, MongoDB, MariaDB 등
3. WAS
   - Web Application Server
   - 동적인 웹 서비스
   - 웹 어플리케이션
   - 웹 서비스
   - 개발을 지원하기 위해 설계된 소프트웨어
   - 데이터 접근, 세션 관리, 트랜잭션 관리등을 위한 라이브러리를 제공한다
     - Apache Tomcat - Apache Tomcat Foundation에서 Servlet과 JSP를 이용한 동적인 웹 문서를 처리하기 위해 만든 WAS
     - Wildfly(Jboss) - 예전에는 JBoss 라는 이름이었다, 톰캣의 기본 Servlet Container 뿐만 아니라 EJB Container 를 별도로 제공하여 폭 넓은 서비스를 구현한다
     - Jeus - 국산 WAS, 대용량 데이터의 트랜잭션을 고성능으로 처리하며 개발 빛 운영에 관한 기술 지원이 뛰어나다고 하긴 하는데..(...)
4. 오픈소스
   - 소스코드를 공개해 누구나 특별한 제한 없이 그 코드를 보고 사용할 수 있는 오픈소스 라이센서를 만족하는 소프트웨어

<br>

#### 배치, Batch

- 일괄 처리
- 정해진 특정 시간에 실행되며 어떤 요청이 있을 때마다 실시간으로 통신(동작)하는 것이 아닌 한꺼번에 일괄적으로 대량의 작업을 처리하는 것

<br>

#### 트랜잭션, Transaction

- 데이터 베이스의 상태를 변화시키기 위해 수행하는 작업들의 단위

<br>

### ERD, Entity Relation Diagram

- 개체 관계도
- Entity, 엔티티 : 테이블
- Attribute, 속성 : 컬럼
- Relation, 관계 : PK - FK 관계 등

<br><br>