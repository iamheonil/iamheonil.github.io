---

layout: post
comments : true
title: '멀티스레딩 관련 클래스'
subtitle:
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 35

---

> 멀티 스레딩 관련 클래스

<br>

- interface Runnable
  - run() 추상 메소드를 가지고 있다.
  - run() 메소드는 스레드화 될 수 있는 코드를 정의할 수 있다.
  - 스레드 코드를 작성(정의)하는 메소드
- class Thread implements Runnable
  - run() 메소드를 가지고 있다.
  - 스레드를 제어하고 관리하는 메소드들을 정의하고 있다.
    - 스레드의 정보를 확인할 수 있게 해준다.
  - 스레드를 실행시킬 수 있다.
    - start() 메소드 사용

<br>

> 스레드 제어 메소드

<br>

- 스레드의 동작을 제어하는 메소드
- 스레드 생명 주기(Life Cycle)에 영향을 준다.
  - public static void sleep(long millis) throws InterruptedException
    - 주어진 밀리초만큼 sleep을 호출한 스레드를 일시정지 시킨다.
  - public final void join() throws InteruptedException
    - 스레드가 종료될 때 까지 기다린다.
  - Thread Scheduling, 스레드 스케줄링
    - Round Robin, 순환할당 : time slice만큼 번갈아 가면서 실행한다.
    - Time slice, 시간조각
  - Priority
    - 우선순위 : 우선순위가 높은 스레드를 좀 더 많이 실행한다.
  - 자바는 Round Robin, Priority 알고리즘을 섞어 스케줄링을 수행한다.

<br>

```java
// 우선순위의 적용

		py1.setPriority(Thread.MIN_PRIORITY);	// 1
		py2.setPriority(Thread.NORM_PRIORITY);	// 5
		py3.setPriority(Thread.MAX_PRIORITY);	// 10
```

<br>

- 스레드의 스택트레이스 확인

  ```java
  package kh202003.kh20200318.thread;
  
  class Thread06 extends Thread {
  	@Override
  	public void run() {
  		method01();
  	}
  
  	public void method01() {
  		method02();
  	}
  
  	public void method02() {
  		method03();
  	}
  
  	public void method03() {
  		try {
  			throw new Exception();
  		} catch (Exception e) {
  			e.printStackTrace();
  		}
  	}
  }
  
  public class Ex06_StackTrace {
  	public static void main(String[] args) {
  
  		Thread06 th06 = new Thread06();
  		
  		th06.start();
  		
  		th06.run();
  		
  	}
  }
  ```

<br>

>  스레드 동기화, Thread Synchronization

<br>

- 여러 스레드가 하나의 같은 자원에 접근하려고할 때 동시에 접근하는 상황을 막기 위한 처리
- 스레드가 자원에 접근 하면 다른 스레드가 접근할 수 없도록 막는다. (Lock을 건다고 표현한다.)
- 작업이 완료되면 Lock을 해제한다.

<br>

임계영역, Critical Section

- 이 안에서 일어나는 일이 프로그램에 영향을 미친다.
- 동기화를 처리하는 영역이다.(Lock이 걸리는 공간)
- 여러 스레드들이 자원에 동시에 접근하는 것을 막는 영역
- 자바에서 Synchronized 키워드를 이용하여 구현한다.
- 임계영역 객체마다 만들어진다.
- 같은 클래스타입이더라도 다른 객체라면 서로 다른 임계영역을 가지고 있다.

<br>

동기화 영역 설정 방법

- 동기화 메소드
  - 접근제한자 synchronized 리턴타입 메소드명(매개변수) {     }
  - 메소드가 임계영역으로 설정된다.
  - 한번에 하나에쓰레드만 이 메소드를 호출할 수 있게 된다.
- 동기화 블록
  - 중괄호 블록 {     } 에 synchronized 키워드를 붙인 것
  - synchronized(객체) {     }

<br>

임계영역(동기화영역)의 LOCK 상태 통지 (알림)

- wait(), notify(), notifyAll();
- 반드시 임계영역 내에서 호출해야 한다.
- 임계영역에 접근 권한(Lock)의 상태를 알리는 메소드이다.

<br>

- wait()
  - LOCK 반납
  - notify 신호통지를 기다린다.
  - wait()을 호출한 스레드는 BLOCKED 상태가 된다.
- notify()
  - 대기상태의 **임의**의 스레드에게 LOCK 상태를 통지한다.
- notifyAll()
  - 대기 상태의 **모든** 스레드에게 LOCK 상태를 통지한다.
- notify(), notifyAll()
  - 임계영역에 대한 LOCK 이 반납되었음을 알린다.



<br>

동기화 주의사항

  - 공정성, Fairness
    - 모든 스레드가 자원에 접근할 기회를 공정하게 받아야한다
  - 기아상태, Starvation
    - 자원에 대한 접근 기회를 얻지 못하는 스레드의 상태
  - 교착상태, Deadlock
    - 스레드들이 서로 상대방이 사용중인 자원을 필요로하는데 서로 반납하지 않는 상황
  - 경쟁상태, Race Condition
    - 스레드들이 서로 자원 접근권한(LOCK)을 얻기 위해 경쟁하는 상태 ( 스케줄링 )


<br><br>