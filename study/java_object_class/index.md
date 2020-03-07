---

layout: post
comments : true
title: '오브젝트 클래스'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 15

---

> 오브젝트 클래스 <br>

### 오브젝트 클래스
Object 클래스
- 패키지 : java.lang 
    + 자바의 모든 클래스의 최상위 부모 클래스
    + 모든 클래스는 Object를 상속받고 있다.
    + 자바 프로그래밍의 기본이 되는 클래스.
 
Object 클래스의 메소드
- 재정의(Override) 불가능 메소드
    + 스레드 동기화에 사용 ↓ 
	+ notify, notifyAll, wait 
 	
 	+ 클래스의 타입 정보를 반환(Class 타입) ↓
 	+ getClass
 
- 재정의(Override) 가능 메소드 - 개발자가 바꿔서 사용 가능하다.
    + toString, equals, hashCode, clone, finalize
 
- toString
    + 객체를 설명하는 문자열을 반환.
    + 기본리턴값 - "데이터타입@참조값" 형식의 문자열을 반환한다.
	+ Sysout 메소드의 전달인자 객체를 사용하면 해당 객체의 toString() 반환값을 출력한다.
 
- equals 
    + 동일성을 비교하는 코드 - Identity
 	+ 동일성이 아닌 동등성을 비교하는 코드로 바꿔줘야할 때	- Equality
 
- hashCode
    + 객체의 고유값을 반환한다.
    + 기본동작으로는 객체의 참조값을 10진수(int)로 반환한다.
    + String 은 같은 데이터라면 같은 hashCode 를 반환한다.
    + String 은 동등한 객체에서 같은 hashCode 를 반환한다.
    + 사용빈도가 적다. 			
 			
- clone
    + 객체 복사 메소드
    + protected 접근제한자로 설정되어있다.
 	+ 사용하려는 클래스에서 public 으로 오버라이딩한 후 사용한다.
 	+ 반환 타입이 Object이므로 형변환이 필요하다.
 	+ 예외처리구문(try/catch)을 추가해야한다.
 	+ clone()을 구현하는 클래스는 interface Cloneable을 상속(구현처리)해야한다. 
 	+ 성공적으로 수행했다면 깊은 복사가 이뤄진다.
	+ 사용빈도가 적다. 

- finalize
    + GC(Garbage Collector)가 객체를 파괴할 때 호출하는 메소드
 	+ 자바에서는 사용하지 않으므로 절대 건들지 말 것
 			
- Math
    + 수학적인 연산을 정적메소드로 제공하는 클래스
	+ 멤버필드로 E(자연상수), PI(원주율) 두 가지를 정적멤버로 가지고 있다.
	+ 사용방법 <br>
	System.out.println(cos(30.0));
			
<br><br>