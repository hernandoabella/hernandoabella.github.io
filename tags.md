---
layout: page
title: Tags
permalink: /tags/
---

{% assign tags = site.tags | sort %}

{% for tag in tags %}
## {{ tag[0] }}

<ul>
  {% for post in tag[1] %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <small>— {{ post.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>
{% endfor %}
