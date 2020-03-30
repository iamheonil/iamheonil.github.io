---

layout: post
comments : true
title: '네트워크 관련 클래스'
subtitle:
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 33

---

> 네트워크 관련 클래스

<br>

> InetAddress class

<br>

- IP 정보 관리 클래스
- 생성자 없음
- 직접 객체생성 불가능
- 정적 메소드를 이용하여 정보를 얻어와야 한다.



<br>

> Localhost

<br>

- 가상 루프백(loopback) 호스트
- 루프백 호스트네임 : localhost
- 루프백 IP : 127.0.0.x
- 네트워크 상에서 자기가 자기 자신을 나타낼 때 사용하는 주소



<br>

> URL class

<br>

- URL 정보를 관리하는 클래스
- Uniform Resource Locator
  - 인터넷 상 정보(자원, Resource)가 어디있는지 표현하는 방법
  - 인터넷에 존재하는 자원에 접근할 수 있는 주소로 사용된다.
- URL 형식
  - 프로토콜://인터넷주소:포트번호/디렉토리/파일이름/쿼리스트링/참조
  - 프로토콜 : 자원에 접근하기 위해 사용된 통신규약
  - 인터넷주소 : 자원을 가지고 있는 서버의 주소
  - 포트번호 : 통신에 사용된 포트번호
  - 디렉토리, 파일명 : 자원이 저장되어있는 서버 내의 파일 위치
  - 쿼리스트링 : ? 문자 뒤에 작성하는 통신용 매개변수(전달인자)
  - 참조 : # 문자 뒤에 작성하는 문서 내 참조 위치



<br>



> 소켓, Socket

- Software 적인 통신 접속지점, 가상장치
- 통신에서 필요한 절차를 프로그램으로 직접 구현하지 않아도 네트워크 프로그램을 개발할 수 있도록 만들어진 API
- 자바에서는 class 로 제공된다.
- 데이터 패킷화, 패킷마다 IP 부여하기, 네트워크를 통한 패킷 전달 등의 과정을 알아서 처리해준다.

<br>

소켓 통신

- 서버 소켓과 클라이언트 소켓을 이용해서 서로 통신하는 것
- 소켓 프로그래밍, TCP 프로그래밍, 네트워크 프로그래밍 이라고 한다.
- 서버 소켓 : ServerSocket class(TCP), DatagramSocket class(UDP)
- 클라이언트 소켓 : Socket class(TCP), DatagramPacket class(UDP)


<br><br>