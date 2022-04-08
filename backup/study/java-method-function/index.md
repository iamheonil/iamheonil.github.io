---

layout: post
comments : true
title: '메소드와 함수'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 4

---

> 메소드와 함수의 기본 개념 <br>

### 메소드와 함수

메소드(Method), 함수 (Function) <br>
클래스이 기능 또는 동작 또는 행위 등을 정의하는 코드 <br>
객체 변수를 통해 호출하여 사용한다. <br>
객체들 간의 데이터 전달(주고 받는) 수단으로 사용한다. <br>
<br>

메소드의 기본형태 작성

  1. 메소드 이름 작명, 만들고자 하는 기능을 대표하는 이름으로 적절히 작명한다.
  2. 매개변수를 작성한다. ( )의 안을 채우는 작업 -> 기능을 수행하는데 필요한 입력 값을 저장하는 변수.
  3. 실행코드를 작성한다. { }의 안을 채우는 작업 -> 메소드가 수행할 기능을 작성, 구현한다.
  4. 리턴코드를 작성한다. 실행코드 작성 후 실행코드의 처리를 어떻게 할 것인지 정한다.
  5. 리턴코드의 데이터타입을 작성한다. return 코드 값의 데이터 타입을 명시한다.

메소드 정의 방법 <br>

접근제한자 리턴타입 메소드의 이름 (매개변수) { <br>
 			실행코드 <br>
 } <br>
<br>

ex)

```java
public int add (int num1, int num2) {
 		// 실행코드
        int result = num1 + num2;
                                     
        return result;
        // 실행결과 num1 + num2 가 리턴.
 }
```

<br>

return 데이터가 없으면 return 타입은 void로 작성한다. <br>
void - 텅 빈, 공허한 <br>

매개변수가 없다면 괄호 ( ) 안을 비어둔다. <br>

<br><br>