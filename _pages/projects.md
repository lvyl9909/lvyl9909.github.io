---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
---

<div class="toggle-container">
  <label class="toggle-switch">
    <input type="checkbox" id="toggleSwitch" class="toggle-switch-checkbox">
    <span class="toggle-switch-label">
      <span class="toggle-switch-inner"></span>
      <span class="toggle-switch-switch"></span>
    </span>
  </label>
</div>


<div class="projects grid" id="projectsContainer">

  {% assign sorted_projects = site.projects | sort: "importance" %}
  {% for project in sorted_projects %}
  {% if project.is_index %}
  <div class="grid-item {% if project.category %}{{ project.category }}{% endif %}">
    {% if project.redirect %}
    <a href="{{ project.redirect }}" target="_blank">
    {% else %}
    <a href="{{ project.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if project.img %}
        <img src="{{ project.img | relative_url }}" alt="project thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title">{{ project.title }}</h2>
          <p class="card-text text-secondary">{{ project.description }}</p>
          <div class="row ml-1 mr-1 p-0">
            {% if project.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ project.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if project.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ project.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
  {% endif %}
  {% endfor %}

</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const toggleSwitch = document.getElementById("toggleSwitch");
    const researchItems = document.querySelectorAll(".grid-item.research");
    const developmentItems = document.querySelectorAll(".grid-item.development");

    // 页面加载时默认显示 research 项目，隐藏 development 项目
    researchItems.forEach(item => item.style.display = "block");
    developmentItems.forEach(item => item.style.display = "none");

    toggleSwitch.addEventListener("change", function() {
      if (toggleSwitch.checked) {
        // 显示 development 项目并隐藏 research 项目
        researchItems.forEach(item => item.style.display = "none");
        developmentItems.forEach(item => item.style.display = "block");
      } else {
        // 显示 research 项目并隐藏 development 项目
        researchItems.forEach(item => item.style.display = "block");
        developmentItems.forEach(item => item.style.display = "none");
      }
    });
  });
</script>



