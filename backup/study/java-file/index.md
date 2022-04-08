---

layout: post
comments : true
title: '자바의 File'
subtitle: '파일 I/O'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 28

---

> File

<br>

- 파일 정보를 다루는 클래스
- 입출력대상으로 사용할 수 있다.

<br>

```java
File file = new File("파일의 경로", "파일의 이름");
```



<br>

> 절대경로와 상대 경로

- 절대 경로 : 루트 디렉토리부터 파일까지의 위치를 나타낸 것
- 상대 경로 : 클래스패스(ClassPath)로 부터 파일까지 경로를 적은 것.
  - 클래스패스(ClassPath) - 프로그램이 실행 된 위치
  - 이클립스는 프로젝트 폴더가 ClassPath로 적용되어 있다.



<br>

경로 지정 문자

- . -> 현재 디렉토리
- .. -> 부모 디렉토리
- / -> 루트 디렉토리

ex) /test/folder -> D:\test\folder\

ex) ./test -> 프로그램실행폴더/test

ex) D:/test/folder/../myfolder -> D:\test\myfolder



<br>

> class File의 생성자

<br>

- File(String path, String filename)

- File(File path, String filename)
  - File path 를 넣어주는 이유는 File class 가 폴더도 관리할 수 있기 때문.
- File(String filepath);
  - 경로, 파일명 따로 적는게 아니라 "D/test/myfolder/file.txt" 처럼 한번에 쓴다.



<br>



> File OutputStream

<br>

파일 출력 모드

- 쓰기모드 - 두번째 인자를 false
- 추가모드 - 두번째 인자를 true



<br><br>