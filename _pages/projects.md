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
      <a href="{{ site.tag_archive.path | relative_url }}#{{ tag_word | slugify }}" class="project__taxonomy-item p-category" rel="tag">
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
      <a href="{{ site.category_archive.path | relative_url }}#{{ category_word | slugify }}" class="project__taxonomy-item p-category" rel="tag">
        {{ category_word }}
      </a>
    {% endfor %}
  </span>
</p>


{% assign projects = site.projects %}
{% include project-card-list.html %}
