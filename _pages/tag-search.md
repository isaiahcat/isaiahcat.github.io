---
layout: archive
permalink: /tags/
title: "Projects by Tag"
author_profile: true
---

{% include projects-navigation.html %}
{% include project-tags.html %}
{% include group-by-array collection=site.projects field="tags" %}

{% for tag in group_names %}
  {% assign projects = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% include project-card-list.html %}
{% endfor %}