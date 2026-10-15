---
layout: page
title: projects
description: Research engineering, interaction prototypes, and undergraduate projects.
permalink: /projects/
nav: true
nav_order: 3
display_categories: [research-engineering, undergraduate]
horizontal: false
---
<div class="projects">
{% for category in page.display_categories %}
  {% if category == 'research-engineering' %}
    <h2 class="category">Research Engineering</h2>
  {% elsif category == 'undergraduate' %}
    <h2 class="category">Undergraduate Projects</h2>
  {% endif %}
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
{% endfor %}
</div>
