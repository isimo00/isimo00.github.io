---
layout: page
title: Projects
permalink: /projects/
description: Some stuff I made that is worth sharing! (Not for diploma obtention)
nav: true
nav_order: 3
display_categories: [tools, templates]
horizontal: false
---

### Under supervision
Some notable projects my code has contributed to:
- `soupy` library for Stochastic Optimization under high-dimensional Uncertainty in Python, developed by the Scientific Computing and Uncertainty Quantification @ GeorgiaTech. [Github repo](https://github.com/hippylib/soupy) (Python)
- _Study on the union of hyperbolic graphs_. Private repository, under [Prof. Maria Serna](https://www.cs.upc.edu/~mjserna/)'s supervision.
- `biggr` library, developed by BEEGroup @ CIMNE. [Github repo](https://github.com/biggproject/biggr) (R)
- `beemeteo` library, developed by BEEGroup @ CIMNE. [Github repo](https://github.com/BeeGroup-cimne/beemeteo) (Python)
- _Wall modelling using a MLP neural network_ project for turbulent flow boundary layer modeling. Private repository, under [Prof. Bernat Font](https://b-fg.github.io/)'s supervision @ BSC-CSN. (Python)
This was an extracurricular extension of my [aerospace engineering bachelor's thesis](https://upcommons.upc.edu/handle/2117/372288) (for diploma obtention).
- Various $\LaTeX$ workflows for automation and templates. Private repository, under [Prof. Rafael Weyler](https://futur.upc.edu/RafaelWeylerPerez?locale=en) and Prof. Josep Piñol's supervision @ UPC, Material Science department.

### Self-initiated
Some cool self-directed projects I have designed and developed.

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
