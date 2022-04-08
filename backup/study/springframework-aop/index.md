---

layout: post
comments : true
title: '[Spring] Java 스프링 프레임워크 AOP에 대해서'
subtitle: 'AOP - 관점 지향 프로그래밍'
date: 2020-07-25
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 164

---
> AOP, Aspect Oriented Programming

<br>

- 관점 지향 프로그래밍
  - 시스템의 규모와 복잡도가 증가하면서 기능별로 모듈화를 거치더라도 중복되는 코드가 생겨나게 된다
    - 트랜잭션 관리, 로깅처리 등
  - 이러한 코드들을 다시 한번 더 모듈화 해내어 분리하는 것이 AOP 이다
  - 재 모듈화 라고 생각하면 ~~이해가 쉬울 것이다~~

<br>

AOP 용어

- Advice
  - PointCut 에서 지정한 JoinPoint 에서 실행되어야 하는 코드
    - Around Advice : JoinPoint 의 앞과 뒤에서 실행되는 Advice
    - Before Advice : JoinPoint 의 앞에서 실행되는 Advice
    - After return Advice : JoinPoint 메소드 호출이 정상적으로 종료된 뒤에 실행되는 Advice
    - After Throwing Advice : JoinPoint 메소드 호출이 예외를 반환할 때 실행되는 Advice
- JoinPoint
  - Advice 를 적용할 수 있는 지점
  - Spring 에서는 Method 실행 저느 혹은 실행 후에 Advice 를 적용할 수 있다
- PointCut
  - JoinPoint 의 부분 집합으로 실제로 우리가 Advice 를 적용한 JoinPoint 이다
  - Spring 에서는 AspectJ 문법을 활용해서 PointCut 을 정의할 수 있다
- Weaving
  - Advice 를 로직코드에 적용하는 것
- Advisor
  - Advice + PointCut - 언제 무엇을 할 지 정의하는 것
- Target
  - 핵심 로직을 구현하는 클래스
- Proxy
  - 대상 객체에 Advice 가 적용된 후 생성된 객체

<br><br>