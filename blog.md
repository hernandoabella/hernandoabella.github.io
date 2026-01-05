---
layout: page
title: Writing & Insights
permalink: /blog/
---

<div class="blog-feed">
  {% if paginator.posts.size > 0 %}
    {% for post in paginator.posts %}
    <article class="post-card" style="margin-bottom: 40px; padding-bottom: 20px; border-bottom: 1px solid #333;">
      <header class="post-header">
        <h2 style="margin-bottom: 10px;">
          <a class="post-link" href="{{ post.url | relative_url }}" style="color: #35e87c; text-decoration: none;">
            {{ post.title | escape }}
          </a>
        </h2>
        
        <div class="post-meta" style="font-family: monospace; color: #888; margin-bottom: 15px; font-size: 0.9em;">
          <span class="date">📅 {{ post.date | date: "%b %d, %Y" }}</span>
          {% if post.categories.size > 0 %}
            <span class="divider"> | </span>
            <span class="categories">📂 {{ post.categories | join: ", " | upcase }}</span>
          {% endif %}
          <span class="divider"> | </span>
          <span class="read-time">⏱️ {% assign words = post.content | number_of_words %}{% if words < 360 %}1 min{% else %}{{ words | divided_by: 180 }} min{% endif %} read</span>
        </div>
      </header>

      <div class="post-excerpt" style="color: #ccc; line-height: 1.6;">
        {{ post.excerpt | strip_html | truncatewords: 50 }}
      </div>

      <a href="{{ post.url | relative_url }}" style="display: inline-block; margin-top: 15px; font-weight: bold; font-size: 0.9em; text-transform: uppercase; letter-spacing: 1px; color: #35e87c;">
        Read Full Post →
      </a>
    </article>
    {% endfor %}

    {% if paginator.total_pages > 1 %}
    <nav class="pagination" style="text-align: center; margin-top: 50px; font-family: monospace;">
      {% if paginator.previous_page %}
        <a href="{{ paginator.previous_page_path | relative_url }}" style="padding: 10px; border: 1px solid #35e87c; color: #35e87c;">&laquo; Prev</a>
      {% endif %}

      <span class="page-number" style="margin: 0 15px;">Page {{ paginator.page }} of {{ paginator.total_pages }}</span>

      {% if paginator.next_page %}
        <a href="{{ paginator.next_page_path | relative_url }}" style="padding: 10px; border: 1px solid #35e87c; color: #35e87c;">Next &raquo;</a>
      {% endif %}
    </nav>
    {% endif %}

  {% else %}
    <div style="text-align: center; padding: 50px;">
      <p style="font-size: 1.5em; color: #888;">No posts yet. The lab is currently quiet. 👀</p>
    </div>
  {% endif %}
</div>