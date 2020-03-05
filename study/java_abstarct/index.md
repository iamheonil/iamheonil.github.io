---

layout: post
comments : true
title: '추상화, Abstract'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 12

---

> 추상화(Abstract) <br>

### 추상화
클래스, 메서드를 정의할 때 사용한다. <br>
abstract 키워드를 적용하면 추상클래스, 추상메소드 라고 부른다. <br>
<br>
* 추상 클래스 <br>
    - 실체화(인스턴스)할 수 없다.
    - new 연산자를 사용할 수 없다.
    - 인스턴스를 생성할 수 없다.
    - 추상메소드를 멤버로 가질 수 있는 클래스.
<br>
접근제한자 abstract class [클래스명] <br><br>

```java
public abstract class 클래스명 {

}
```

* 추상 메소드 <br>
    - 메소드의 구현부(몸체, Body -> '{ }' 부분)가 없는 메소드
    - 구현되지 않고 추상화 된 메소드.
    - 추상메소드를 상속받은 자식 클래스는 반드시 추상메소드를 처리해야한다.
    - -> 오버라이딩을 이용하여 코드를 작성해줘야한다.
<br>
추상메소드의 형태 <br>
<br>
접근제한자 abstract 리턴타입 메소드명(매개변수); <br>

```java
private abstract void out();
```

추상 메소드를 멤버로 가지는 클래스는 반드시 추상클래스여야한다. <br>
<br>

자식 클래스가 추상 메소드를 상속받은 경우

* 추상클래스를 extends 한 경우
    1. 상속받은 추상 메소드를 구현한다. { } << 요 안을 채워넣는것. <br>
        오버라이딩이 동반 되어야 한다.
        -> 자식클래스가 추상메소드를 반드시 구현하도록 강제한다. <br>
    2. 자식 클래스를 추상 클래스로 지정한다.
    <br><br>
    
```java
// ex)
abstract class Parent {
    public abstract void out();

}
```

<br>
해결방법 <br>

1 <br>

```java
class Child extends Parent {
    
@Override
public void out() {

            
    }

}
```

<br>
해결방법 <br>

2 <br>

```java
abstract class Children extends Parent {

}
```

메소드를 호출하면 동적 바인딩.

<br><br>