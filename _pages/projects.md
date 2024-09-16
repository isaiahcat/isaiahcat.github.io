---
title: Projects
permalink: /projects/
---

<div class="card-container">
  {% assign sorted_projects = site.projects | sort: 'start_date' | reverse %}
  {% assign featured_projects = sorted_projects | where: 'featured', true %}
  {% assign non_featured_projects = sorted_projects | where: 'featured', false %}
  {% assign all_projects = featured_projects | concat: non_featured_projects %}
  {% for project in all_projects %}
  <a href="{{ site.baseurl }}/projects/{{ project.slug }}" class="card-link">
    <div class="card">
      <div class="card-content">
		<h4 class="card-title">{{ project.title }}</h4>
        <div class="card-description">{{ project.description }}</div>
  		  <div class="card-duration">
            {% assign start_date = project.start_date | date: "%B %Y" %}
            {% assign end_date = project.end_date | date: "%B %Y" %}

            {% if project.end_date == nil or project.end_date == "Present" %}
              <p>{{ start_date }} - Present</p>
            {% elsif project.start_date == project.end_date %}
              <p>{{ start_date }}</p>
            {% else %}
              <p>{{ start_date }} - {{ end_date }}</p>
            {% endif %}
          </div>
      </div>
      <div class="card-image">
        <img src="{{ site.url }}{{ site.baseurl }}{{ project.thumbnail }}" alt="{{ project.title }}">
      </div>
    </div>
  </a>
  {% endfor %}
</div>
