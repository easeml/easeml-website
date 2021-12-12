---
layout: list
title: DataScope
aliases: [/datascope]
summary: If data cleaning won’t increase your accuracy by too much, another potential reason of unsatisfactory ML quality is simply that you don’t have enough amount of data. If CPClean advices the user against data cleaning, she needs to acquire more data. Market is the next ease.ml component that helps the user with this.
thumbnail: images/easeml-component-generic.png
weight: 4
sections:
    - partial: content
    - title: Publications
      partial: list
      content:
        data: publications
        where:
          key: tag
          match: datascope
          operator: eq
      params:
        header:
          field: year
        grouped: true
links:
  - icon: fa-github
    href: https://github.com/easeml/datascope
    large: true
    label: Code
---

<div class="embedded-element">
{{< youtube ZwGToAb0MT8 >}}
</div>

We focus on a specific case of data acquisition — given a pool of data examples, how can we choose which one to include (and to label if they are unlabelled) to maximize the accuracy of ML models? In principle, we hope to pick out those data examples that are more “valuable” to the downstream ML models.

In Market, we decide whether a data example is valuable by using the Shapley value, a well established concept in game theory, and treat the accuracy of ML models as the utility. Unfortunately, simply evaluating the Shapley value can be expensive — for generic ML models, it is exponential to the number of data examples. Fortunately, we show that, for k-​nearest neighbour classifiers, calculating the exact Shapley value can be done in nearly linear time! In Market, we use the k-​nearest neighbour classifiers as a proxy and provide the guidance for the user on which new data samples to acquire.

**Input:** (1) Augmented, machine readable, dataset; (2) A pool of potential data examples that one can acquire.

**Output:** The system’s belief on the value of each potential data example for the user to acquire.

**Action:** The user acquire more data and rerun the loop starting from ease.ml/DataMagic.
