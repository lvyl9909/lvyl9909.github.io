---
layout: page
permalink: /projects/hierarchical
title: Enhancing Approximate Conformance Checking Accuracy with Hierarchical Clustering Model Behaviour Sampling
description: >
  Existing model sampling-based methods for approximate conformance checking lack sufficient accuracy. This study 
  proposes new hierarchical clustering approaches to improve approximation, achieving results closer to exact values.
nav: false
is_index: true
importance: 1
category: research
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

#### Further Reading

- [Our paper presenting the framework][frameworkpaper]
- [Our github repository for source code and experiment data][rtdwebsite]

[frameworkpaper]: {{ '/assets/Hierarchical_paper.pdf' | relative_url }}
[rtdwebsite]: https://github.com/lvyl9909/Approximate-Conformance-Checking-using-Hierarchical-Clustering
