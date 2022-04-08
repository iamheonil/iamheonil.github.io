---

layout: post
comments : true
title: 'BackEnd DTO란?'
subtitle: 'Data Transmission Object'
date: 2020-05-16
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 119

---

> DTO, Data Transmission Object

<br>

- 데이터 전송 객체
- 계층(Layer) 간 데이터 교환을 위해 작성되는 자바 클래스

<br>

- DTO 작성 규칙
  - 멤버 필드는 모두 Private 접근 제한자를 적용한다.
  - 메소드는 getter, setter, toString 만 작성한다. 
    - 추가적인 일반메소드는 작성하지 않는다.
    - 데이터 이외의 추가 기능을 넣지않고 데이터에만 집중한다.
  - 클래스명을 데이터베이스의 테이블명으로 하는것이 좋다.
    - 클래스의 필드명은 데이터베이스의 컬럼명으로 작성하는 것이 좋다.

<br>

- DTO 와 유사한 VO, Value Object
  - 데이터를 저장하기 위해 작성되는 자바 클래스
  - VO와 DTO는 거의 동일하지만 큰 차이점은 VO는 데이터를 저장하기 위한 객체, DTO는 데이터 교환을 위한 객체라고 생각하면 쉽다.

<br><br>