---
title: Projects
permalink: /projects/
---

{% assign all_tags = "" | split: "" %}
{% assign all_categories = "" | split: "" %}

{% for project in site.projects %}
  {% assign all_tags = all_tags | concat: project.tags %}
  {% assign all_categories = all_categories | concat: project.categories %}
{% endfor %}

{% assign all_tags = all_tags | uniq | sort %}
{% assign all_categories = all_categories | uniq | sort %}

<p class="project_taxonomy">
  <!-- Tags Section -->
  <strong>
    <i class="fas fa-fw fa-tags" aria-hidden="true"></i> 
    {{ site.data.ui-text[site.locale].tags_label | default: "Tags:" }}
  </strong>
  <span itemprop="keywords">
    {% for tag_word in all_tags %}
      <a href="{{ tag_word | slugify | prepend: site.tag_archive.path | relative_url }}" class="project__taxonomy-item p-category" rel="tag">
        {{ tag_word }}
      </a>
    {% endfor %}
  </span>
  
  <!-- Categories Section -->
  <br>
  <strong>
    <i class="fas fa-fw fa-folder-open" aria-hidden="true"></i> 
    {{ site.data.ui-text[site.locale].categories_label | default: "Categories:" }}
  </strong>
  <span itemprop="keywords">
    {% for category_word in all_categories %}
      <a href="{{ category_word | slugify | prepend: site.category_archive.path | relative_url }}" class="project__taxonomy-item p-category" rel="tag">
        {{ category_word }}
      </a>
    {% endfor %}
  </span>
</p>


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
          {% if project.featured %}
            <span class="featured-icon" aria-label="Featured project">⭐</span>
          {% endif %}
      </div>
      <div class="card-image">
        <img src="{{ site.url }}{{ site.baseurl }}{{ project.thumbnail }}" alt="{{ project.title }}">
      </div>
    </div>
  </a>
  {% endfor %}
</div>
