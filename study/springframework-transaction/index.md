---

layout: post
comments : true
title: '[Spring] Java 스프링 트랜잭션 속성'
subtitle: 'Transaction'
date: 2020-08-06
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 166

---
> Spring Transaction 속성

<br>



``` java
@Transactional(readOnly=true, isolation=Isolation.DEFALUT, rollbackFor=Exception.class)
```



<br>

1. propagation
   - 이미 진행 중인 트랜잭션이 존재할 때 새로운 쿼리가 호출 될 경우 어떻게 처리할 지 설정한다
   - @Transactional(propagation=Propagation.REQUIRED)
     - REQUIRED(기본값) - 진행중인 트랜잭션이 있다면 새로운 쿼리가 트랜잭션에 포함되고 진행중인 트랜잭션이 없다면 새로운 트랜잭션을 생성한다
     - REQUIRED_NEW - 항상 새로운 트랜잭션을 시작한다
     - SUPPORT - 이미 시작된 트랜잭션이 있으면 트랜잭션에 포함하고 없으면 트랜잭션 없이 진행한다
     - NOT_SUPPORTED - 트랜잭션을 사용하지 않는다
     - MANDATORY - 시작된 트랜잭션이 있다면 참여한다 그러나 시작된 트랜잭션이 없다면 예외를 발생시킨다
     - NEVER - 트랜잭션을 사용하지 않는다, 먼저 시작된 트랜잭션이 있으면 예외를 발생시킨다
2. isolation
   - 트랜잭션 격리 수준을 관리한다
     - 여러 트랜잭션이 진행될 때 트랜잭션의 작업 결과를 어떻게 노출할 것인지를 결정하는 기준
     - @Transactional(propagation=Propagation.REQUIRED, isolation=Isolation.DEFAULT)
       - DEFAULT - DB 설정을 따라간다
       - READ_COMMITED - COMMIT 처리를 하지 않은 정보를 읽는 것을 방지한다, 가장 많이 사용하는 격리 수준이다 ORACLE 의 기본값
       - READ_UNCOMMITED - COMMIT 처리를 하지 않은 정보를 읽을 수 있다
       - REPEATABLE_READ - 하나의 트랜잭션에서 읽고 있는 ROW 를 다른 트랜잭션에서 변경하는 것을 막아준다
       - SERIALIZABLE - 트랜잭션을 순차적으로 진행시킨다. 가장 강력한 트랜잭션 격리 수준이며 속도가 느리다는 단점이 있다
3. readOnly=true
   - readOnly 가 지정된 트랜잭션에서는 읽기만 가능
4. rollbackFor=Exception.class
   - 해당 예외가 발생했을 때 rollback 처리를 해준다
   - 원하는 예외를 지정할 수 있다
5. noRollBackFor=Exception.class
   - 해당 예외가 발생했을 때 rollback 처리 하지 않는다



<br><br>