---
layout: page
title: Blog
permalink: /blog/
---

{% if site.posts.size > 0 %}
  {% for post in site.posts %}
  <article>
    <h2>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h2>

    <small>
      📅 {{ post.date | date: "%B %d, %Y" }}
    </small>

    <p>{{ post.excerpt }}</p>
  </article>
  <hr>
  {% endfor %}
{% else %}
  <p>No posts yet 👀</p>
{% endif %}
