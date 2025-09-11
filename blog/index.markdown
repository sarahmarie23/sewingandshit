---
layout: default
title: Blog
---

<h1>Blog</h1>

<ul class="post-list">
  {% for post in site.posts %}
    <li class="post-list-item">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="date">{{ post.date | date: "%B %-d, %Y" }}</p>

      {% capture snippet %}{{ post.excerpt | markdownify | strip_html }}{% endcapture %}
      <p>{{ snippet | truncate: 200 }}</p>

      <a class="read-more" href="{{ post.url | relative_url }}">Read →</a>
    </li>
  {% endfor %}
</ul>
