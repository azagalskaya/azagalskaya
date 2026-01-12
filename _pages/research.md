---
layout: research
title: Research
permalink: /research/
subtitle:
description: Electrochemical energy conversion and storage are crucial for the advancement of future renewable energy technologies. Enhancing energy efficiency requires optimizing the performance and durability of electrochemical systems, especially at the interfaces where electrocatalytic reactions take place. However, predicting and controlling these interfaces remain a grand challenge due to their structural and chemical complexities, especially under working conditions. Through the integration of cutting-edge modeling techniques, our research targets the development of advanced models to capture realistic behavior of the electrochemical interfaces and bridge the gap between theory and experimental observations for rational design of electrocatalytic systems. In a broader context, our work contributes to sustainability goals, including zero hunger, clean energy, and climate action, with the goal of accelerating the transition from today's environmental challenges to a more sustainable future.
nav: true
nav_order: 1
display_categories: [Current] # [work, fun]
horizontal: false

profile:
  image: research-home.webp
  width: 340px
  image_circular: true
---

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
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
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
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
