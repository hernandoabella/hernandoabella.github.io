---
layout: page
title: Categories
permalink: /categories/
---

{% assign categories = site.categories | sort %}

{% for category in categories %}
## {{ category[0] }}

<ul>
  {% for post in category[1] %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <small>— {{ post.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>
{% endfor %}
