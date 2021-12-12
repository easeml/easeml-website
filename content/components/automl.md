---
layout: list
title: AutoML
aliases: [/automl]
summary: If ease.ml/snoopy said “Yes” and we can finally fire up our ML training process! Given a dataset, ease.ml contains an AutoML component that outputs a ML model without any user intervention. There are three aspects of ease.ml/AutoML that makes it special.
thumbnail: images/easeml-component-generic.png
weight: 5
sections:
    - partial: content
    - title: Publications
      partial: list
      content:
        data: publications
        where:
          key: tag
          operator: eq
          match: automl
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

The first aspect is that it is holistic — we aim at fully automate the end-​to-end process of building ML applications, from feature engineering, model selection, architecture search, hyper-​parameter tuning, and post-​processing. Our system is built upon many seminal work for each of these sub-​process, while also contains our own techniques and algorithms.

The second aspect is that it is multi-​tenant and scalable — different from many existing ML platforms in which users are isolated, the view of ease.ml/AutoML is that AutoML is an endless process: whenever a new model architecture has been published by researcher, all users' application should be reran! This view introduced a scalability problem and ease.ml/AutoML tries to handle this process by having multiple users sharing multiple devices. Those users who have the highest potential to better accuracies should occupy proportionally more devices. This opens up an interesting research problem about resource sharing and allocations for AutoML workloads, and we develop an interesting principled algorithm for this problem.

The third aspect is rooted in our belief that many future ML workloads can be solved by simply applying a transfer learning-​based approach. Together with the increasing availability of pre-​trained ML models (via repositories such as TensorFlow Hub and Pytorch Hub), this aspect becomes increasingly promising, while how to efficiently manage such large pools of pre-​trained models also becomes an emerging problem.

**Input:** (1) Augmented, machine readable, dataset;

**Output:** An endless stream of models trained by the AutoML system.
