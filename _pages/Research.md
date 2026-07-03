---
layout: page
title: Research
permalink: /research/
description: Earth Observation, data-centric AI, food security, and urban vulnerability research.
nav: true
nav_order: 2
display_categories: [research]
horizontal: false
---

<!-- _pages/Research.md -->

<section class="research-overview" markdown="1">

## Research overview

Mariana Belgiu's research develops GeoAI and data-centric machine learning methods for multi-temporal Earth Observation data. The work combines optical, radar, hyperspectral, UAV, and spatial data to support crop mapping, crop monitoring, yield forecasting, soil and crop nutrition assessment, urban vulnerability mapping, and environmental monitoring.

The group is particularly interested in transferable models, learning with limited labels, data quality, citizen-guided AI, and the connection between Earth Observation indicators and societal challenges such as food security, hidden hunger, and climate vulnerability.

<div class="expertise-tags" aria-label="Research expertise">
  <span>Remote sensing</span>
  <span>GeoAI</span>
  <span>Data-centric AI</span>
  <span>Multi-temporal imagery</span>
  <span>SAR</span>
  <span>Hyperspectral data</span>
  <span>Crop monitoring</span>
  <span>Hidden hunger</span>
  <span>Citizen-guided AI</span>
</div>

</section>

<section class="project-highlights" aria-labelledby="funded-projects">
  <h2 id="funded-projects">Selected funded projects and networks</h2>

  <div class="project-highlight-grid">
    <article class="project-highlight">
      <h3>EO4Nutri</h3>
      <p>ESA-funded work using Earth Observation and spatial data to help map and predict nutrient levels in crops.</p>
      <span>2023-2025</span>
    </article>

    <article class="project-highlight">
      <h3>SPACE4ALL</h3>
      <p>NWO-funded research on climate vulnerability in slum communities in Ghana, Kenya, and Nigeria using citizen science, remote sensing, and AI.</p>
      <span>2023-2027</span>
    </article>

    <article class="project-highlight">
      <h3>ASTRAIOS</h3>
      <p>Horizon Europe project analyzing space curricula and skills gaps to strengthen training for future space and Earth Observation professionals.</p>
      <span>2023-2025</span>
    </article>

    <article class="project-highlight">
      <h3>EENSAT</h3>
      <p>Education network connecting East African universities around space science, Earth Observation, and environmental monitoring.</p>
      <span>2017-2024</span>
    </article>

    <article class="project-highlight">
      <h3>EO4all</h3>
      <p>ITC working group focused on gender equality, diversity, inclusion, student intake, and collaborative project acquisition in Earth Observation.</p>
      <span>2022-2027</span>
    </article>

    <article class="project-highlight">
      <h3>HyNutri</h3>
      <p>ESA-funded hyperspectral remote sensing project focused on soil and crop nutrient monitoring.</p>
      <span>2019-2021</span>
    </article>
  </div>
</section>

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
