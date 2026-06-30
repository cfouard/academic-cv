---
title: "Medical Image Analysis"
summary: "Three pioneering projects in computer vision and image processing for computer-assisted surgery: distributed laparoscopy, ultrasound-based bone tracking, and prostate brachytherapy."
date: 2014-10-01
lastmod: 2014-10-01
tags:
  - "computer vision"
  - "3D ultrasound"
  - "brachytherapy"
  - "laparoscopy"
  - "segmentation"
  - "CamiTK"
  - "analyse-images-medicales"
image:
  filename: featured.webp
  caption: "Transperineal ultrasound-guided implantation — prostate brachytherapy"
  focal_point: Smart
---

When I joined the [GMCAO](https://www.timc.fr/gmcao) research group at TIMC laboratory in 2006, I contributed my expertise in medical image processing and analysis to three ongoing applied projects led by my colleagues. These collaborations allowed me to tackle diverse clinical challenges — from real-time surgical vision to oncological dose computation — while immersing myself in the tools and culture of the team.

> These three projects are grounded in rigorous academic knowledge production: each contribution led to publications in international peer-reviewed journals and conferences, or to a patent filing. The skills described here were forged *alongside* that scientific output — they are its direct product.

These three projects embody a conviction that has shaped my entire approach: **a medical image is only as good as its usability by the clinician, at the right moment and in the right context**.

---

## Prostate Brachytherapy — Orientation of Iodine-125 Seeds

> *Project led by Jocelyne Troccaz (TIMC-GMCAO)*  
> Co-supervision of post-doctoral researcher **Giao Nguyen** (50%, with Jocelyne Troccaz)

### Context
{{< figure src="prostateBrachytherapy-context.webp" caption="Transperineal implantation guided by ultrasound — clinical context" >}}

Prostate brachytherapy involves implanting radioactive iodine-125 seeds directly into the prostate gland. Calculating the radiation dose absorbed by tumour tissue — **dosimetry** — is critical for evaluating treatment effectiveness and anticipating side effects. At the time, dosimetry tools modelled seeds as **isotropic point sources**, ignoring their actual orientation within the tissue.

The research question: *does seed orientation influence dosimetry enough to warrant its inclusion in clinical software?*

### Contributions

To answer this, we first needed to **automatically detect and localise seeds** in post-operative CT images — a challenging task, as seeds are small, closely spaced, and may overlap in projection.

{{< figure src="prostateBrachytherapy-02.png" caption="Implanted seeds as visible in a CT slice: single seeds, clustered seeds, and pelvic bones" >}}

We developed a complete pipeline for:

- **Segmentation** of iodine seeds in CT images
- **Separation** of seeds that touch or overlap
- **Pose estimation** (3D position + orientation) of each individual seed

{{< figure src="prostateBrachytherapy-01.png" caption="3D localisation of brachytherapy seeds in the prostate (CamiTK visualisation)" >}}

Results confirmed that seed orientation had a **measurable impact on dosimetry** — a clinically significant finding for post-operative evaluation and treatment follow-up.

### Skills Applied

- 3D medical image processing (CT)
- Geometric modelling of radioactive sources
- Software development and integration into the **CamiTK** platform for clinical use
- Validation protocols on real patient data

### Related Publications

- **[IEEE TBME 2015]** H.-G. Nguyen, C. Fouard, J. Troccaz — *Segmentation, separation and pose estimation of prostate brachytherapy seeds in CT images* — [read](/en/publication/2014-nguyen-isbi/)
- **[Cancer/Radiothérapie 2014]** F. Meneu, H. Nguyen, C. Fouard et al. — *Impact de l'orientation des grains iode 125 dans l'évaluation de la dosimétrie à 1 mois* — [read](/en/publication/2014-meneu-cancer/)
- **[Physica Medica 2013]** F. Meneu, G. Nguyen et al. — *Consideration of seeds orientation in prostate brachytherapy and dosimetry analysis* — [read](/en/publication/2013-meneu-physicamedica/)

---

## 3D Ultrasound-Based Bone Tracking

> *Co-supervision at 50%, with Jocelyne Troccaz*  
> PhD thesis of **Jonathan Schers** (2006–2009)

{{< figure src="us-bone-tracking-02.png" caption="Ultrasound-guided orthopaedic intervention: the clinical context" >}}

### Context

Orthopaedic procedures — prosthesis placement, osteotomies — require **real-time tracking of bone structures** during surgery. Classical techniques rely either on X-ray imaging (radiation) or on invasive bone markers. The goal of this project was to explore a **minimally invasive** alternative: tracking bone structures using **3D ultrasound**.

### Contributions

We proposed a per-operative tracking method based on **3D/3D ultrasound image registration**: from a reference volume acquired at the start of the procedure, bone displacements are tracked by registering each new acquisition against that reference.

{{< figure src="us-bone-tracking-03.png" caption="Segmentation of the bone surface in an ultrasound image" >}}

Key scientific contributions:

- **Segmentation of bone surfaces** in ultrasound images (noisy signal, reflection artefacts)
- **Rigid and deformable registration** methods adapted to the ultrasound modality
- **Panoramic reconstruction** from multiple partial acquisitions
- Evaluation on cadaveric anatomical specimens


### Skills Applied

- Ultrasound signal processing
- Multimodal medical image registration
- Design of a ground-truth-free registration validation method
- Doctoral co-supervision (50%)

### Related Publications
- **[IUS 1007]** J. Schers, J. Troccaz, V. Daanen, C. Fouard, C. Plaskos, P. Kilian - *3D/4D ultrasound registration of bone* - [read](/en/publication/2007-schers-ius/)
- **[IJCARS 2009]** J. Schers, J. Troccaz, C. Fouard, C. Plaskos, O. Palombi — *3D/3D ultrasound registration for panoramic volume reconstruction* — [read](/en/publication/2009-schers-cars/)
- **[CAOS 2010]** J. Schers, C. Fouard, J. Troccaz — *Non invasive ultrasound-based bone tracking* — [read](/en/publication/2010-schers-caos/)

---

## Distributed Laparoscopy — Extended View of the Surgical Field

> *Co-supervision at 50%, with Philippe Cinquin*  
> PhD thesis of **Christophe Boschet** (2007–2010)

{{< figure src="distributive-laparoscopy-02.jpg" caption="Standard laparoscopy: a single camera, a narrow field of view" >}}

### Context

During a laparoscopic procedure, the surgeon's field of view is **very narrow**: the endoscopic camera, inserted through a trocar, only covers a small portion of the abdominal cavity. The surgeon must constantly reposition the camera to explore the operative field, which is cognitively demanding and lengthens procedures.

The idea: replace a single high-resolution camera with **several small, distributed miniature cameras** (similar to the phone cameras of the day), and **reconstruct a real-time 3D panoramic view** of the operative zone.

{{< figure src="distributive-laparoscopy-01.jpg" caption="Standard laparoscopy: a single camera, a narrow field of view" >}}

### Contributions

This project posed novel challenges at the intersection of computer vision and embedded computing:

- **Calibration** of multiple miniature cameras in an endoscopic configuration
- **3D reconstruction** of the surgical field via distributed stereovision
- **Fusion of video streams** to produce a coherent augmented view
- Integration into the CamiTK platform and prototyping for pre-clinical experimentation

{{< figure src="distributive-laparoscopy-03.jpg" caption="3D reconstruction of the operative field from multiple cameras (CamiTK)" >}}

The project remained at the research prototype stage but led to a **European patent filing**.

### Skills Applied

- Stereoscopic computer vision
- Multi-camera optical system calibration
- Hardware/software integration
- Patent writing

### Related Output

- **[Patent EP 2016]** P. Cinquin, S. Voros, C. Boschet, C. Fouard, A. Moreau-Gaudry — *Imaging system for the three dimensional observation of an operation field* — [read](/en/publication/2008-cinquin-patent/)

---

## What These Projects Taught Me

These three collaborations were a **practical school in medical prototyping** — and far more than a checklist of technical skills.

I learned to work with real, imperfect clinical data, often without ground truth available to validate the algorithms. I developed the reflex of **designing rigorous evaluation protocols** where standard benchmarks didn't exist, and of **integrating operating room constraints** from the design phase — time pressure, sterility requirements, ergonomics for the surgeon.

I also shaped my collaborative approach: learning to ask the right questions to clinicians, to translate a medical need into an algorithmic problem, to deliver tools integrated into a software platform usable by non-computer-scientists.

These skills — built *alongside* a sustained effort in scientific publication and formal knowledge production — are the ones I bring today to medical application prototyping.
