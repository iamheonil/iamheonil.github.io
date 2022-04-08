---

layout: post
comments : true
title: '[Spring] Java 스프링 프레임워크 Annotation'
subtitle: ''
date: 2020-07-25
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 163

---
> Spring Annotation

<br>

- 어노테이션은 자바 1.8 버전부터 지원한다
- 스프링은 어노테이션을 이용하여 bean과 관련된 정보를 설정할 수 있다

<br>

### 스프링에서 어노테이션을 사용하기 위해 필요한 설정
  
1. 의존성 관련 어노테이션
   &lt;context:annotation=config/> 태그를 applicationContext.xml 에 등록하면
   @Autowired, @Required, @Resource 등을 사용할 수 있다
  
2. bean 으로 등록하는 것과 관련된 어노테이션
   &lt;context:component-scan base-package=""/>
   context:annotation-config + @Component, @Controller, @Service, @Repository 등
   @Component : 클래스 위에 선언하며, 해당 클래스를 자동으로 bean으로 등록한다, bean 의 이름은 해당 클래스명이 사용된다 (첫글자는 소문자)
  
   @Controller : Spring MVC 에서 컨트롤러가 인식되게 해주는 어노테이션, 클래스 위에 @Controller 어노테이션을 지정해야 RequestMapping, RequestParam 등을 사용할 수 있다  
   @Service : Component 와 동일하다, 가독성을 위해서 만약 해당 클래스가 Service 역할을 한다면 Service 어노테이션을 사용하는걸 권장한다  
   @Repository : Dao 역할을 하는 클래스에 적용이 된다. 발생하는 SQLException(Checked Exception) 을 DataAccessException(UnChecked Exception) 으로 바꿔준다  
  
3. Spring MVC 와 관련된 Annotation  
  
   &lt;mvc:annotation-driven />  
   @RequestMapping, @Valid 등을 자동으로 처리한다  
  
<br>

### 각 Annotation 설명

- @Autowired : Spring 에서 의존관계를 자동으로 설정할 때 사용한다, 생성자(매개변수), 메서드(매개변수), 필드변수에 적용이 가능하다 해당 타입의 bean 객체가 applicationContext 에 존재하지 않거나 2개 이상이면 예외가 발생한다
  - 예외를 피하기 위해 @Qualifier 을 사용하게 되는데, 2개 이상의 bean 중에서 특정 bean 을 사용할 수 있도록 지정하는 어노테이션. 아이디로 지정이 가능하다
- @Resource : 어플리케이션에서 필요로 하는 의존성 주입을 해준다, 빈 객체의 이름을 지정해서 의존성 주입한다
- @Required : 필수 프로퍼티임을 명시(반드시 bean 의 생성과정에서 호출되어야 하는 Setter 메소드) Setter 메서드 위에 적용하고 필수 프로퍼티를 설정하지 않으면 bean이 생성되지 않는다

<br>

** @Component 로 올라가는 bean 은 singleton 이다

<br><br>