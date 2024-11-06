---
layout: page
permalink: /projects/mamba
title: Mamba-based Approximate Conformance Checking Method
description: >
  Event logs can be a promising source for discovering knowledge on 
  organizational structures and empowering workforce analytics. Novel process 
  mining methods unlock this opportunity.
nav: false
importance: 11
is_index: true
category: research
---

Today's process mining techniques have empowered numerous modern
organizations to use process execution data --- available from many
contemporary enterprise information systems as event logs --- for
diagnosing and improving their business processes from multiple
perspectives and on a continuing basis.
Human resources contribute an area less explored in process mining, but
are recognized as an impactful factor to business process improvement.

My research looks into the human resource perspective of process mining
and centers around organizational model mining from event logs.
We develop models, methods, and software tools to extract insights into
human resource groupings and behavior relevant to business process
execution.
In doing so, we aim to support organizations to make guided decisions on
staff deployment and organization design.
Our research is built within *OrdinoR*, a
framework for organizational model mining, as illustrated below.

<div class="w-75 mx-auto d-block">
<figure class="figure">
  <img src="{{ '/assets/img/research-omm/framework.svg' | relative_url }}"
  class="figure-img img-fluid rounded" 
  alt="Organizational model mining framework">
  <figcaption class="figure-caption text-center">
    Figure 1: OrdinoR ("organize resources"), our framework for organizational model mining from event logs
  </figcaption>
</figure>
</div>

What underpins this framework is our notion of organizational model that
captures human resources, their groups, and the connection between the
groupings and process execution.
With this novel notion, OrdinoR lays the foundation of many exciting
topics being researched --- for example, how can we use organizational models 
discovered from event logs to analyze the behavior of resources groups working 
in processes?

Besides the theoretical part of research, we are also developing an
open-source Python toolkit that implements OrdinoR and the relevant methods and 
techniques. Keep an eye on us if you find this topic interesting --- the party 
has started 🥳!

<!--
<nav>
  <div class="nav nav-tabs nav-justified mb-3" role="tablist">
    <a class="nav-item nav-link active" id="tab-discovery" data-toggle="tab" href="#tabc-discovery" role="tab" aria-controls="tabc-discovery" aria-selected="true">
      Model Discovery
    </a>
    <a class="nav-item nav-link" id="tab-conformance" data-toggle="tab" href="#tabc-conformance" role="tab" aria-controls="tabc-conformance" aria-selected="false">
      Conformance Checking
    </a>
    <a class="nav-item nav-link" id="tab-analysis" data-toggle="tab" href="#tabc-analysis" role="tab" aria-controls="tabc-analysis" aria-selected="false">
      Model Analysis
    </a>
    <a class="nav-item nav-link" id="tab-enhancement" data-toggle="tab" href="#tabc-enhancement" role="tab" aria-controls="tabc-enhancement" aria-selected="false">
      Model Enhancement
    </a>
  </div>
</nav>

<div class="tab-content">
  <div class="tab-pane fade show active" id="tabc-discovery" role="tabpanel" aria-labelledby="tab-discovery">
    TODO: Gif of discovery
  </div>
  <div class="tab-pane fade" id="tabc-conformance" role="tabpanel" aria-labelledby="tab-conformance">
    TODO: Gif of conformance
  </div>
  <div class="tab-pane fade" id="tabc-analysis" role="tabpanel" aria-labelledby="tab-analysis">
    TODO: Gif of analysis
  </div>
  <div class="tab-pane fade" id="tabc-enhancement" role="tabpanel" aria-labelledby="tab-enhancement">
    TODO: Gif of enhancement
  </div>
</div>
-->

#### Further Reading

- [Our paper presenting the OrdinoR framework][frameworkpaper]
- [Workforce analytics &times; Process mining: Group-oriented workforce
  analytics (appeared on BPM'21)][forestpaper]
- [OrdinoR: A Python toolkit for organizational model mining from event logs][rtdwebsite]
  
[rtdwebsite]: https://royjy.me/to/ordinor
[frameworkpaper]: https://ordinor.readthedocs.io/en/latest/citing.html
[forestpaper]: /projects/omm/forest
