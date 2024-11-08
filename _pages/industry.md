---
layout: page
title: Industry
permalink: /industry/
description: A collection of the experiences that have shaped my career, each one 
  a chapter in my story of growth and contribution.
nav: true
nav_order: 3
horizontal: false
---

<div class="industry">
  {%- assign sorted_industries = site.industry | sort: "importance" %}
  {% if page.horizontal -%}
    <div class="container">
      <div class="row row-cols-2">
        {%- for industry in sorted_industries -%}
          {% include industry_horizontal.html industry=industry %}
        {%- endfor %}
      </div>
    </div>
  {%- else -%}
    <div class="grid">
      {%- for industry in sorted_industries -%}
        {% include industry.html industry=industry %}
      {%- endfor %}
    </div>
  {%- endif %}
</div>
