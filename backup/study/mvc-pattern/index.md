---

layout: post
comments : true
title: 'MVC Pattern 에 대하여'
subtitle: ''
date: 2020-05-19
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 123

---

> MVC 패턴

<br>

- 프로그램을 세가지 파트(역할)로 구분하여 개발하는 방법론
- MODEL 2 기반의 MVC패턴을 적용한다
- Model, View, Controller 의 약자

<br>

- Model
  - 데이터베이스(저장소)의 데이터를 처리하는 파트
  - 데이터베이스(저장소)의 데이터를 관리
  - DAO, DTO 가 Model 에 해당한다.
- View
  - 사용자가 보는 화면을 구성하는 파트
  - 프레젠테이션 로직
- Controller
  - 사용자의 입력처리, 프로그램 흐름제어, 사용자와의 상호작용
  - 비지니스 로직
- 웹 프로그래밍에서는 Controller의 역할을 나누어 Service Layer를 둔다.
  - Service 계층은 비지니스 로직의 일부

<br>

- Controller 의 역할

  1. 사용자의 입력 처리
  2. 데이터베이스 데이터 처리(가공)하기
  3. 도메인(Domain) 객체를 처리하는 로직
     - 도메인 객체 == DB데이터 객체 == VO == DTO
  4. View 의 요청, 어떤 화면을 보여줄 것인지 View를 선택한다, Model(DB 데이터) 과 View(화면)의 연결지점이 된다.
     - DAO가 처리한 결과를 View에 전달한다.

  - 역할 3번(도메인로직)을 Service가 담당하도록 만든다. 
  
  <br><br>