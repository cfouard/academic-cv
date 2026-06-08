---
title: Extraction de paramètres morphométriques pour l'étude du réseau micro-vasculaire cérébral

date: '2005-01-21'


authors:
- Fouard Céline

# # Publication type
# Options: article-journal, paper-conference, thesis, book, chapter, report, patent, manuscript
publication_types: ["report"]

abstract: "Our aim is to provide anatomists and neuroanatomists with software tools to quantitatively analyze 3-D images of the cerebral micro-vascular network.
Such analyses require that input images be both of high resolution and of large size, to take into account the smallest capillaries and cover areas of the brain sufficiently wide to be statistically relevant, respectively. As it cannot be acquired at once, we propose to pave the image area with smaller images acquired with a confocal microscope to obtain an “image mosaic”. We developed dedicated building tools for this kind of mosaic to allow large and precise images. But these images are to large to be loaded and process at once in the memory of a standard computer. We therefor developed dedicated image analysis tools (filtering, thresholding, mathematical morphology, discrete topology tools...) for such mosaic which process with sub-images.
Micro-vascular network analysis requires vessels’ center lines extraction and a vessel diameters estimation. Discrete geometry lends itself as a particularly appropriate and powerful framework for this kind of processes. We indeed have to compute distance map on each image point. To obtain the best trade-off between precision and computational cost, we choosed chamfer distances. One of our contributions was to propose an automatic computation of chamfer coefficients adapted to any grid anisotropy.
The use of such distance maps can guide skeletonisaton algorithms. Such algorithms require to keep the global property of topology. As we can only access sub-images we proposed a new skeletonization algorithm which minimizes the number of disk access to guaranty an acceptable computational time as well as a good skeleton localization. The developed algorithms have been integrated within the ergonomic software Amira and are currently in use at the INSERM research institute.
Keywords : brain micro-vascular network, discrete geometry, chamfer distance, distance ordered homotopic thinning, block-wise skeletonization."

publication: 'Thèse de doctorat, *Université de Nice Sophia Antipolis*'

links:
- name: URL
  url: https://theses.hal.science/tel-00308884/

tags:
  - chamfer distances
  - thèse
  
---

