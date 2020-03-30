---

layout: post
comments : true
title: '자바 예외의 기본'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 25

---

> Throw





```java 
public class Exception06_Throw {
	public static void main(String[] args) {

		Exception e = new NullPointerException(); // 예외 객체 생성
//		 Exception 은 Checked

//		NullPointerException e = new NullPointerException();	// 예외 객체 생성
		// NullPointer 는 Un Checked이기 때문에 위의 소스는 작동하지 않는다.
		// 다만 try catch 문으로 감싸주면 실행 가능하다.

//		throw e;

		try {
			throw e;
			
		} catch (Exception e2) {
			// catch(Exception e) 부분은 이름 충돌이 날 수 있기 때문에
             // e1, e2 등과 같이 이름을 수정해서 사용한다.
			
            e2.printStackTrace();
		}

	}
}
```





> 예외 발생시키기, throw 키워드



개발자가 직접 예외를 발생시키기 위해 사용하는 키워드

- 사용방법
  - throw 예외객체;
  - throw new 예외클래스();



1. 예외 객체 생성



```java
Exception e = new Exception();
throw e;
// 예외 객체 생성 후 예외 발생 시키기
```



2. 객체 생성후 바로 



```java
throw new NullPointerException(); 
```





```java
class ThrowTest {

	public void print(String string, int i) {

		if (string == null) {
			throw new NullPointerException();
//			throw new ArithmeticException();
		}

		for (int y = 0; y < i; y++) {
			System.out.println(string);
		}

	}
}

public class Exception07_Throw {
	public static void main(String[] args) {

		ThrowTest tt = new ThrowTest();

		tt.print("HI", 3); // HI 를 3번 출력.

		try {
			tt.print(null, 3); // NULL 3번 출력.

		} catch (Exception e) {
			System.out.println("문자열이 Null");

		}

	} // Main Method End
} // Class End

```



<br><br>