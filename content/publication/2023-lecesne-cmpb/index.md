---
title: Segmentation of cardiac infarction in delayed-enhancement MRI using probability map and transformers-based neural networks

date: '2023-12-01'

# Autheurs 
authors:
- Erwan Lecesne
- Antoine Simon
- Mireille Garreau 
- Barone-Rochette Gilles
- Celine Fouard

# # Publication type
# Options: article-journal, paper-conference, thesis, book, chapter, report, patent, manuscript
publication_types: ["article-journal"]

abstract: "Background and Objective: Automatic segmentation of myocardial infarction is of great clinical interest for the quantitative evaluation of myocardial infarction (MI). Late Gadolinium Enhancement cardiac MRI (LGE-MRI) is commonly used in clinical practice to quantify MI, which is crucial for clinical diagnosis and treatment of cardiac diseases. However, the segmentation of infarcted tissue in LGE-MRI is highly challenging due to its high anisotropy and inhomogeneities. Methods: The innovative aspect of our work lies in the utilization of a probability map of the healthy myocardium to guide the localization of infarction, as well as the combination of 2D U-Net and U-Net transformers to achieve the final segmentation. Instead of employing a binary segmentation map, we propose using a probability map of the normal myocardium, obtained through a dedicated 2D U-Net. To leverage spatial information, we employ a U-Net transformers network where we incorporate the probability map into the original image as an additional input. Then, To address the limitations of U-Net in segmenting accurately the contours, we introduce an adapted loss function. Results: Our method has been evaluated on the 2020 MICCAI EMIDEC challenge dataset, yielding competitive results. Specifically, we achieved a Dice score of 92.94% for the myocardium and 92.36% for the infarction. These outcomes highlight the competitiveness of our approach. Conclusion: In the case of the infarction class, our proposed method outperforms state-of-the-art techniques across all metrics evaluated in the challenge, establishing its superior performance in infarction segmentation. This study further reinforces the importance of integrating a contour loss into the segmentation process."


publication: '*Computer Methods and Programs in Biomedicine, vol 242*'

# Featured image
image:
  filename: 2023-lecesne-cmpb.png
  caption: "Architecture diagram"
  focal_point: Smart



doi: 10.1016/j.cmpb.2023.107841 
 
tags : 
  - cardio
---

