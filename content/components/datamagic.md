---
layout: list
title: DataMagic
aliases: [/datamagic]
summary: |
    What if ease.ml/snoopy thinks your data is not good enough for ML to reach your quality target? In this case,
    it might be counterproductive to fire up an expensive ML training process, instead, we hope to help the user
    to understand their data better and make a more informative decision.
thumbnail: images/easeml-component-generic.png
weight: 1
sections:
    - partial: content
    - title: Publications
      partial: list
      content:
        data: publications
        where:
          key: tag
          match: datamagic
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

The current version of ease.ml/DataMagic focuses on the NLP domain. For data augmentation, we designed a
novel framework of automatic style transfer for natural language text (e.g., passive to active voice). For data
ingestion, we designed a robust system, based on a novel weak supervision technique, to automatically parse
documents in different formats (e.g., PDFs, Word, scanned documents, etc.) to machine readable JSON objects.

**Input:** Input dataset with labels.

**Output:** Augmented, machine readable, dataset with labels.
