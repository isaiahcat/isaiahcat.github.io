---
title: About
---

Hi! I'm Isaiah Butler, a **Technical Project Manager** with a **Master's in Computer Science** and over **eight years** of experience in software development, including **three years** of focused project management. 

My expertise lies in **leading cross-functional teams** to deliver high-impact software projects that meet business needs and are completed on time.

In my technical roles, I have frequently taken on project management responsibilities, from **managing timelines and sprints** to **collaborating with stakeholders** and ensuring project success. 

I specialize in **Agile methodologies** and I'm currently pursuing my **PMP certification** to further solidify my project management knowledge and stay up-to-date with evolving industry practices.

I’m passionate about solving problems, leading teams, and helping businesses grow through technology-driven solutions.

---

### Skills Overview

| **Skill**                    	| **Years of Experience** |
|-------------------------------|-------------------------|
| **Project Management**        | 3+ years                |
| **Software Development**    	| 8+ years                |
| **Android Development**          | 3+ years (Kotlin), 2+ years (Java) |
| **iOS Development (Objective-C)** | 6 months             |
| **Version Control (Git, SVN)** | 8+ years                |
| **Database Management**        | 4+ years                |
| **REST APIs & Retrofit**       | 4+ years                |

---

### Full Skillset

- **Project Management**: Agile, Scrum, Waterfall, Risk Management, Stakeholder Collaboration
- **Software Development**: Android, Kotlin, Java, iOS, Objective-C, C, C#, Python
- **Frontend Development**: Bootstrap, HTML, CSS, JavaScript
- **Backend Development**: PHP (Laravel), MySQL
- **Version Control**: Git, Subversion (SVN)
- **Cloud & Integration Tools**: Amazon S3, Firebase, Fabric, Payment SDKs, Biometrics
- **Testing & Monitoring**: Crashlytics, Jira, Confluence, Trello, Basecamp

--- 

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
