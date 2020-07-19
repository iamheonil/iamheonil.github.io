---

layout: post
comments : true
title: '[Spring] Java 스프링 프레임워크 프로젝트 생성'
subtitle: ''
date: 2020-07-19
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 160

---
> Spring 첫 프로젝트 만들기

<br>

1. File - new - other 선택
2. Spring 폴더 찾기
3. Spring Legacy Project 선택
4. 제일 밑에 Spring MVC Project 선택
5. 프로젝트 이름 입력

<br>

- Top-level Package 입력
  - 3단계로 이루어진 기본 패키지 (xcode 에서 com.username.www ~~ 쓰는것과 똑같은 원리)
- Finish



<br>

### 스프링 프로젝트에 적용되어 있는 JRE 버전 바꾸기

1. 프로젝트 폴더 우클릭
2. Build Path 메뉴 - Configure build path 클릭
3. 왼쪽 사이드 메뉴 중에서 Project Facets 선택
4. Java 항목에서 1.6 을 1.8 로 변경 선택
5. Apply

<br>

변경 확인은 왼쪽 사이드 메뉴나 프로젝트 우클릭 - Build Path - Libraries 탭에서 JRE Library 의 버전을 확인할 수 있다 <br>

Libraries 탭에서 JRE Library 삭제 후 다른 버전으로 바꿀 수 있다

<br>

### 프로젝트 적용된 스프링 버전 바꾸기

1. 프로젝트 내 pom.xml 파일 열기
2. &lt;properties> 태그 확인
3. &lt;org.springframework-version> 항목의 값을 변경한 후 저장한다
   5.2.7.RELEASE 를 사용할 예정

<br>

버전 정보를 변경하고 저장하면 이클립스가 곧바로 다운로드를 시작한다, 잘못된 버전을 입력하거나 오타를 입력하면 버그가 생길 수 있으니 주의해야한다

<br><br>