---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
nav_order: 2
---

<style>
  .grid-item { display: none; }
</style>
<noscript>
  <style>
    .grid-item { display: block; }
  </style>
</noscript>

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

<div id="paginationContainer" class="mt-3 text-center"></div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const toggleSwitch = document.getElementById("toggleSwitch");
  const projectsContainer = document.getElementById("projectsContainer");
  const paginationContainer = document.getElementById("paginationContainer");
  const itemsPerPage = 3;
  let currentCategory = "research";

  function displayPage(category, pageNumber) {
    const projects = Array.from(projectsContainer.querySelectorAll(".grid-item"))
      .filter(project => project.getAttribute("data-category") === category);

    const totalPages = Math.ceil(projects.length / itemsPerPage) || 1;
    const start = (pageNumber - 1) * itemsPerPage;
    const end = start + itemsPerPage;

    Array.from(projectsContainer.querySelectorAll(".grid-item")).forEach(project => {
      project.style.display = "none";
    });

    projects.forEach((project, index) => {
      if (index >= start && index < end) {
        project.style.display = "block";
      }
    });

    renderPagination(totalPages, pageNumber, category);

    if (typeof window.$grid !== "undefined") {
      window.$grid.masonry("layout");
    }
  }

   function renderPagination(totalPages, currentPage, category) {
    paginationContainer.innerHTML = "";
    if (totalPages <= 1) return;
    for (let i = 1; i <= totalPages; i++) {
      const btn = document.createElement("button");
      btn.className = "btn btn-sm mx-1 " + (i === currentPage ? "btn-primary" : "btn-outline-secondary");
      btn.textContent = i;
      btn.addEventListener("click", () => displayPage(category, i));
      paginationContainer.appendChild(btn);
    }
  }

  toggleSwitch.addEventListener("change", function () {
    currentCategory = toggleSwitch.checked ? "development" : "research";
    displayPage(currentCategory, 1);
  });

  displayPage(currentCategory, 1);
});
</script>



