---
layout: list
title: ModelPicker
aliases: [/modelpicker]
summary: All models that pass ease.ml/ci, in principle, can be deployed. This gives a pool of candidate models at any given time, each of which can be developed under different hypotheses (e.g., different slices of data). While real-​world data distribution keeps changing rapidly (e.g., every day), how can we pick the best model, i.e. the one that fits our latest data distribution?
thumbnail: images/easeml-component-generic.png
weight: 7
sections:
    - partial: content
    - title: Publications
      partial: list
      content:
        data: publications
        where:
          key: tag
          operator: eq
          match: modelpicker
      params:
        header:
          field: year
        grouped: true
links:
  - icon: fa-github
    href: https://github.com/easeml
    large: true
    label: Code
---

All models that pass ease.ml/ci, in principle, can be deployed. This gives a pool of candidate models at any given time, each of which can be developed under different hypotheses (e.g., different slices of data). While real-​world data distribution keeps changing rapidly (e.g., every day), how can we pick the best model, i.e. the one that fits our latest data distribution?

Our view is to enable a rapid MLOps loop: every day (hour), real-​world (unlabelled) data comes into the system, and an MLOps engineer would label these fresh data to pick the best model to use for the coming day (hour), from the pool of candidate models. The key technical challenge is to decrease the number of labels required from the MLOps engineer to control the cost of such a process.

In ease.ml/ModelPicker, we designed a novel active learning algorithm which picks the most “informative” data points for an MLOps engineer to label. With our algorithm, we can pick the best out of 102 models over ImageNet, with merely ~1K images to label!

**Input:** (1) A set of models, each of which passed ease.ml/ci; (2) a fresh unlabelled test set.

**Output:** The model with highest test accuracy.

**Action:** The user provides labels on data examples picked by ease.ml/ModelPicker. Deploy the picked model until a new fresh unlabelled test set comes.
