---

layout: page
title: Study
description: UI/UX Engineering 과정을 이수하며

---
<p> Hi </p>
{% assign sorted = site.pages | sort: 'order' | reverse %} {% for page in sorted %} {% if page.blog == true %} {% include post-list.html %} {% endif %} {% endfor %}
