---
layout: page
permalink: /software/
title: software
description: Select Levy Lab software, of many others our group is working on.
nav: true
display_categories: [ongoing, complete]
horizontal: false
---

<!-- pages/software.md -->
<div class="software">
{%- if site.enable_software_categories and page.display_categories %}
  <!-- Display categorized software -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_software = site.software | where: "category", category -%}
  {%- assign sorted_software = categorized_software | sort: "importance" %}
  <!-- Generate cards for each software -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for software in sorted_software -%}
      {% include software_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for software in sorted_software -%}
      {% include software.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display software without categories -->
  {%- assign sorted_software = site.software | sort: "importance" -%}
  <!-- Generate cards for each software -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for software in sorted_software -%}
      {% include software_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for software in sorted_software -%}
      {% include software.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
