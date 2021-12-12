---
layout: list
title: Snoopy
aliases: [/snoopy]
summary: |
    Machine learning is no panacea — if your data are 20% wrong but you are hoping for 90% accuracy to make a
    profit out of your model, it is highly likely that it is doomed to fail. In our experience, we were surprised by
    how often an end user has a staggering mismatch between the quality of their data an the expectation of the accuracy
    that an ML model can achieve.
thumbnail: images/easeml-component-generic.png
weight: 2
sections:
    - partial: content
    - title: Publications
      partial: list
      content:
        data: publications
        where:
          key: tag
          match: snoopy
          operator: eq
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

Our view to this problem is to provide the functionality of an automatic feasibility study to the end user — given a dataset and an target accuracy, we provide the user a best-​effort “belief” on whether it is possible or not, before the users fire up expensive ML processes, just like how many real-​world ML consultants are dealing with their customers. Of course, such a “belief” will never be perfect, but we hope that providing such a signal will help the end users to better calibrate their expectations.

From the technical perspective, what we are estimating is the Bayes error, a fundamental ML concept. In ease.ml/snoopy, we designed a simple, yet effective, Bayes error estimator enabled by the recent advancement of representation learning and the increasing availability of pre-​trained feature embeddings.

**Input:** (1) Augmented, machine readable, dataset; (2) Target accuracy.

**Output:** {Feasible, Not Feasible} as the belief of the system.

**Action:** (1) If "Feasible", proceeds to ease.ml/AutoML; (2) If "Not Feasible", proceeds to CPClean.
