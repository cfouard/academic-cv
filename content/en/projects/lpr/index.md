---
title: "A lightweight puncture robot for interventional radiology"
subtitle: "From concept to evaluation: designing a CT- and MRI-compatible robot, robust and automatic"
summary: "Coordination and design of the LPR (Light Puncture Robot): a lightweight, patient-mounted puncture robot, compatible with both CT and MRI, able to register itself automatically in the image. A project carried from concept to evaluation, at the interface of research, clinical practice and industry."
date: 2016-07-01
lastmod: 2026-06-10
tags:
  - "robotique-medicale"
  - "radiologie-interventionnelle"
  - "recalage"

image:
  filename: featured.png
  caption: "The LPR: a lightweight, patient-mounted puncture robot, compatible with CT and MRI"
  focal_point: Smart
---

*Designing a puncture robot compatible with both CT and MRI, able to register itself in the image — and carrying it from concept all the way to clinical evaluation.*

## The procedure to assist

Inserting a needle under imaging guidance is a routine interventional radiology procedure: for a biopsy or a tumour ablation, the clinician acquires a volumetric image, identifies a trajectory on a slice, then inserts the needle. The gesture is delicate: at the moment of insertion, the radiologist has very few guidance tools and relies mainly on experience and on memorising the chosen slice. Under CT, checking the trajectory requires repeated control images — meaning radiation, back-and-forth, and patient discomfort. Under MRI, the gesture becomes almost impossible to perform by hand inside the tunnel.

## The LPR in action

The LPR (*Light Puncture Robot*) is a lightweight robot, placed directly on the patient to follow their movements as closely as possible. The video below shows it in use, from automatic registration in the image through to needle positioning:

{{< video src="lpr-demo.mp4" controls="yes" >}}

> Lightweight, patient-mounted, compatible with both CT **and** MRI, and able to register itself: a single system that moves from one imaging modality to another with no manual tuning. Genericity is not a luxury — it is what makes a technology transferable from one clinical context to another.

## Results that match the clinical stakes

Phantom evaluation confirmed an accuracy compatible with the intended clinical use:

- under **CT**: targeting error of **3.3 ± 1.7 mm** and needle orientation under **1°**;
- under **MRI**: targeting under **5 mm** (limited by image resolution) and orientation under **2°**.

The intended clinical accuracy — under 5 mm — was achieved in both modalities.

## Controlling the robot remotely, in real time

In collaboration with the **LIRMM team (Montpellier)**, a partner of the ANR Robacus project, we demonstrated real-time remote control of the robot through a force-feedback teleoperation interface. A step toward a procedure where the radiologist would drive the insertion from the control room, without being exposed to radiation.

{{< video src="teleoperation-lirmm.mp4" controls="yes" >}}

## A coordination project

Beyond the technical side, this project was a long adventure in **coordination at the interface of research, clinical practice and industry**. I coordinated the **ANR-11-TECS-020-01 Robacus** project, which brought together two laboratories (TIMC and LIRMM), a university hospital (Grenoble Alpes University Hospital, through the CIC-IT and the radiology department) and a company (Axe Systems, for manufacturing the robot). I also coordinated the Carnot LSI LPROP project, supervised three post-doctoral researchers (Nabil Zemiti, Nikolaï Hungr, Baptiste Veron) and around ten Master's interns.

The control software was built on [CamiTK](/en/projects/camitk/), the medical-application prototyping framework I co-develop. Its modularity allowed code to be reused from one prototype version to the next — exactly the kind of method that saves time in industrial prototyping.

> Reusing a software building block from one prototype to the next instead of rewriting everything: that is what turns a lab demonstration into a technology that moves fast.

## Toward the clinic

This research phase laid the groundwork for a far more demanding stage: bringing the robot to the first trials on humans. That is the subject of the [LPR's TRL progression](/en/projects/lpr-trl/) page — overhaul under quality assurance, risk analysis, preclinical trials on healthy volunteers, and industrial maturation.

**Skills involved:** multi-partner project coordination (research · clinical · industry) · design of robust, automatic algorithms · multi-modality porting (CT / MRI) · modular, reusable software architecture for medical-application prototyping.

## Related publications

{{< pubs_by_tag tag="lpr" >}}
