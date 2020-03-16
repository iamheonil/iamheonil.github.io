---

layout: post
comments : true
title: '스트림의 종류'
subtitle:
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 31

---

> 스트림의 종류

<br>

|    바이트 스트림     |  문자 스트림   |
| :------------------: | :------------: |
|     InputStream      |     Reader     |
|     OutputStream     |     Writer     |
|                      |                |
|   FileInputStream    |   FileReader   |
|   FileOutPutStream   |   FileWriter   |
|                      |                |
| BufferedInputStream  | BufferedReader |
| BufferedOutputStream | BufferedWriter |

<br>

바이트스트림만 존재

- DataInputStream
- DataOutputStream
- 
- ObjectInputStream
- ObjectOutputStream

<br>

바이트 스트림을  문자 스트림으로 변환 해주는 클래스

- InputStreamReader
- OutputStreamWriter

<br>

문자 출력 스트림

- PrintWriter
<br><br>