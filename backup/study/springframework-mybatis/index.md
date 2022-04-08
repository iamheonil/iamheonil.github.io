---

layout: post
comments : true
title: '[Spring] Java 스프링 프레임워크 MyBatis 연동하기'
subtitle: ''
date: 2020-07-19
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 162

---
> 스프링에 마이바티스 설치하기 (연동하기)

<br>

- 메이븐 툴을 이용하여 라이브러리를 설치한다
- <a href="http://mvnrepository.com" target="_blank">MVN Repository</a>

<br>

- ### 필요 라이브러리

- mybatis-spring

  - 스프링에서 마이바티스 사용할 수 있도록 해주는 라이브러리

  <br>

  

  ``` xml
  <dependency>
      <groupId>org.mybatis</groupId>
      <artifactId>mybatis-spring</artifactId>
      <version>2.0.5</version>
  </dependency>
  
  <!-- pom.xml 에 <dependency> 태그 사이에 추가 -->
  ```

  

  <br>

- mybatis

  - MyBatis 프레임워크

  <br>

  

  ``` xml
  		<!-- MyBatis 3.5.5 -->
  		<dependency>
  		    <groupId>org.mybatis</groupId>
  		    <artifactId>mybatis</artifactId>
  		    <version>3.5.5</version>
  		</dependency>
  ```

  

  <br>

- spring-jdbc

  - 스프링에서 JDBC 를 사용할 수 있게 해주는 라이브러리

  <br>

  

  ``` xml
  		<dependency>
  		    <groupId>org.springframework</groupId>
  		    <artifactId>spring-jdbc</artifactId>
  		    <version>5.2.7.RELEASE</version>
  		</dependency>
  ```

  

  <br>

- ojdbc

  - 자바 프로그램이 오라클 DB 에 연동할 수 있게 해주는 JDBC 라이브러리

  <br>

  

  ``` xml
  		<dependency>
  			<groupId>com.oracle</groupId>
  			<artifactId>ojdbc6</artifactId>
  			<version>12.1.0.2</version>
  		</dependency>
  ```

  

<br>
<br>