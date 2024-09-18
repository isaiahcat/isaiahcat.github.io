---
layout: archive
permalink: /categories/
title: "Projects by Category"
author_profile: true
toc: true
toc_sticky: true
---

{% include group-by-array collection=site.projects field="categories" %}

{% for category in group_names %}
  {% assign projects = group_items[forloop.index0] %}
  <h2 id="{{ category | slugify }}" class="archive__subtitle">{{ category }}</h2>
  {% include project-card-list.html %}
{% endfor %}
