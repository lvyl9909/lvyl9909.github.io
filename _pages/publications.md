---
layout: page
permalink: /publications/
title: Publications
description: 
years: []
nav: true
---

<p class="text-secondary">
    Hoping both my publication list and hair keep growing
</p>

### Journal Articles
<div class="publications" id="publications-journal">
{% bibliography -f publications -q @article %}
</div>

### Conference Articles
<div class="publications" id="publications-conference">
{% bibliography -f publications -q @inproceedings %}
</div>

### Patents
<div class="publications" id="publications-patent">
{% bibliography -f publications -q @misc %}
</div>