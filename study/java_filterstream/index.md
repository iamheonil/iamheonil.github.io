---

layout: post
comments : true
title: '보조 스트림'
subtitle: 'FilterStream'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 29

---

> 보조 스트림, FilterStream

<br>

- 입출력스트림의 기능을 강화하는 보조 스트림
- 2차 스트림
  - BufferedStream
    - 클래스 내부에 버퍼를 가지고 있는 보조스트림
    - 입출력장치와 프로그램 사이의 입출력횟수를 줄여 성능 향상(속도)을 유도한다.
    - 기본적으로 사용되는 보조스트림
    - 스트림을 다룰 때 거의 항상 사용한다.
  - DataStream
    - 자바의 기본자료형 형식을 유지하면서 입출력한다.
    - 자료형에 맞는 입출력 메소드가 추가되어있다.
    - readBoolean, writeBoolean, readInt, writeInt, ... 등
    - 출력할 결과를 사람이 알아보기는 힘들다.
  - ObjectStream
    - 객체 단위로 입출력할 수 있도록 기능을 제공한다.
    - DataInput / DataOutput interface를 구현하고 있다.
    - DataStream의 기능을 다 사용할 수 있다.
    - ArrayList 같은 컬렉션도 객체형태를 유지하면서 입출력할 수 있다.
    - 입출력되는 객체는 직렬화 가능한 클래스여야 한다.


<br><br>