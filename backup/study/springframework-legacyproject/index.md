---

layout: post
comments : true
title: '[Spring] Java 스프링 레거시 프로젝트 만들기'
subtitle: 'Legacy Project'
date: 2020-07-30
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 165

---
> Spring MVC Legacy Project 생성하고 구성하기

<br>

1. Eclipse > new > other > Spring > Spring Legacy Project

2. Project name 설정 > Templates 영역 가장 하단에 Spring MVC Project 선택

3. Specific Setting 할 때 com.xxx.xxx 형식으로 주소를 입력해야하는데 최소한 3Depth 로 구성하는것이 좋다, 세번째 Depth 가 Context Path 로 지정된다

   ex) com.heonil.project -> project 가 Context Path
   -> localhost:9999/project

4. Tomcat 에 올리고 사용

<br>

1. pom.xml 환경설정
   - java 1.6 > java 1.8
   - SpringFramework 3.1.1 > 5.2.7
   - servlet API 2.5 > 4.0.1 & artifact-id servlet-api > javax.servlet-api
   - jsp-api 2.1 > 2.3.3 & artifact-id jsp-api > javax.servlet.jsp-api
   - maven-compiler-plugin source > 1.6 -> 1.8
   - maven-compiler-plugin target > 1.6 -> 1.8
2. 프로젝트 우클릭
   - configure Build Path > Project Facets  들어가서
     dynamic web module : 2.5 > 4.0
     java 1.6 > 1.8
3. Maven Project Update !

<br><br>