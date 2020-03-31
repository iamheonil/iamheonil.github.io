---

layout: post
comments : true
title: 'Database Schema'
subtitle: 'Database 스키마'
date: 2020-04-01
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 61

---

> 스키마, Schema

<br>

- 데이터베이스의 구조
- 데이터베이스에 대한 메타데이터

<br>

데이터베이스를 바라보는 관점에 따라 분류한 스키마

- 개념 스키마 : 전체적인 구조, DB의 전체적인 논리 구조 개체들의 관계(Relation), 제약조건 등을 나타낸다. DB의 보안/권한/무결성 등을 정의한 것
- 내부 스키마 : 프로그래머 입장에서 보는 관점의 데이터베이스 구조, DB의 물리적인 저장구조, HDD에 어떻게 저장되어 있는지에 대한 관점
- 외부 스키마 : 사용자관점에서 바라보는 데이터베이스 구조, SELECT 구문을 수행하여 조회된 결과

<br><br>