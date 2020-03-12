---

layout: post
comments : true
title: '프로그램 개발 오류(Error)'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 23

---

> 프로그램 개발 오류, Error

<br>

1. 컴파일 타임 에러 (Compile-time Error)

   - 컴파일 시점에 발생하는 에러

   - 이클립스에서는 소스코드를 저장하는 즉시

   - 주로 문법 에러(Syntax Error)

     

2. 런타임 에러 (Runtime Error)

   - 프로그램 수행 중 발생하는 에러

   - 수행할 수 없는 작업을 시도할 때 발생

   - 주로 Exception(예외) 처리 된다.

     - NullPointerException : null 값을 참조해서 코드 수행 시
     - ArrayIndexOutOfBoundsException : 배열에 Index 지정을 잘못 했을 때
     - ArithmeticException : 불가능한 산술연산 수행 시

     

3. 논리 에러 (Logical Error)

   - 프로그램이 에러없이 잘 작동한다.
   - 프로그램의 흐름, 동작이 개발자의 의도대로 수행되지 않을 때
     - ex) 무한루프



<br>

> Throwable 클래스

- 에러와 예외 클래스의 부모 클래스





Throwable 클래스의 계층구조

```java
Object
   |
   |
Throwable --------------- |
   |					|
   |					|
 Error				Exception
(Critical Error)		 | --------------- |
    			여러 Exception		Runtime Exception
		   		(Checked Exception)			 |
   									   	    |
	    								여러 Exception
    									(UnChecked Exception)
```



- Error

  - 복구 불가능한 심각한 에러

- Checked Exception

  - Exception의 하위클래스들 중 RuntimeException의 하위클래스를 제외한 것.

  - 반드시 예외처리 구문(Try - Catch)으로 예외 처리를 해야만 하는 클래스

    - 예외처리하지 않으면 컴파일 에러가 발생한다.

  - 코드 작성단계에서 미리 체크해서 예외처리구문을 작성해야 한다.

    - IOException, SQLException 등이 있다.

    

- UnChecked Exception

  - RuntimeException의 하위 클래스
  - 반드시 처리하지 않아도 되는 예외
  - 프로그램 실행도중 예외가 발생하면 결과를 보고
    - 예외가 발생하지 않도록 코드를 수정
    - 예외처리 구문을 작성하여 처리되도록 수정
      - NullPointerException, IndexOutOfBoundsException 등





<br>

<br>

> Error 클래스, 에러

- 심각한 수준의 오류를 뜻한다.
- 복구가 불가능하다.
- 프로그램이 무조건 중단된다.
- 시스템에 변화를 주어 문제를 해결해야한다.
- 프로그램 자체가 해결이 불가능한 수준의 문제.
  - ex) OutOfMemoryError



<br>

<br>

> Exception 클래스, 예외

- 프로그램의 예외적인 상황
- 개발자가 Exception 을 예측하여 프로그램 로직으로 처리가능한 수준의 오류
- 논리적으로 예상 가능했던 상황
- 미리 예외 상황을 처리해줘야 한다.
  - Exception Handling
    - Try, Catch 구문을 이용





```java
package kh20200312;

public class Exception01_Basic {
	public static void main(String[] args) {

		// IndexOutOfBoundsException
		int[] arr = new int[5];
		System.out.println(arr[4]);
//		System.out.println(arr[5]);

		// NullPointerException
		int[] arr2 = new int[5];
		System.out.println(arr2[4]);
		arr2 = null;
//		System.out.println(arr2[6]);

		System.out.println("\n와일문 가즈앙\n");
		int i = 0;
//		while(true) {	// 무한루프
//			arr[i] = i + 1;
//		
//		System.out.println(arr[i]);
//		System.out.println(i + "번째 완료");
//		
//		i++;
//		
//		}

		while (true) { // 무한루프를 해결

			if (i < 0 || i >= arr.length) {
				System.out.println("\n인덱스는 " + arr.length + "보다 작아야 합니다.");
				
				break;
			}

			arr[i] = i + 1;
			System.out.println(arr[i]);
			System.out.println(i + 1 + "번째 완료");

			i++;

		}

	}
}
```



<br>

- 예외 발생 시 체크사항

  1. 예외 클래스 이름

     - java.lang.ArrayIndexOutOfBoundsException
       - 배열의 인덱스를 벗어나서 접근하려고 할 때 발생한다.
         - UnChecked Exception

     

  2. 발생 지점

     - at kh20200312.Exception01_Basic.main(Exception01_Basic.java:20)

     

  3. 에러 메세지

     - 5번



<br><br>