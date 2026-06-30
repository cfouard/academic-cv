---
title: Interventional cardiology
subtitle: "From clinical need to prototype: guiding the gesture at the heart of the cath lab"
summary: "Guiding the gesture in interventional cardiology, from preoperative imaging to the intervention room. A project where a data constraint was turned into a better-targeted clinical innovation — from cell therapy to mapping for endomyocardial biopsy."
tags:
  - cardiologie
  - "pilotage-projets"
  - "analyse-images-medicales"
  - "ia-sante"
  - "navigation-robotique"
image:
  filename: featured.png
  caption: "Image-guided interventional cardiology"
  focal_point: Smart
---

*From clinical need to prototype: guiding the gesture at the heart of the cath lab.*

Interventional cardiology is performed under imaging, yet the clinician must often act without directly seeing the target: the lesion to treat or to biopsy does not appear on the real-time image in the room. Carried out with Prof. Gilles Barone-Rochette (Grenoble Alpes University Hospital) and the LTSI laboratory in Rennes, this project pursues a single goal expressed through two clinical questions: **to give the cardiologist reliable guidance, built from preoperative imaging and usable directly in the room.**

## The common thread: bouncing back when the data runs short

The project started with the guidance of **cell therapy**. The first clinical trial enrolled fewer patients than expected: the data needed for the next steps were not there. Rather than abandoning it, we **redeployed the technical building blocks already developed** (image segmentation, navigation) toward a related clinical need with more immediate value and a better-identified bottleneck: **endomyocardial biopsy**.

This pivot is, in itself, a deliverable: it illustrates the ability to **de-risk a project, preserve the assets already built, and refocus the effort** where the clinical value is highest — exactly the kind of trade-off a company expects when an R&D programme does not go as planned.

## Sub-project 1 — Guiding post-infarction cell therapy

After a heart attack, some therapies consist in re-injecting cells into the myocardium. The whole challenge is **precision**: reaching the right areas, relying on information (the extent of fibrosis, the viable regions) that is only visible on preoperative imaging, not on the real-time image in the room.

Our approach: **fuse multimodal imaging** to transfer, during the intervention, the targets identified preoperatively. The core building block is the **automatic segmentation of the myocardium and fibrosis on late gadolinium enhancement MRI (LGE-MRI)**, developed using deep learning as part of Erwan Lecesne's PhD (co-supervised with the LTSI in Rennes), then integrated into [CamiTK](/en/projects/camitk/) to be presented to the clinician in the room.

{{< figure src="injection-cellules.png" caption="Re-injecting cells in the right place: the precision of the gesture determines the therapy's effectiveness." >}}

CamiTK is a **prototyping toolkit**: it makes it possible to move quickly from concept to evaluated prototype, but its output is not meant to be a CE-marked medical device. This building block is therefore a **proof of concept**; its **industrial transfer is currently under discussion** with partners in the field.

## Sub-project 2 — A map for endomyocardial biopsy

Three conditions — cardiac sarcoidosis, chronic myocarditis and arrhythmogenic cardiomyopathy — can present a **similar clinical picture yet call for opposite treatments**. To decide, a biopsy is needed… provided the sample is taken **in the right place**.

<div style="display: flex; justify-content: center;">{{< figure src="ponction-endomyocardique.png" caption="Endomyocardial biopsy: sampling a piece of cardiac tissue, where the lesion is located." >}}</div>

The state of the art leaves a real gap:

- "blind" biopsy is poorly specific, because the fibrosis to target stays invisible during the gesture;
- electro-anatomical guidance is long and, likewise, **blind to fibrosis**.

Our solution acts as a **"GPS" for the biopsy catheter**: it transfers the target identified on preoperative imaging onto the real-time image, to guide the sampling. Two design choices make it a solution **built for adoption**: it is **hardware-independent** (compatible with an existing room) and works **on real-time fluoroscopy, with no complex fusion step**. It **directly reuses** the segmentation building block from the first sub-project.

{{< figure src="systeme-biopsie.png" caption="Diagram of the proposed guidance system for endomyocardial biopsy (published)." >}}

Current status: we are **preparing the first clinical trials in the laboratory**; industrial transfer will follow.

## What this project demonstrates

- **Designing from a real clinical need**, in close dialogue with practitioners, rather than around a technical feat.
- **Mastering medical image processing and AI**, and putting them at the service of a precise, useful target.
- **Taking a prototype from the laboratory toward the clinic**, with a clear awareness of maturity stages (TRL), the trial framework and CE marking.
- **Architecting for adoption**: hardware independence, integration into a prototyping toolkit, reuse of building blocks.
- **Refocusing a project to preserve its value**: agility and de-risking in the face of the unexpected.
- **Leading a multi-site collaboration** (Grenoble–Rennes) and co-supervising a PhD.

## Funding obtained

| Funding | Amount | Purpose |
| --- | --- | --- |
| Famtastic project (France Life Imaging) | €20,000 | Kick-starting the collaboration with the LTSI (Rennes) |
| PUI (UGA) | €60,000 | Maturing the prototype toward the first clinical trials |
| PhD funding (LabeX CAMI) | €170,000 | Co-supervision of Erwan Lecesne's PhD |
| Post-doctorate (LabeX CAMI) | €56,000 | One year of post-doctoral engineering |
| **Total** | **€306,000** | |

## Collaborations and supervision

- **Prof. Gilles Barone-Rochette** — interventional cardiologist, Grenoble Alpes University Hospital: clinical partner of the project.
- **LTSI laboratory (Rennes)** — Professor Mireille Garreau and Antoine Simon (associate professor): collaboration on cardiac image processing.
- **Erwan Lecesne's PhD** (2020–2024), co-supervised at 50% with Mireille Garreau (LTSI): multimodal image processing to improve post-infarction cell therapy.
- **Théophile Tiffet's PhD** — medical resident: echocardiography / SPECT calibration for interventional cardiology.

## Related publications

{{< pubs_by_tag tag="cardiologie" >}}
