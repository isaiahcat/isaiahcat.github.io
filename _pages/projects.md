---
layout: single
title: Projects
permalink: /projects/
---

<div class="card-container">
  {% for project in site.projects %}
  <a href="{{ site.baseurl }}/projects/{{ project.slug }}" class="card-link">
    <div class="card">
      <div class="card-content">
        <div class="card-title">{{ project.title }}</div>
        <div class="card-description">{{ project.description }}</div>
      </div>
      <div class="card-image">
        <img src="{{ site.baseurl }}{{ project.thumbnail }}" alt="{{ project.title }}">
      </div>
    </div>
  </a>
  {% endfor %}
</div>
