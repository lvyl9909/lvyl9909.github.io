---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
nav_order: 2
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
  <div class="grid-item {{ project.category }}" data-category="{{ project.category }}">
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
        </div>
      </div>
    </a>
  </div>
  {% endif %}
  {% endfor %}
</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const toggleSwitch = document.getElementById("toggleSwitch");
  const projectsContainer = document.getElementById("projectsContainer");

  function filterProjects(category) {
    const projects = projectsContainer.querySelectorAll(".grid-item");
    projects.forEach(project => {
      if (project.getAttribute("data-category") === category) {
        project.style.display = "block"; // 显示符合条件的项目
      } else {
        project.style.display = "none"; // 完全隐藏不符合条件的项目
      }
    });
  }

  filterProjects("research");

  toggleSwitch.addEventListener("change", function () {
    if (toggleSwitch.checked) {
      filterProjects("development");
    } else {
      filterProjects("research");
    }
  });
});
</script>



