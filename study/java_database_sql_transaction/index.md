---

layout: post
comments : true
title: 'Database 트랜잭션'
subtitle: 'Transaction'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 58

---

> 트랜잭션, Transaction

<br>

- 데이터를 처리하는 일련의 작업 단위
- 클라이언트마다 관리되는 데이터베이스에 작업한 내역들을 트랜잭션이라고 한다.
- COMMIT, ROLLBACK 에 의해서 작업한 내역들을 반영하거나 되돌린다. [Commit & Rollback 이란?](https://naver.com)

<br>

트랜잭션의 상태 변화

- 트랜잭션의 시작
  - INSERT, UPDATE, DELETE 세 개중 하나를 수행했을 때
  - 실행 가능한 DML 문장이 수행 되었을 때부터 시작된다.
- 트랜잭션의 종료
  - Commit 또는 Rollback 수행 시
  - DDL 이나 DCL 문장을 수행했을 때 종료된다.

<br>

Auto Commit (자동 반영) 상황

- DDL, DCL 완료되는 시점
- SQLPlus 의 정상 종료(Exit 명령 수행)ㅇㅇ

<br>

Auto Rollback (자동 미반영) 상황

- 시스템의 비정상적인 종료
- SQLPlus의 비정상 종료(윈도우 창 닫기 버튼 클릭)

<br>

LOCK, 락

- ROW LOCK (행 단위 락)
- TABLE LOCK (테이블 단위 락)
- DB LOCK (데이터베이스 단위 락)
- 특정 사용자(클라이언트)에게만 해당 락 영역에 대한 접근을 허용하는 것
- 트랜잭션 변경사항은 ROW LOCK이 발생한다, 수정 후 Commit 을 해야 접근 가능하다.
- LOCK 영역에 접근하여 작업중인 클라이언트가 있으면 그 외 사용자는 LOCK 영역에 접근할 수 없다 (SELECT 도 불가능하다.)

<br><br>