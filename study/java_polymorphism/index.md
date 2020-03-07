---

layout: post
comments : true
title: '다형성, PolyMorphism'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 13

---

> 다형성 (PolyMorphism) <br>

### 다형성

다형성
- 상속관계에 있는 클래스들에서 나타나는 특징

부모 클래스 타입으로 자식 클래스 타입들을 대신하여 코드를 작성할 수 있게된다.
- 이미 만들어둔 부모클래스 타입을 상속하여 중복으로 작성하지 않아도 된다.
- 코드 재사용성이 증가된다.

부모클래스 타입의 매개변수가 자식 클래스 타입들 대신 사용될 수 있다.<br>

```java
//ex)

public void method(Parent p) {
		Body
}

///	-> 오버로딩 해야하는 메소드의 수를 줄일 수 있다.

```

<br>
<br><br>