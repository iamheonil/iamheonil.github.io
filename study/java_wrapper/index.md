---

layout: post
comments : true
title: '박싱과 언박싱, 파싱'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 17

---

> 박싱, 언박싱, 오토박싱, 오토 언박싱, 파싱까지 <br>

박싱, Boxing
- Wrapper : 포장지
- 기본 데이터타입 -> 객체화
- ** 기본 데이터타입의 데이터를 객체화하여 사용할 수 있게 해주는 클래스들 **
<br>
<br>

기본형 타입 데이터를 참조형 변수로 사용할 수 있게 된다.
- Boolean
- Character
- Byte, Short, Integer, Long
- Float, Double
<br>
<br>

언박싱, Unboxing
- Wrapper 클래스 -> 기본 데이터타입 변환
- Wrapper 클래스의 메소드를 이용한다.
- int i2 = iVal2.intValue();  Integer 에서 int 타입으로 변환해주는 코드
<br>
<br>

오토 박싱, 오토 언박싱
- 박싱, 언박싱이 자동으로 이루어지는 현상
- 기본 데이터타입과 참조형(Wrapper)를 따로 구분하지 않고 사용할 수 있다.
```java
// ex)
		 Integer iVal = new Integer(123);
		 int num = 456;
		 int sum = iVal + num;  // 에러없이 작동한다.
```
<br>
<br>

파싱
- 문자열에서 데이터를 추출하는 기능
- Wrapper 클래스의 정적메소드로 구현된 parseXXX() 메소드를 이용한다.
- 각 데이터타입에 맞는 형태의 문자열에서 해당 데이터타입으로 추출한다.

``` java
// ex)
		 String str = "1234";
		 int num = Integer.parseInt(str);
		 double d = Double.parseInt("3.14");
//		 ** Character 에는 파싱 메소드가 존재하지 않는다.
//		 ** 대신 "문자열".charAt(idx) 를 사용한다.
//		 ** Boolean형은 "true"만 제대로 파싱하고 나머지 문자열은 무조건 false로 반환.

```

<br>


<br><br>