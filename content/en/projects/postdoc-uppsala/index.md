---
title: "From mathematical foundations to medical images"
summary: "Postdoctoral research at Uppsala University (2005–2006): extending chamfer distance transforms to anisotropic grids with formal proof of their metric properties, directly motivated by medical volumetric imaging."
date: 2006-08-01
lastmod: 2006-08-01
tags:
  - distances-de-chanfrein
  - "geometrie-discrete"
image:
  filename: featured.png
  caption: "BCC and FCC grids — non-standard lattices for medical imaging"
  focal_point: Smart
---

> This project deliberately steps away from applied prototyping. It reflects another side of my approach: the ability to work at a rigorous level of mathematical abstraction, to produce formal proofs, and to publish in leading discrete mathematics journals — while keeping a concrete medical imaging application in view.

From September 2005 to August 2006, I held a postdoctoral position at the [Centre for Image Analysis](https://www.uu.se/en/centre/image-analysis) at Uppsala University, Sweden — one of the founding laboratories of discrete geometry applied to images. There I had the opportunity to work alongside [Gunilla Borgefors](https://en.wikipedia.org/wiki/Gunilla_Borgefors), a pioneer of the field, whose 1986 paper on distance transforms in digital images remains a landmark reference cited by thousands of researchers — including today in the computation of loss functions for U-Net networks in deep learning segmentation.

---

## The starting point: computing distances in an image

A **distance transform** is a fundamental operation in image processing: for each pixel of an object, it computes its distance to the nearest boundary. It is ubiquitous — segmentation, skeletonisation, registration, cost function computation in machine learning.

The Euclidean distance is the most natural, but it raises two practical issues:

- It is **continuous**, and therefore expensive to compute exactly on a discrete grid.
- The **squared** Euclidean distance (d²E), which is discrete, does not satisfy the triangle inequality.

This second point deserves an illustration. The triangle inequality simply states that the direct path between two points can never be longer than going via an intermediate stop — it is the fundamental property of any mathematically valid distance.

{{< figure src="triangle_inequality.svg" caption="2D example: d²E(p,q) = 9 > d²E(p,o) + d²E(o,q) = 7. The detour via o is cheaper than the direct path — the shortest path is not the straight line!" >}}

The **chamfer distance** solves this: it is an efficient way to compute distances in a digital image without examining every possible path. Each displacement direction (4-connected, 8-connected neighbour, etc.) is assigned a local weight, and these weights are propagated in a simple two-pass scan of the image. The result is a discrete, integer-valued, fast-to-compute distance — which, under certain conditions on the weights, satisfies all the properties of a mathematical norm.

{{< figure src="chamfer_forward.png" caption="Chamfer algorithm — 1st pass: propagation left to right, top to bottom" >}}

{{< figure src="chamfer_backward.png" caption="Chamfer algorithm — 2nd pass: propagation right to left, bottom to top" >}}

---

## The specific problem: medical images are anisotropic

On an **isotropic** grid (square pixels, cubic voxels), chamfer distances are well understood. But medical images are rarely isotropic.

{{< figure src="anisotropic_medical.png" caption="Anisotropic medical image: voxels are elongated in the axial direction" >}}

A typical CT scan has a resolution of 0.5 mm × 0.5 mm within the axial plane, but 2 to 5 mm between slices. If one naively applies a chamfer algorithm designed for an isotropic grid to such an image, the computed distances no longer satisfy the triangle inequality — and can lead to geometric absurdities where the direct path between two points appears longer than a detour.

**The standard workaround** is to resample the image to make it isotropic before computing distances. But this resampling introduces artefacts and significantly increases processing overhead.

---

## My contribution: a unified theory for arbitrary grids

My postdoctoral work consisted in developing a general mathematical framework for computing chamfer distances directly on any grid — in particular the anisotropic grids of medical images — with the formal guarantee that the resulting distance is a genuine **norm** in the mathematical sense (positive, symmetric, triangle inequality, positive homogeneity).

The key insight is the notion of a **module**: by generalising the standard discrete grid framework (Z²) to that of modules over commutative rings, I was able to establish the necessary and sufficient conditions on the chamfer mask weights to guarantee the norm property — independently of the grid geometry.

This work led to three major contributions:

### 1. Distances on general grids — proof of the norm

The main paper in *Pattern Recognition* (2007) establishes the complete theory: definitions, properties (distance, metric, norm), validity conditions for the sequential two-scan algorithm, and application to FCC (*face-centered cubic*) and BCC (*body-centered cubic*) grids — crystallographic structures with optimal sampling properties for 3D medical imaging.

**My contribution**: I was the primary author of this paper. I developed the generalisation to modules, established the validity conditions for the two-pass algorithm on arbitrary grids, and computed the optimal weights for FCC and BCC grids.

- **[Pattern Recognition 2007]** C. Fouard, R. Strand, G. Borgefors — *Weighted distance transforms generalized to modules and their computation on point lattices* — [read](/en/publication/2007-fouard-pr/)

### 2. Distances on non-standard grids via neighbourhood sequences

An extension to distances defined by neighbourhood sequences (which allow even better isotropy), with formal proof of the conditions for the sequential algorithm to produce correct distance maps on square, cubic, FCC, and BCC grids.

- **[DGCI 2006]** R. Strand, B. Nagy, C. Fouard, G. Borgefors — *Generating distance maps with neighbourhood sequences* — [read](/en/publication/2006-strand-dgci/)

### 3. Comparison of grey-level distance transforms

A comparative study of two distance definitions on grey-level images (GWDT and WDTOCS), with theoretical and experimental analysis of their respective behaviours on different image types (density maps, height maps).

- **[DGCI 2006]** C. Fouard, M. Gedda — *Distance transforms on curved spaces* — [read](/en/publication/2006-fouard-dgci/)

---

## What this work gave me

Those twelve months in Uppsala taught me to hold two stances simultaneously: that of the mathematician who proves, and that of the engineer who solves a concrete problem. Formal rigour is not an end in itself — it is what guarantees that an algorithm will behave correctly on real data, including in the edge cases one did not anticipate.

The indirect impact of this work on medical imaging practice is real: most modern segmentation tools, including U-Net networks that compute their loss functions from distance maps, build on these theoretical foundations. I have not yet had the opportunity to apply these anisotropic distances directly in my applied research projects in Grenoble — but it is a direction I keep in mind, particularly for processing medical images without prior resampling.
