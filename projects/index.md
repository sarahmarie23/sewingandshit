---
layout: default
title: Projects
body_class: projects-page
permalink: /projects/
---

<section class="container">
  <h1>Projects</h1>

  <h2>Current</h2>
  <ul class="post-list">
    {% assign current = site.projects | where: "status", "current" %}
    {% for p in current %}
      <li class="post-card">
        <h3 class="post-title"><a href="{{ p.url | relative_url }}">{{ p.title }}</a></h3>
        {% if p.summary %}<p class="post-excerpt">{{ p.summary }}</p>{% endif %}
        <a class="btn-read" href="{{ p.url | relative_url }}">View build →</a>
      </li>
    {% endfor %}
    {% if current.size == 0 %}<p>No active build right now.</p>{% endif %}
  </ul>

  <h2 style="margin-top:2rem">Completed</h2>
  <ul class="post-list">
    {% assign completed = site.projects | where: "status", "completed" %}
    {% for p in completed %}
      <li class="post-card">
        <h3 class="post-title"><a href="{{ p.url | relative_url }}">{{ p.title }}</a></h3>
        {% if p.summary %}<p class="post-excerpt">{{ p.summary }}</p>{% endif %}
        <a class="btn-read" href="{{ p.url | relative_url }}">View details →</a>
      </li>
    {% endfor %}
  </ul>
</section>
