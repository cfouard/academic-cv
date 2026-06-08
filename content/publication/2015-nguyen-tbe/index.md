---
title: Segmentation, separation and pose estimation of prostate brachytherapy seeds in CT images

date: '2015-03-06'

# Autheurs 
authors:
- Nguyen Huu-Giao
- Fouard Céline
- Troccaz Jocelyne
  
# # Publication type
# Options: article-journal, paper-conference, thesis, book, chapter, report, patent, manuscript
publication_types: ["article-journal"]

abstract: "Goal: In this paper, we address the development of an automatic approach for the computation of pose information (position + orientation) of prostate brachytherapy loose seeds from 3-D CT images. Methods: From an initial detection of a set of seed candidates in CT images using a threshold and connected component method, the orientation of each individual seed is estimated by using the principal components analysis method. The main originality of this approach is the ability to classify the detected objects based on a priori intensity and volume information and to separate groups of closely spaced seeds using three competing clustering methods: the standard and a modified k-means method and a Gaussian mixture model with an expectation-maximization algorithm. Experiments were carried out on a series of CT images of two phantoms and patients. The fourteen patients correspond to a total of 1063 implanted seeds. Detections are compared to manual segmentation and to related work in terms of detection performance and calculation time. Results: This automatic method has proved to be accurate and fast including the ability to separate groups of seeds in a reliable way and to determine the orientation of each seed. Significance: Such a method is mandatory to be able to compute precisely the real dose delivered to the patient postoperatively instead of assuming the alignment of seeds along the theoretical insertion direction of the brachytherapy needles."

publication: '*IEEE Transactions on Biomedical Engineering, vol 62, Issue 8*'

# Featured image
image:
  filename: 2015-nguyen-tbe.png
  caption: "Architecture diagram"
  focal_point: Smart

doi: 10.1109/TBME.2015.2409304

tags:
  - Curietherapy
---

