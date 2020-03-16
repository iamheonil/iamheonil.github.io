---

layout: post
comments : true
title: '직렬화'
subtitle: 'Serialization'
study: true
text: true
author: 'Kim Heonil'
tags: Java
order: 30

---

> 직렬화, Serialization

<br>

- 크기가 큰 데이터를 바이트단위로 잘게 나누어서 스트림을 통과할 수 있도록 만드는 것
- 데이터들을 순서에 맞게 바이트단위로 일렬로 나열하는 것과 비슷
- writeObject



<br>

> 역직렬화, Deserialization

<br>

- 바이트단위로 잘게 나누어져 스트림을 통과한 데이터를 원본의 형식으로 다시 합치는 것
- readObject
<br><br>