---

layout: post
comments : true
title: 'String, 문자열'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 18

---

> String 심화 (2020년 02월 21일 kh20200221_string의 StringEx 추가내용) <br>

String
- 문자열을 저장할 때마다 새로운 공간을 할당한다.

``` java

	String str = "Apple";
	str = "BaNaNa";
	str = "Cherry";

```
<br>
String 은 상수이기 때문에 새로운 문자열을 대입하면 기존의 공간은 그대로 내비두고 <br>
새로운 공간을 만들어주고(생성하고) 그곳을 참조한다. <br>
<br>
문자열을 수정할 때에도 새로운 공간을 할당한다. <br>
기존의 값을 가지고 있으면서 수정, 삭제할 때 매번 새로운 공간을 할당한다. <br>
어떻게 보면 낭비가 될 수 있다는 단점을 가지고 있다. <br>
그러므로 단순 문자열을 저장할 때 좋다. (더 이상 편집되지 않는 문자열) <br>
문자열의 값의 변경이 자주 발생할 경우 메모리 효율, 성능효율이 전부 떨어진다. <br>
<br>
<br>
문자열의 수정, 삭제가 자주 발생할 경우 StringBuffer, StringBuilder를 사용하는 것이 좋다. <br>
- 객체 내부에 문자열 저장공간을 따로 만들어서 관리한다.
- 문자열 저장공간을 관리하면서 문자열을 다룬다 (크기 확장, 축소 가능)
- 수정이 빈번한 문자열 관리에 효율적이다.
- 문자열 저장공간의 크기(Capacity)의 기본값은 16개
- Capacity보다 더 긴 문자열을 저장해야할 때 크기가 확장된다.
- (기존 Capacity + 1) * 2 만큼 확장, 이거 보다 더 크게 저장하는 상황에서는
- length() 만큼 Capacity가 확장된다.
<br>
<br>
StringBuffer와 StringBulider의 차이점
- StringBuffer 는 모든 메소드가 동기화 처리되어 있다.(Thread-Safe, 스레드에 쓰기 안전)
- StringBuilder 는 비동기화 되어 있다.
- ** 동기화 Synchronized는 다음에 스레드 배울 때 다시 나옴
- Single Thread : 프로그램 코드를 하나만 실행 시키는 프로그램
- Multi Thread : 한번에 프로그램 코드를 동시에 여러개 실행 시킬 수 있는 프로그램
<br>
<br>
멀티스레드 환경에서
- StringBuffer는 스레드들이 내부 문자열 저장소를 순서대로 접근하게 만들어짐
- StringBuilder는 스레드들이 내부 문자열 저장소에 동시에 접근할 수 있음.
- 둘 중 뭐가 더 좋다고 말할 수는 없고 상황에 맞춰 적절하게 사용해야한다. *
- StringBuffer 는 동시 작업이 안된다, 빠르지가 않다는 말.	 ] 		둘 다 + String 까지
- StringBuilder 는 비동기작업이라 빠르다.					 ] 		아무거나 상관 없다
												        ]		스레드 들어가기 전까지는

<br>
<br>
<br>