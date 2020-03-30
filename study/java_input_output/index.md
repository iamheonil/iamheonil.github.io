---

layout: post
comments : true
title: '자바의 I/O'
subtitle: 'Input, Output'
date: 2020-03-31
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 27

---

> 입출력 I/O(Input / Output)

<br>

|              | Computer |               |
| :----------: | :------: | :-----------: |
| Input -----> | Program  | <----- Output |
|              | Process  |               |

- 프로그램이 입력장치(Input Device), 출력장치(Output Device)와 데이터를 송 수신하는 것, 통신 하는 것.



<br>



스트림, Stream

- 통로, 흐름
- 입출력 장치와 프로그램 사이에서 데이터를 통신(교환)할 수 있도록 제공되는 통로
- 논리적인, Sw적인 장치
- 단방향이다.
- FIFO(First In First Out) 구조로 만들어져있다.
- Byte 단위로 데이터 통신을 한다.
- 대표적인 스트림
  - System.in - 표준 입력 스트림(키보드), Standard Input, STDIN
  - System.out - 표준 출력 스트림(모니터), Standard Output, STDOUT
  - System.err - 표준 에러 스트림(모니터), Standard Error, STDERR
  - 버퍼를 가지고 있다
    - 버퍼, Buffer - 스트림안에 포함되어있는 임시 저장소, IO장치와 프로그램 간 처리속도 차이를 줄이기 위해 사용된다.

<br>

스트림의 종류

1. 입출력으로 구분
   1. 입력 스트림
   2. 출력 스트림
2. 연결 대상을 기준으로 구분
   1. 1차 스트림 : 입출력 장치와 직접 연결되는 스트림
   2. 2차 스트림 : 1차 스트림과 연결되어 보조하는 스트림
3. 전송 데이터의 형태에 따른 구분
   1. 바이트 스트림 : 바이트(1B) 단위로 통신
   2. 문자 스트림 : 문자(Char, 2B) 단위로 통신
4. 기능에 따른 분류
   1. 보조 스트림 : 직접적인 입출력 기능은 없지만 다른 스트림들의 기능 향상 목적으로 사용한다.



<br>

> InputStream의 read 메소드

<br>

- public abstract int read() throws IOException
  - 입력스트림으로부터 1Byte를 읽어들인다.
  - 읽어들인 데이터의 ASCII CODE를 int형으로 반환한다. (0 ~ 255)
  - 입력스트림에서 End Of Stream을 만나면 -1을 반환한다.
    - EOF(End Of File, End Of Stream)
    - 스트림의 끝(중단 지점), 파일의 끝

<br>

## 이걸 많이 쓴다 ↓↓

- public int read(byte[] b) throws IOException
  - 입력스트림에서 최대 b배열의 길이만큼 읽어들인다.
  - 읽어들인 데이터는 b배열의 0번째 인덱스부터 기록한다.
  - 읽어들인 데이터의 길이는 int형으로 반환한다.
  - 읽어들일 데이터가 없는 경우(EOF)엔 -1을 반환한다.

<br>

- public int read(byte[], int offset, int len) throws IOException
  - 입력 스트림에서 최대 len 만큼 읽어들인다.
  - 읽어들인 데이터를 b배열의 offset 인덱스부터 기록한다.
  - 읽어들일 데이터가 없으면(EOF) -1을 반환한다.
  - read(buf)
  - read(buf, 0, buf.length)
    - 위의 두 코드는 똑같다.

<br>

<br>

> OutputStream 의 Write() 메소드

<br>

- public abstract void write(int b) throws IOException
  - 출력 스트림으로 아스키코드 b에 해당하는 문자를 출력한다.
- public void write(byte[] b) throws IOException
  - 출력스트림으로 b 배열의 모든 문자를 출력한다.
  - b 배열에는 ASCII Code 값을 문자로 변환하여 출력한다.
  - b.length 만큼 출력, 모두 다 출력한다.
    - '\0' 도 빈칸으로 인식하여 출력한다. -> 문제를 야기할 수 있다.

## 이걸 많이 쓴다 ↓↓

- public void write(byte[] b, int offset, int len) throws IOException
  - 출력스트림으로 b배열의 off인덱스부터 len만큼 출력한다.




<br><br>