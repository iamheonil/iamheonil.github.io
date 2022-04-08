---

layout: post
comments : true
title: '[Spring] Java 스프링 프레임워크 @Autowired'
subtitle: ''
date: 2020-07-19
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 161

---
> @Autowired 의 바인딩 전략

<br>

- 바인딩 : 실행코드와 정의코드가 연결되는 것
- 주로 메소드 호출코드와 메소드 정의코드가 연결되는 것을 의미한다
- @Autowired 는 객체변수와 스프링 Bean 을 연결하는 것을 뜻한다 (DI, **Dependecy Injection**)

<br>

1. byType
   - 스프링 Bean 의 이름(id)에 상관없이 같은 타입의 Bean 이 한 개만 존재한다면 바인딩한다
   - 같은 타입으로 등록된 Bean 이 두가지 이상 존재한다면 예외처리가 발생한다
     - NoUniqueBeanDefinitionException
2. byName
   - 같은 타입의 빈이 여러 개 등록되어 있더라도 지정된 이름의 빈을 바인딩
   - 이름이 지정되지 않았다면 스프링 빈의 id와 멤버필드의 이름을 비교해서 바인딩



### 같은 이름으로 여러 개의 스프링 빈이 등록되어있을 경우는 고려하지 않아도 된다!

-> XML 파일의 id 는 중복될 수 없다

<br>

- ### DI 어노테이션(@)

  1. @Autowired
     - 패키지 : org.springframework.beans.factory.annotation.Autowired
     - 스프링에서 제공하는 DI 어노테이션
     - 적용가능 위치 : 멤버필드, 생성자, 파라미터가 존재하는 메소드
     - DI 전략 : byType 먼저, byName 나중에
  2. @Resource
     - 패키지 : javax.annotation.Resource
     - 자바 표준으로 제공되는 DI 어노테이션
     - 적용가능 위치 : 멤버필드, 파라미터가 한계인 setter
     - DI 전략 : byName 먼저, byType 나중에
  3. @Inject
     - 패키지 : javax.inject.Inject
     - 자바 표준으로 제공되는 DI 어노테이션
     - @Autowired 랑 기능이 똑같다
     - Spring 3.0 버전 이상부터 사용 가능하다
     - javax.inject.Inject-버전명.jar 라이브러리가 필요하다
     - @Resource 강화 버전

  

  <br>

  #### @Qualifier("beanName")

  - DI 어노테이션의 보조 기능
  - 바인딩될 스프링 빈의 이름(beanName)을 직접 지정할 수 있게 해주는 어노테이션

<br><br>