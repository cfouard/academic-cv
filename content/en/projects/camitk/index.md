---
title: "CamiTK: a workshop for prototyping medical applications"
subtitle: "From software to method — capitalizing on interdisciplinary know-how to move faster, from concept to validated prototype."
summary: "Co-founder of CamiTK, an open-source workshop for prototyping medical applications. A software building block that grew into a maturity-scaling (TRL) methodology, adopted for over 15 years — packaged in Debian and still developed today (version 6.0)."
date: 2011-11-01
lastmod: 2026-06-19
tags:
  - camitk
  - prototypage
  - genie-logiciel
  - open-source
  - interdisciplinarite
  - "pilotage-projets"
image:
  filename: featured.png
  caption: "CamiTK — Computer Assisted Medical Intervention ToolKit"
  focal_point: "Center"
---

*From software to method — capitalizing on interdisciplinary know-how to move faster, from concept to validated prototype.*

Designing an application for the operating room is never "just code." It means getting medical images, sensors, biomechanical models — sometimes a robot — and above all specialists who don't speak the same technical language, to work together. **CamiTK** is the tool I co-founded with Emmanuel Promayon **so that this dialogue produces prototypes** — fast, clean, and reusable. It is also the foundation of expertise I now draw on to help companies prototype medical applications.

<div class="camitk-logo"><style>.camitk-logo{display:flex;justify-content:center;margin:1.75rem 0;}.camitk-logo img{max-width:240px;height:auto;}</style>{{< figure src="camitk-logo.png" alt="CamiTK logo" >}}</div>

## The problem: interdisciplinarity is expensive

In computer-assisted medical interventions, every team shows up with its own world: its operating system, its language of choice, its libraries, its habits — and its level of maturity, from throwaway prototype to clinical-grade software. With each new project, the temptation is to rewrite everything. You reinvent the wheel, you lose months, and the know-how walks out the door when someone leaves the team.

For a company, this is exactly the pain point: *how do you avoid starting from scratch with every innovation, while keeping the rigor that medical work demands?*

## The answer: a shared software foundation

With Emmanuel Promayon, we designed CamiTK as a **modular workshop**: a stable core that handles what is common to every project — 3D visualization, interaction, data and input/output management, abstraction of medical formats (DICOM, meshes…) — and around which each specialist plugs in their own domain **extension**, without touching the rest.

<div class="camitk-archi"><style>.camitk-archi{width:100%;margin:1.75rem 0;}.camitk-archi figure{width:100%;margin:0;}.camitk-archi img{width:100%;height:auto;max-width:100%;}</style>{{< figure src="camitk-architecture.svg" alt="CamiTK modular architecture: a shared core and discipline-specific extensions" caption="CamiTK's building-block architecture: a shared core, an interface layer, and one extension per domain of expertise." >}}</div>

This architectural choice (a C++/Qt/VTK core, following component-based software engineering) delivers what a company looks for in a technical foundation. And since version 5, CamiTK also accepts **Python extensions**: you can prototype an idea in a few lines, then harden it in C++ once validated — exactly the right trade-off between exploration speed and production robustness.

In practice, the foundation provides:

- **Cross-platform** — the same code runs on Linux, Windows and macOS.
- **Interoperability** — the building blocks of one project are reused in the next.
- **Default behaviors** — a specialist plugs in their algorithm and immediately gets a working application, without rewriting the interface.
- **Intellectual-property safeguards** — each module keeps its own license; the open-source core coexists with proprietary extensions (as was the case for the confidential LPR modules).
- **Durability** — the knowledge stays in the tool, not only in people's heads.

<!-- Screenshots of applications developed with CamiTK (segmentation, registration, robot guidance, etc.) -->
{{< figure src="camitk-capture-1.png" alt="Application prototyped with CamiTK" caption="Example of an application prototyped with CamiTK." >}}

## From software building block to method

CamiTK's most valuable contribution is not the code: it is what its practice taught us. By guiding real projects all the way to technology transfer — first among them the [LPR needle-insertion robot](/en/projects/lpr/) — we **generalized a methodology for maturing** software building blocks for medical devices, aligned with the TRL (*Technology Readiness Levels*) scale.

Concretely: knowing what maturity level a prototype sits at, what it takes to reach the next one, and where to invest validation and software-quality effort so you don't get stuck at the moment of industrial or clinical transfer. This is exactly the kind of course a company needs to hold when moving an idea from the lab to a product.

Over the projects, CamiTK thus became a **dual methodological tool**: to make disciplines collaborate, and to structure the climb up the TRL scale.

## Adoption as proof

A method is only worth as much as its ability to outlive its authors. CamiTK has passed that test: released as open source, **packaged in the official `debian-med` suite**, adopted by internal and national projects, and — the most telling proof — **still actively developed** more than fifteen years after it began (version 6.0, with new tools such as DevStudio to create an extension in minutes).

{{< figure src="camitk-timeline.svg" alt="Timeline of CamiTK adoption from 2008 to today" caption="A continuous adoption trajectory, from the lab to the open-source ecosystem." >}}

This project also gave me the chance to **coordinate and co-supervise a team of engineers** — up to four at once — over several years: hiring, organizing development, code review, documentation, and nurturing a community of users.

## What I take from it — and what I can bring

> **I founded and structured CamiTK; today, I use it daily as an expert.** This dual standpoint — the one who designed the architecture *and* the one who uses it — lets me bring to a company:
>
> - a **durable software architecture** designed for reuse and cross-platform support;
> - a **maturity-scaling (TRL) method** proven on real technology transfers;
> - the ability to make **very different profiles collaborate** (clinical, research, engineering, industry) around a single prototype;
> - fine-grained **intellectual-property management** in an ecosystem mixing open source and proprietary building blocks;
> - the **supervision of technical teams** over the long term.

## Publications

{{< pubs_by_tag tag="camitk" >}}

---

*CamiTK is the thread that runs through all my projects, from the [LPR needle-insertion robot](/en/projects/lpr/) to [medical image analysis](/en/projects/imageanalysis/): the conviction that a good medical prototype begins with good engineering — shared, and built to last.*
