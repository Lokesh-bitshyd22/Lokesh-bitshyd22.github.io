---
layout: default
title: Writing
permalink: /blog/
---

<section class="page-header">
  <h1>Writing</h1>
</section>

<div class="blog-list">
  {% for post in site.posts %}
  <div class="post-item">
    <span class="post-date">{{ post.date | date: "%b %d, %Y" }}</span>
    <div>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      {% if post.excerpt %}
        <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 140 }}</p>
      {% endif %}
    </div>
  </div>
  {% else %}
  <p style="color: var(--gray-mid); font-style: italic; padding: 1.5rem 0;">
    No posts yet. First one coming soon.
  </p>
  {% endfor %}
</div>
