---
layout: page
permalink: /projects/omm
title: Organizational Model Mining
description: >
  Event logs can be a promising source for discovering knowledge on 
  organizational structures and empowering workforce analytics. Novel process 
  mining methods unlock this opportunity.
nav: false
importance: 1
is_index: true
category: development
---

In recent years, alignment-based method has become the
de facto standard for conformance checking in computing con-
formance diagnostics, as it always returns the most accurate
deviations, known as optimal-alignment. However, as the com-
plexity of the log and model increases, the runtime complexity
of optimal alignment computation grows exponentially, leading
to extremely long computation times—sometimes even taking
several weeks. This makes them impractical for real-world ap-
plications. To tackle the problems, various approximation strategies
have been proposed. Notably, model behaviour sampling method provides 
an angle for approximate conformance checking, that is, selecting partial 
model traces to substitute process model.

My research looks into an enhanced model behaviour sampling method to 
select more representative subsets and get more accuracy approximate values.
We apply hierarchical clustering to the event log with a new proposed 
distance criterion. Then, we propose two in-cluster methods to select 
typical traces from each cluster. Finally, we extend existing cost lower 
bound algorithm to achieve more accurate approximation results.

Our framework for proposed methods, as illustrated below.

<div class="w-75 mx-auto d-block">
<figure class="figure">
  <img src="{{ '/assets/img/research-hierarchical/framework-hierarchical.svg' | relative_url }}"
  class="figure-img img-fluid rounded" 
  alt="Proposed framework">
  <figcaption class="figure-caption text-center">
    Figure 1: Our framework for proposed approximate conformance checking method
  </figcaption>
</figure>
</div>

With this novel notion, our method lays the foundation of many exciting
futures being researched --- for example, can we use more advanced hierarchical
algorithm to obtain results? Keep an eye on us if you find this method interesting 
and practical --- the party has started 🥳!

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
