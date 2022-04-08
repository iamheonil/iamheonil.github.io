---

layout: post
comments : true
title: '[Spring] Java 스프링 프레임워크 의존성 주입'
subtitle: ''
date: 2020-07-19
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 159

---
> 스프링 의존성 주입

<br>

의존성, Dependency

- 특정 객체가 작동하기 위해 필요한 외부 객체와의 연결

<br>

``` java
public class EmpController {
  
  // EmpController class는 EmpService 객체에 의존적이다
  private EmpService empService = new EmpServiceImpl();
  
}

// EmpController Class 가 작동하기 위해서는 EmpService 객체가 필요하게 된다,
// 그러므로 private EmpService empService = new EmpServiceImpl(); 를 선언하는데,
// 이때부터 의존관계가 되는 것
```



<br>

의존성 주입, Dependency Injection, DI

- 객체가 의존성을 직접 발생시키지 않고 외부(스프링)의 도움을 받아 주입되는 것
- 생성자 의존성 주입
- Setter(메소드) 의존성 주입

<br>

IoC, Inversion Of Control

- 제어의 역전
- 프로그램 흐름의 제어권이 역전되었다는 뜻
- 프로그램의 동작 흐름을 스프링 프레임워크가 담당하게 된다

<br><br>