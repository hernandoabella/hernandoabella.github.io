---
layout: page
title: Tags
permalink: /tags/
---

<div class="tag-cloud" style="text-align: center; padding: 30px; background: #1a1a1a; border-radius: 12px; border: 1px solid #333; margin-bottom: 40px;">
  {% assign tags = site.tags | sort %}
  {% for tag in tags %}
    {% assign tag_name = tag[0] %}
    {% assign count = tag[1] | size %}
    
    {% if count > 10 %}
      {% assign size = "2.0em" %}
    {% elif count > 5 %}
      {% assign size = "1.5em" %}
    {% else %}
      {% assign size = "1.0em" %}
    {% endif %}

    <a href="#{{ tag_name | slugify }}" style="font-size: {{ size }}; margin: 0 10px; display: inline-block; text-decoration: none; color: #35e87c; transition: transform 0.2s;" onmouseover="this.style.transform='scale(1.1)'" onmouseout="this.style.transform='scale(1.0)'">
      {{ tag_name }}<span style="font-size: 0.5em; color: #888; vertical-align: super;">{{ count }}</span>
    </a>
  {% endfor %}
</div>

<div class="tag-sections">
  {% for tag in tags %}
    <section id="{{ tag[0] | slugify }}" style="margin-bottom: 40px; scroll-margin-top: 50px;">
      <h2 style="border-bottom: 2px solid #35e87c; display: inline-block; padding-bottom: 5px;">
        #{{ tag[0] }}
      </h2>
      
      <div class="posts-list" style="margin-top: 15px;">
        {% for post in tag[1] %}
          <div style="display: flex; align-items: baseline; margin-bottom: 8px;">
            <span style="color: #35e87c; margin-right: 10px;">&gt;</span>
            <a href="{{ post.url | relative_url }}" style="font-weight: 500;">{{ post.title }}</a>
            <span style="flex-grow: 1; border-bottom: 1px dotted #444; margin: 0 10px;"></span>
            <time style="font-family: monospace; color: #888; font-size: 0.9em;">{{ post.date | date: "%Y-%m-%d" }}</time>
          </div>
        {% endfor %}
      </div>
    </section>
  {% endfor %}
</div>