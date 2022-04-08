---

layout: post
comments : true
title: 'FrontEnd JavaScript 기본 대화상자'
subtitle: 'JavaScript에서 제공하는 기본 대화상자'
date: 2020-05-07
comments: true
study: true
text: true
author: 'Kim Heonil'
tags: FrontEnd
order: 109

---

> 자바스크립트에서 제공하는 기본 대화상자

<br>

- alert
  - 확인버튼과 메세지를 출력하는 Alert 창, 주로 확인용으로 사용된다.

<br>

``` javascript
<script type="text/javascript">
        function showAlert() {
            var res = alert("Message")

            console.log(res) // 반환 값이 없다, Undefined

        }
</script>

<li>확인 버튼과 메세지를 출력하는 Alert 창</li>
        <input type="button" onclick="showAlert()" value="확인">
```

<br>

- confirm
  - 확인버튼, 취소버튼, 메세지가 들어가는 Confirm 창
    - 반환값이 Boolean 타입이다

<br>

``` javascript
<script type="text/javascript">
     function showConfirm() {
            var res = confirm('ㅎㅇ')

            console.log(res)

            if (res) {
                document.getElementsByTagName("li")[1].style.color = "blue";
            } else {
                document.getElementsByTagName("li")[1].style.color = "red";
            }
        }
</script>

        <li>확인, 취소 두가지와 메세지가 들어가는 Confirm 창<br>
            (반환값이 Boolean 타입이다. True(확인) Or False(취소))</li>
        <input type="button" onclick="showConfirm()" value="확인">
```

<br>

- prompt
  - 확인버튼, 취소버튼, 메세지, 텍스트필드가 들어가는 Prompt 창

<br>

``` javascript
<script type="text/javascript">
   function showPrompt() {
            var res = prompt('아래에 값을 입력해주세요.')

            console.log(res)
            
            if (res == "싫어") {
                alert('싫다고?')
            } else if (res == "좋아") {
                alert('좋다고?')
            } else {
                alert('어떡하라구 ㅠㅠ')
                showPrompt()
            }
        }
</script>

<li>확인, 취소 두가지와 텍스트필드, 메세지가 들어가는 Prompt 창</li>
        <input type="button" onclick="showPrompt()" value="확인">
```

<br><br>