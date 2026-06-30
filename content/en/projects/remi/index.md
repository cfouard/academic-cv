---
title: "REMI — Decision Support for Lower-Limb Endovascular Revascularization"
summary: "How do you help a vascular surgeon choose the best revascularization strategy when a technique's success is hard to predict? A multidisciplinary clinical project that turns accumulated experience into an interpretable decision-support system — from collecting real-world data to software deployed in the clinic."
date: 2021-09-01
lastmod: 2026-06-10
tags:
  - remi
  - raisonnement-par-cas
  - aide-a-la-decision
  - chirurgie-vasculaire
  - apprentissage-automatique
  - "pilotage-projets"
  - "ia-sante"
image:
  filename: featured.png
  caption: "The Case-Based Reasoning (CBR) cycle applied to surgical decision-making (fig. 2.5, M. Roux thesis)"
  focal_point: Center
---

*How do you help a vascular surgeon choose the best revascularization strategy, when the success of a technique remains hard to predict? REMI explores one answer: learning from past cases — the way an experienced clinician does — but in a tooled, traceable and interpretable way.*

## The result, first

**REMI** (from the French *Revascularisation Endovasculaire des Membres Inférieurs* — Lower-Limb Endovascular Revascularization) is a clinical decision-support project I have coordinated since 2021, in close collaboration with the vascular surgery department of Grenoble Alpes University Hospital. Within a few years, it has made it possible to:

- design and **deploy in the clinic** a user-centred data-collection software;
- turn real clinical data — incomplete and heterogeneous — into a usable **case base**;
- demonstrate the relevance of **case-based reasoning** to suggest, for a new patient, the strategies that succeeded in similar patients;
- bring a doctoral thesis to completion (**Margaux Roux**, defended with distinction on 16 December 2025) and lead a multidisciplinary team funded by five successive grants.

This project consisted of taking a concrete clinical need, translating it into specifications, removing the technical *and* organizational roadblocks, and going all the way to a genuinely used prototype.

## The clinical problem: a decision that is hard to anticipate

**Peripheral Arterial Disease (PAD)** of the lower limbs is an arterial condition whose main symptoms are pain and ischemic wounds. To avoid severe complications — amputation, death — **revascularization** aims to restore blood flow, either endovascularly (angioplasty, stenting) or through open surgery.

The problem: the probability of success or failure of a given technique remains **hard to predict**. The surgeon relies on decision trees, scores (WIfI) and, above all, on experience. To date, no tool fully helps them choose, for *this* patient, the most promising strategy.

{{< figure src="techniques-endovasculaires.png" caption="Endovascular revascularization techniques: angioplasty and stenting (fig. 1.9, M. Roux thesis)." >}}

## A method: case-based reasoning

Clinical decision-support systems traditionally fall into two families: **statistical** approaches, powerful but often poorly interpretable ("black boxes"), and **expert-rule** approaches, transparent but hard to scale.

REMI explores a middle path: **Case-Based Reasoning (CBR)**. Its assumption — *"similar problems have similar solutions"* — translates, in the clinic, into: *similar symptoms, treated with similar therapies, lead to similar outcomes*. It is a learning method close to medical reasoning itself, and naturally more **explainable**: every recommendation rests on real cases that can be examined.

The CBR cycle unfolds in four steps (shown in the cover image): **retrieve** similar cases, **reuse** and adapt their solution, **revise** the outcome, then **retain** the new case to enrich the base.

## From raw clinical data to a usable case base

This is often the most underestimated — and most structuring — step. The data available in electronic health records are incomplete, heterogeneous and designed for care, not for analysis. The project therefore had to:

- **model a "case"**: a set of attributes describing the problem (severity, WIfI score, lesion anatomy, comorbidities) and a second set describing the surgical solution and its outcome;
- explicitly handle **missing data** and attribute typing;
- combine **retrospective** and **prospective** data, then develop a **Python** extraction-and-aggregation pipeline that transforms patient-centred data into a decision-support-oriented case base.

{{< figure src="modele-donnees.png" caption="Class diagram of the data model implemented in the collection software (fig. 3.9, M. Roux thesis)." >}}

## A user-centred prototype, deployed in the clinic

To collect high-quality prospective data, we designed a **prototype software** directly usable by clinicians, within their workflow. It automatically computes the **WIfI score** (and thus the amputation risk), models an operation as a sequence of surgical gestures applied to lesions, and automatically generates an **operative report**.

This is exactly the kind of deliverable I care about: a tool designed *with* and *for* its users, robust enough to leave the lab bench and enter clinical practice. Developing this application justified hiring a dedicated research engineer.

{{< figure src="logiciel-prototype.png" caption="Interface of the prototype data-collection software (fig. 3.11, M. Roux thesis)." >}}

{{< video src="demo-logiciel.mp4" controls="yes" >}}

*Demo video of the software, presented at the project's first conference (in French).*

## Representing cases to compare them

Comparing two patients requires a sound **similarity** measure between cases. The project relies on an **autoencoder**: a neural network that learns to represent each case in a compact latent space, where geometric proximity reflects clinical similarity. Retrieval of relevant cases then takes place in that space.

{{< figure src="espace-latent.png" caption="Retrieval of similar cases in the learned latent space (fig. 4.4, M. Roux thesis)." >}}

## Project leadership and funding

Started in 2021 with Prof. Rafaëlle Spear, the project gradually brought together three sites (TIMC in Grenoble, LTSI in Rennes, Grenoble Alpes University Hospital) and was supported by **€284,450** raised from four funding sources.

| Period | Project / scheme | Co-lead(s) | Funding obtained | Source | Amount |
|---|---|---|---|---|---|
| 2021–2022 | REMI-ORIA | Rafaëlle Spear | Equipment | EMERGENCE (TIMC laboratory) | €12,000 |
| 2022–2023 | *User-centered development for data collection in endovascular revascularization* | Rafaëlle Spear & Alexandre Demeure | 2 Master's (M2) interns (Laure Chatenet & Clément Gasse) | MIAI@Grenoble Alpes (ANR-19-P3IA-0003) | €11,200 |
| 2024–2025 | *CAMI-assistant chair* | Sandrine Voros | 1 research engineer for one year (Romaric Ruga) + equipment | MIAI@Grenoble Alpes (ANR-19-P3IA-0003) | €66,056 |
| 2024–2026 | Decision support — REMI | Rafaëlle Spear & Pascal Haigron | 1 PhD student (Margaux Roux) | LabeX CAMI | €160,000 |
| 2026–2027 | Clinical deployment and validation of an AI tool | Rafaëlle Spear | Thesis completion + 1 intern + software subcontracting | Fondation pour l'Avenir | €35,194 |
| | | | | **Total** | **€284,450** |

## Supervision and collaborations

- **Margaux Roux**, PhD student — thesis *"Decision support for lower-limb endovascular revascularization"*, defended on 16 December 2025 (co-supervision at 33% with R. Spear and P. Haigron).
- **Laure Chatenet** and **Clément Gasse**, Master's (M2) interns.
- **Romaric Ruga**, research engineer (finalizing the data-collection software).
- **Prof. Rafaëlle Spear** (PU-PH, vascular surgery, Grenoble Alpes University Hospital) — clinical co-lead since the project's inception.
- **Prof. Pascal Haigron** (University of Rennes, LTSI) — thesis co-supervisor.
- **Sandrine Voros** (TIMC) and **Alexandre Demeure** — co-leads on funding schemes.

## Publications

{{< pubs_by_tag tag="remi" >}}

---

*Together with [Prasad Samarakoon's thesis](/en/projects/these-samarakoon/), this project anchors my work in [AI applied to healthcare](/en/topic/ia-sante/) — with one constant requirement: interpretable methods, genuinely usable tools, and an ongoing dialogue with clinicians.*
