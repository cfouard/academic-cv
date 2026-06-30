---
title: "Automatically locating organs in CT images"
subtitle: "PhD supervision — machine learning in the service of computer-assisted intervention"
summary: "Co-supervision of Prasad Samarakoon's PhD (2016): lighter, more robust regression forests to automatically locate organs in CT images, within the LPR project. My first turn toward machine learning."
date: 2016-09-30
lastmod: 2016-09-30
tags:
  - "ia-sante"
  - "machine-learning"
  - "regression-forest"
  - "pilotage-projets"
  - "analyse-images-medicales"

image:
  filename: featured.png
  caption: "Automatic localization of the kidneys in a CT volume, using bounding boxes"
  focal_point: Smart
---

*My first turn toward machine learning — taken, with this student, two years before the deep-learning boom.*

In the continuation of the [LPR](/en/projects/lpr/) project, I co-supervised with Emmanuel Promayon the PhD of **Prasad Samarakoon**, defended on 30 September 2016 at Université Grenoble Alpes (funded by the French ANR TecSan project "Robacus"). This is the project that tipped me toward **machine learning** applied to medical imaging. We started two years *before* the rise of deep-learning segmentation: so we bet not on deep neural networks, but on **decision-tree forests** (*random forests*) — a clear-eyed choice for the time, and a formative one.

> What this thesis really gave me was not one more method: it was an early familiarity with the **strengths and the limits** of learning-based approaches — first among them their surprising robustness.

## The challenge: locating, not segmenting

To plan a puncture assisted by the LPR robot, one must first locate, in the CT scan, the target organs and those to avoid — a step still done *by hand* by the clinician, tedious and costly in expert time. Rather than aiming straight for full segmentation (delineating every contour), we tackled the more tractable and equally useful problem of **localization**: enclosing each organ in a bounding box, automatically.

## The contribution

Beyond a thorough analysis of the method, the thesis produced two contributions of real practical reach:

- the **Light Random Regression Forests**: a faster and far more memory-efficient model, at equivalent accuracy — and therefore easier to embed and deploy;
- an **automatic parametrization** that removes settings previously fixed "by hand", making the method more robust and more reproducible from one dataset to another.

{{< figure src="pipeline-rrf.png" caption="The regression-forest pipeline: training-set preparation, preprocessing, training, then prediction (data in yellow, algorithmic steps in blue)" >}}

## Robustness — and bias: the phantom-kidney story

One experiment remains, for me, the perfect illustration of what these methods really are. To learn to locate the kidneys, our training database — built from experts' manual delineations (ours and those of the team's PhD students) — contained only patients **with two kidneys**. During the testing phase, the radiologist handed us the image of a patient who had **only one**. The algorithm dutifully found… **two bounding boxes**, placing a "phantom kidney" exactly where statistics expected it.

Even then, we were alert to a truth that has lost none of its relevance: **a model is only the reflection of the data it is shown.** The quality and representativeness of the training set matter as much as the algorithm itself.

## What this project represented

With the rise of deep learning, this forest-based localization strategy was later set aside — but it was decisive. It let me approach the machine-learning turn **from the foundations**, at a time when one still took the time to understand *why* a method works, what it guarantees, and where it fails. That perspective — robustness, generalization, vigilance about the data — is exactly what I bring today to medical-application prototyping.

**Skills involved:** doctoral co-supervision · machine learning applied to medical imaging · design of robust, automatic methods · building and critically assessing training datasets.

## Related publications

{{< pubs_by_tag tag="prasad" >}}
