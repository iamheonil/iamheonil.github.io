---

layout: post
comments : true
title: '예외 처리 구문'
subtitle: 'Exception Handling'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 24

---

> 예외 처리 구문, Exception Handling

- try ~ catch 구문

  - MultiCatch

  

  

  <br>

  ```java
  try { 
  	// 예외가 발생할 수 있는 코드
  } catch(Exception e) {
      // 예외 처리 코드
  } finally { 
  	// finally 는 생략 가능하다.
      // 특수한 경우 사용하게 되는데, try단에서 예외가 발생하여 프로그램이 종료 된 경우
      // 실행이 안된 남아있는 코드들 중 반드시 실행해야하는 코드를 finally에 넣는다.
      // 프로그램이 예외가 없어 종료되지 않아도 무조건 실행된다.
      // 주로 Checked Exception 에서 사용하는 경우가 많다.
      // 자원해제할 때 사용하는 코드.
  }
  
  ```

  

  <br>

  일반적인 try catch

  ``` java
  package kh20200312;
  
  public class Exception03_Try {
  	public static void main(String[] args) {
  
  		System.out.println("\n와일문 가즈앙\n");
  
  		int[] arr = new int[5];
  		int i = 0;
  
  		try {
  			while (true) { // 무한루프
  				arr[i] = i + 1;
  
  				System.out.println(arr[i]);
  				System.out.println(i + "번째 완료");
  
  				i++;
  			}
  		} catch (ArrayIndexOutOfBoundsException e) { // Exception 으로 try catch 문 사용이 가능하지만 보다 안전하게 Exception 명을 써준다.
  			// TODO: handle exception
  			System.out.println("!! 예외 발생 !!");
  			
  			e.printStackTrace();	// 예외의 정보를 출력
  		}
  
  		System.out.println("\n프로그램이 정상적으로 종료되었습니다.");
  	
  	}
  }
  ```



MultiCatch

```java
package kh20200312;

public class Exception05_MultiCatch {
	public static void main(String[] args) {

		try {
			
			
		} catch (NullPointerException | ArithmeticException | IndexOutOfBoundsException e) {	
            				// MultiCatch
			System.out.println("예외 발생.");
			
		} 
		catch (Exception e) {
			
		}
		
	} // Main End
} // Class End
```


<br><br>