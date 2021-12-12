---
layout: list
title: CPClean
aliases: [/cpclean]
summary: What if ease.ml/snoopy thinks your data is not good enough for ML to reach your quality target? In this case, it might be counterproductive to fire up an expensive ML training process, instead, we hope to help the user to understand their data better and make a more informative decision.
thumbnail: images/easeml-component-generic.png
weight: 3
sections:
    - partial: content
    - title: Publications
      partial: list
      content:
        data: publications
        where:
          key: tag
          match: cpclean
          operator: eq
      params:
        header:
          field: year
        grouped: true
links:
  - icon: fa-github
    href: https://github.com/chu-data-lab/CPClean
    large: true
    label: Code
---

<div class="embedded-element">
{{< youtube VsW_eZTaQD4 >}}
</div>

In ease.ml, our belief (which of course is far off from perfect) is that there are two key reasons behind an unsatisfactory quality — (1) the existing data is too noisy and we need to clean it up, and (2) the existing dataset is too small and we need to acquire more.

CPClean tries to provide insights on the impact of data noises to the trained ML model. In principle, it asks the following question — given a noise distribution on each data value (which can be constructed using an ensemble of state-​of-the-art data cleaning tools), what’s the highest possible accuracy that an ML model can achieve? This value will provide the user more insights on what to do — if such an accuracy is high enough, the user should conduct data cleaning using state-​of-the-art techniques; otherwise, data cleaning might simply be a waste of efforts an the users are probably better off acquiring more data.

The technical challenge here is that there are exponentially many possible combinations of noisy values and how can we find the one with best ML accuracy? We show that, surprisingly, for k-​nearest neighbour classifiers, this problem can be solved in polynomial (and sometimes linear) time! By using a k-​nearest neighbour classifier as a proxy, CPClean provides users the signal corresponding to the potential of data cleaning.

As a by-​product, there is an interesting connection between CPClean and robustness (especially randomised smoothing). We show that it is possible to extend the idea behind CPClean to provide the first provably robust defence to backdoor attacks.

**Input:** Augmented, machine readable, dataset.

**Output:** The system’s belief on the best possible KNN accuracy after data cleaning.

**Action:** (1) If the potential is high, proceeds to state-​of-the-art data cleaning tools and rerun the loop starting from ease.ml/DataMagic; (2) If the potential is low, proceeds to Market to acquire more data.
