---
layout: default
title: Blog
---

<section class="blog-index container">
  <h1>Blog</h1>

  <ul class="post-list" role="list">
    {% for post in site.posts %}
      <li class="post-card">
        <h2 class="post-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h2>

        <p class="post-date">{{ post.date | date: "%B %-d, %Y" }}</p>

        {% capture snippet %}{{ post.excerpt | markdownify | strip_html }}{% endcapture %}
        <p class="post-excerpt">{{ snippet | truncate: 220 }}</p>

        <a class="btn-read" href="{{ post.url | relative_url }}">Read →</a>
      </li>
    {% endfor %}
  </ul>
</section>
