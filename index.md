---
title: About
---

Hi! I'm Isaiah Butler, a **Technical Project Manager** with a **Master's in Computer Science** and over **eight years** of experience in software development, including **three years** of focused project management. 

In my technical roles, I have frequently taken on project management responsibilities, including **managing timelines and sprints**, **collaborating with stakeholders**, and **leading cross-functional teams** to ensure project success. 

I specialize in **Agile methodologies** and I'm currently pursuing my **PMP certification** to further solidify my project management knowledge and stay up-to-date with evolving industry practices.

I’m passionate about **solving problems**, **leading teams**, and helping businesses grow through **technology-driven solutions**.

---

# Skills

&emsp;&emsp;**Project Management**&emsp;&emsp;&emsp;3+ years    
&emsp;&emsp;**Software Development**&emsp;&emsp;8+ years    

### Overview

| --- |---|
| **Project Management** | Agile, Scrum, Waterfall, Team Leadership, Problem Solving, Stakeholder Collaboration |
| **Software Development** | C, C++, C#, Java, Python | 
| **Mobile Development** | Android, Java, Kotlin, iOS, Objective-C | 
| **Frontend Development** | Bootstrap, HTML, CSS, JavaScript |
| **Backend Development** | PHP (Laravel), MySQL |
| **Artificial Intelligence & Machine Learning** | Tensorflow, Keras, PyTorch |
| **Version Control** | Git, GitHub, GitLab, Subversion (SVN) |
| **Cloud & Integration Tools** | Amazon S3, Firebase, Fabric, Payments, Biometrics |
| **Testing & Monitoring** | Crashlytics, Jira, Confluence, Trello, Basecamp |


### See Projects by Tag or Category

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
