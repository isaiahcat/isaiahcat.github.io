---
layout: single
title: Projects
permalink: /projects/
---

<div class="card-container">
  {% for project in site.projects %}
  <a href="{{ project.url }}" class="card-link">
    <div class="card">
      <div class="card-image">
        <img src="{{ project.image }}" alt="{{ project.title }}">
      </div>
      <div class="card-content">
        <div class="card-title">{{ project.title }}</div>
        <div class="card-description">{{ project.description }}</div>
      </div>
    </div>
  </a>
  {% endfor %}
</div>
