---

layout: post
comments : true
title: '컬렉션 프레임워크'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 21

---

<img src = "https://github.com/iamheonil/iamheonil.github.io/blob/master/image/KakaoTalk_20200309_180659623.jpg?raw=true" width="100%">

> Class Properties

Hashtable 의 하위클래스

키(Key)와 값(Value)의 데이터타입이 String으로 제한되어 있음.

프로그램의 옵션정보, 데이터베이스 연결 정보, 다국어정보(Locale) 등 설정 파일을 프로그램이 읽고 저장할 때 사용할 수 있게 해준다.

주로 파일명.properties 확장자를 가진다.

<br>

> 스택, Stack

선입 후출 (First Input Last Output : FILO)

후입선출 (Last Input First Output : LIFO)

자바에서는 컬렉션의 Stack 클래스 타입으로 자료구조를 제공하고 있다.

메소드 호출 스택(Call Stack)에서 사용되는 알고리즘이다.

<br>

* class Stack의 주요 메소드(알고리즘) <br>
    push() : 입력, 스택에 데이터를 추가 <br>
    pop() :  출력, 스택에서 데이터를 반환 및 제거 <br>
    peek() : 데이터 확인, 다음 차례에 출력(pop())될 데이터를 반환한다.(제거되지 않는다.)<br>

<br>

> 큐, Queue

* DelayQueue <br>
    시간을 지정해주면 큐가 해당 시간동안 대기하게 된다. <br>
        
<br>

* PriorityQueue <br>
    우선순위 큐인데 추후 보강예정 <br>
    https://cjh5414.github.io/priorityqueue/ <br>
    http://asuraiv.blogspot.com/2015/11/java-priorityqueue.html <br>



선입선출 (First Input First Out : FIFO)

후입후출 (Last Input Last Output : LILO)

<br>

FCFS 알고리즘,

First Come First Served : 먼저 온 게 먼저 서비스를 받는다. (대기열 서비스에 적합)

구현체는 LinkedList를 주로 사용하고 Queue 는 interface로만 제공된다.

* Interface Queue 의 주요 메소드(알고리즘) <br>
    offer() : 데이터 입력, 데이터를 큐에 Enqueue 하게 된다. <br>
    poll() : 데이터 출력, 데이터를 Dequeue(제거) 하게 된다. <br>
    peek() : 데이터를 확인한다. (제거되지 않는다.) <br>
<br>

Enqueue(인큐) : 큐에 데이터 삽입하기(적용하기)

Dequeue(데크) : 큐의 데이터 제거하기(해제하기)


<br><br>