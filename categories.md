---
layout: page
title: Categories
permalink: /categories/
---

{% assign categories = site.categories | sort %}

<div class="category-nav" style="margin-bottom: 40px; padding: 20px; background: #222; border-radius: 8px;">
  <p style="margin-top: 0; font-weight: bold; color: #f0f0f0;">Jump to:</p>
  {% for category in categories %}
    <a href="#{{ category[0] | slugify }}" style="margin-right: 15px; text-decoration: none; border-bottom: 1px dashed;">
      {{ category[0] | capitalize }} ({{ category[1].size }})
    </a>
  {% endfor %}
</div>

<hr style="border: 0; border-top: 1px solid #333; margin: 40px 0;">

{% for category in categories %}
  <div id="{{ category[0] | slugify }}" class="category-section" style="margin-bottom: 50px;">
    <h2 style="border-left: 4px solid #35e87c; padding-left: 15px; color: #35e87c;">
      {{ category[0] | capitalize }}
    </h2>
    
    <ul style="list-style: none; padding-left: 0;">
      {% for post in category[1] %}
        <li style="margin-bottom: 12px; display: flex; justify-content: space-between; align-items: baseline; border-bottom: 1px solid #222; padding-bottom: 8px;">
          <a href="{{ post.url | relative_url }}" style="font-weight: 500; font-size: 1.1em;">
            {{ post.title }}
          </a>
          <time style="color: #888; font-family: monospace; font-size: 0.9em;">
            {{ post.date | date: "%Y-%m-%d" }}
          </time>
        </li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}