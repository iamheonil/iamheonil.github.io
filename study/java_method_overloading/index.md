---

layout: post
comments : true
title: '메소드 오버로딩'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 6

---

> 메소드 오버로딩 <br>

메소드 오버로딩(Method Overloading), 정해져있는 한계량보다 더더더더더더더 <br>
같은 이름의 메소드를 여러 개 정의하는 것. <br>

비슷한 기능을 하는 추가 메소드를 개발하기 위해 별도의 이름을 사용하지않고 기존의 메소드 이름을 사용할 수 있게 해준다. <br>

메소드 오버로딩 성립 조건 <br>
1. 매개변수가 달라야한다. (정확히는 데이터 타입이 달라야 함)
2. 매개변수에 들어간 데이터타입의 갯수가 달라야한다.
3. 반환 데이터타입은 오버로딩과 상관 없다. 

ex)
```java
public class Overloading_01 {
	
	private int x;
	private int y;

	// 멤버필드 x, y 를 출력하는 메소드 구현
	public void display() { // 매개변수가 없는 Display
		System.out.println("( " + x + ", " + y + " )");
	}
	
	// 매개변수를 대입해 메소드 오버로딩 기능을 구현.
	// int 형 2개를 전달인자로 받아 멤버 x, y 를 초기화 및 출력
	public void display(int x, int y) { // 매개변수가 있는 Display
		this.x = x;		// 초기화
		this.y = y;		// 초기화
		
    // System.out.println("( " + x + ", " + y + " )");	// 출력
    // 위의 display 가 x, y 를 출력하기 때문에 sysout 을 쓰는게 아니라 display(); 를 불러와 사용해도 된다.
		
		display();
		// 코드의 재사용
	}
	
	public void display(double d) {				//	다른
	}

	public void display(String d) {				//	타입의
	}

	public void display(int d) {				//	데이터형
	}
	
	// 리턴타입이 void, int 등 상관없이 메소드 오버로딩과는 연관이 없다.
	// 무조건 데이터형의 갯수와 타입이 달라야한다.
}
```

<br><br>