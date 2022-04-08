---

layout: post
comments : true
title: '[Spring] Java 스프링 트랜잭션 속성'
subtitle: 'Transaction'
date: 2020-08-07
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 168

---
> jUnit Assert 메소드

<br>

1. assertEquals(예상값, 결과값)
   - 예상값과 결과값이 일치하는지 비교한다
   - 기본타입은 값을 비교한다
   - 객체는 equals 메소드를 비교한다
2. assertSame(예상값, 결과값)
   - 예상값과 결과값이 같은 객체를 참조하고 있는지 판단한다 (같은 주소를 참조하고 있는지 - 배열의 주소라든지)
3. assertNotSame(예상값, 결과값)
   - 예상값과 결과값이 다른 객체를 참조하고 있는지 판단한다
4. assertNull / assertNotNul
   - 객체가 Null 을 참조하는지 참조하지 않는지 판단한다
5. assertTrue / assertFalse
   - 조건식의 결과가 참인지 거짓인지 판단한다
6. fail()
   - 테스트 결과를 실패로 처리한다
7. assertThat()
   - Matchers 라는 타입을 반환해주는 Hamcrest 라이브러리를 활용해 더욱더 정밀한 테스트 케이스를 작성할 때 사용한다

<br><br>