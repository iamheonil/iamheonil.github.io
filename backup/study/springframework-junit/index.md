---

layout: post
comments : true
title: '[Spring] Java 스프링 트랜잭션 속성'
subtitle: 'Transaction'
date: 2020-08-07
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 167

---
> Spring jUnit 테스트

<br>

### Spring 테스트 환경 구축

1. spring-test, hamcrest-library, hamcrest-all, mockito-all Dependency 추가
2. 작업 중이던 프로젝트 우클릭 - Build Path - Libraries 이동 - 오른쪽 메뉴에 Add Library 클릭 - jUnit 선택 - jUnit library version : jUnit 5 확인하고 Finish - Apply and Close
3. 마이바티스를 연동해서 사용 중이라면 config.xml 파일에서 mappers 태그 지워주기
4. 스프링 폴더의 root-context.xml 로 이동해서 sqlSessionFactory 에 소스 추가해주기

<br>

``` xml
<property name="mapperLocations" value="classpath:mybatis/mapper/*.xml" />

```

<br>

5. mybatis 폴더를 src/test/resources 로 복사 - 붙여넣기
6. 프로젝트 우클릭 - Run as 클릭 - Run configuration - 좌측 메뉴에서 jUnit 찾은 다음 더블클릭 - 현재 사용중인 프로젝트 나오는거 확인하고 클릭 - Classpath - User Entries 클릭 - add External Jar - ojdbc6.jar 추가 - Apply - Run

<br>

> 테스트 환경 구축이 끝났으니 테스트 케이스를 작성해야한다

<br>

1. src/test/java 에 사용할 패키지를 만든다
2. 패키지 구성은 각자 알아서!
3. 테스트 클래스에 @WebAppConfiguration, @RunWith, @ContextConfiguration 추가
4. 테스트 케이스 작성해서 jUnit Test 로 실행
5. 결과 확인 후 수정이 필요하다면 수정하기

<br><br>