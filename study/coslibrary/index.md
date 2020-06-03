---

layout: post
comments : true
title: 'COS 라이브러리를 이용한 파일 업로드'
subtitle: ''
date: 2020-06-03
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: BackEnd
order: 138

---

> COS 라이브러리 파일 업로드

<br>

- com.oreilly.servlet.MultipartRequest 객체를 이용한다.
- 객체의 생성자를 통해서 업로드 설정을 한다.

<br>

#### MultipartRequest 클래스의 생성자

```java
public MultipartRequest() {
    
        HttpServletRequest request, // 요청 객체
    	String saveDirectory, // 파일 저장 위치
    	int maxPostSize, // 업로드 제한 사이즈
    	String encoding, // 인코딩
    	FileRenamePolicy policy // 중복된 파일이름 처리할 정책
     
} throws IOException
```

<br>

- MultipartRequest 의 주요 메소드

  - String getParameter(String name);
    - 요청 파라미터 얻기
  - Enumeration getParameterNames();
    - 요청 파라미터들의 name 들을 열거체(enumeration) 로 얻기
  - String[] getParameterValues(String name);
    - name으로 전달된 여러 개의 파라미터 값들을 문자열 배열로 얻기

  ----------------------------- 파라미터 처리

  - File getFile(String name);
    - 업로드된 파일 객체 얻기
  - Enumeration getFileNames();
    - 파일들의 name들을 열거체로 반환하기

  ---------------------------- 파일 처리

  - String getFilesystemName(String name);
    - 업로드된 파일 이름(저장된 이름, storedName)
  - String getOriginalFileName(String name);
    - 원본 파일 이름(originName)
  - String getContentType(String name);
    - 업로드된 파일의 형식(MIME 타입)

  

<br><br>