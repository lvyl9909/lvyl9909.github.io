---
layout: page
permalink: /projects/mamba
title: Mamba-based Approximate Conformance Checking Method
description: >
  What sparks might fly when the latest 2024 advancements in neural networks are applied to conformance checking?
nav: false
importance: 2
is_index: true
category: research
---

The use of neural networks in process mining is not new and has been widely 
applied in areas such as predictive process monitoring. However, the application
of neural networks in conformance checking has been underexplored. In this study,
we propose an approximate conformance checking method MACC, which based on Mamba classifiers 
and Temporal Convolutional Networks (TCNs) that significantly improves the efficiency 
of fitness computation. While maintaining fitness values that are almost identical 
to the actual values, our approach substantially reduces computation time.

The proposed MACC method achieves approximate conformance checking through a two-stage training process:

<div class="w-75 mx-auto d-block">
<figure class="figure">
  <img src="{{ '/assets/img/research-mamba/mamba-framework.svg' | relative_url }}"
  class="figure-img img-fluid rounded" 
  alt="Proposed framework">
  <figcaption class="figure-caption text-center">
    Figure 1: Our framework for proposed method MACC
  </figcaption>
</figure>
</div>

##### Stage 1: Classifier Training

- **Log Mutation**: The event log is mutated to generate both correct (fitness = 1) and incorrect (fitness < 1) traces.
- **Fitness Computation**: The pm4py library is used to compute the fitness values of each trace via alignment techniques. Traces with a fitness value of less than 1 are labeled as 0, while others are labeled as 1.
- **Split-Bucket Strategy**: Based on the length distribution of the traces, the log is divided into three buckets using a normal distribution-based binning strategy. Each bucket is used to train a dedicated Mamba classifier.

##### Stage 2: Regressor Training

- **Feature Embedding**: The embeddings produced by the classifier in Stage 1 are combined with the original trace embeddings.
- **Training the Regressor**: These enhanced embeddings are used alongside the original fitness values to train a regressor, improving the accuracy of fitness predictions.

Our classifier leverages a Mamba-based architecture designed for efficient feature extraction. It incorporates layer normalization, row attention (RA) for capturing sequence correlations, and Temporal Convolutional Networks (TCN) for fine-grained temporal feature mining. The structure of our proposed classifier as follows:
<div class="w-35 mx-auto d-block text-center">
<figure class="figure">
  <img src="{{ '/assets/img/research-mamba/mamba-classifier.png' | relative_url }}"
  class="figure-img img-fluid rounded" 
  alt="Proposed framework"
  style="height: 500px; object-fit: contain;">
  <figcaption class="figure-caption text-center">
    Figure 1: The structure of proposed classifier in MACC
  </figcaption>
</figure>
</div>