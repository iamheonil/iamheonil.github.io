---

layout: page
title: 'Study'
main: true

---

{% assign sorted = site.pages | sort: 'order' | reverse %} 

{% for page in sorted %} 

{% if page.study == true %} 

{% include post-list.html %} 

{% endif %} {% endfor %}
