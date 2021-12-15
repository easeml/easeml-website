---
layout: list
title: DataMagic
aliases: [/datamagic]
summary: |
    Modern ML applications are often data hungry --- sometimes it is caused by the extensive process of data
    collection, and sometimes it is caused by the striking diversity of the data format that makes it hard 
    to construct a homogeneous large dataset. Given an input dataset from the user, the first step of the 
    ease.ml process, ease.ml/DataMagic, aims at providing functionalities of automatic data augmentation 
    (adding new data examples automatically) and automatic data ingestion (automatically normalizing data 
    into the same, machine readable, format).
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
