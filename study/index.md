---

layout: default
title: 'Study'
description: '자바 공부를 하면서'
main: true

---

{% assign sorted = site.pages | sort: 'order' | reverse %} 

{% for page in sorted %} 

{% if page.study == true %} 

{% include post-list.html %} 

{% endif %} {% endfor %}
