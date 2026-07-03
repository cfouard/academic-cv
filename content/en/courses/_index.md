---
title: "Teaching: active pedagogy, designed as a methodology"
summary: "Twenty years designing learning systems that actually work: flipped classrooms, automated assessment tools, project-based learning — methods that translate directly into product design."
date: 2025-09-01
lastmod: 2025-09-01
tags:
  - "pédagogie inversée"
  - "apprentissage par projet"
  - "outils numériques pour l'enseignement"
  - "vulgarisation scientifique"
  - "enseignement supérieur"
image:
  filename: contrat-pedagogique-capture.png
  caption: "The APO course contract, as presented to students"
  focal_point: Smart
---

Twenty years designing learning systems that actually work — not just delivering lectures. Since joining the faculty in 2006, I have taught computer science from first-year undergraduate to master's level at UFR IM2AG, averaging 217 teaching-equivalent hours per year, with responsibility for several courses.

> This teaching practice was built over time, questioned and measured every year: an explicit course contract, automated assessment tools, project-based learning. The methods described here were formalised *alongside* my research activity — they are a natural extension of it.

One conviction runs through all of this: **learning content is only worth as much as a student can appropriate autonomously, with fast feedback on their own practice** — exactly what you'd ask of a good prototyping tool.

---

## The course contract: the flipped classroom in practice

> *FDD XML course (lead 2010–2017, then teaching assistant to support continuity of the teaching team) and APO — Object-Oriented Algorithms and Programming (lead since 2018)*
> L3 MIAGE, Université Grenoble Alpes

On the courses I took responsibility for, I flipped the classic model on its head: lectures no longer happen in the classroom. It's an explicit contract, formalised and communicated from the very first session.

{{< figure src="contrat-pedagogique-capture.png" caption="The APO course contract, as presented to students" >}}

### How it works

- **At home**: a hundred-page course booklet, written for self-study, to be read before each session
- **In CTD (supervised tutorials)**: a 10-minute *Quick* check followed by exercises — never a lecture recap
- **In TD (tutorials)**: paper-and-pencil deepening exercises, done in teams
- **In TP (labs)**: individual work in Java on Caseine
- **Grading**: 2/3 final exam, 1/3 continuous assessment (average of Quicks, written and machine-based midterms)

> This principle has taken on new weight each year with the rise of LLMs in student habits: since only genuine mastery counts at the exam, delegating a lab to generative AI brings no benefit — a reminder that has mattered more since 2023.

### Why this is a transferable skill

Designing a course contract is designing a specification: precisely defining what's expected at each stage, with what deliverables and what success criteria. It also means accepting to measure what works — and to redesign a course when it doesn't.

---

## Caseine: designing an assessment tool instead of enduring one

Rather than using a simple code skeleton to hand in, I contributed to [Caseine](https://caseine.org/), a Moodle instance enhanced with an automated code grader (VPL — Virtual Programming Lab). Each lab becomes a self-contained exercise that continuously evaluates compilation, execution and correctness, with individualised feedback.

{{< figure src="capture-caseine.png" caption="A Caseine/VPL lab: automated compilation, execution and grading, with instructions built in" >}}

### Context

I built several dozen of these labs, for cohorts of 40 to 95 students — a scale at which manual grading would become unmanageable. Each lab combines instructions, constraints (allowed/forbidden files, exam conditions) and real-time grade feedback.

### Skills involved

- Designing automated assessment tooling at scale
- Active contribution to a shared digital platform (Caseine, UGA's Moodle instance)
- Formalising objective, reproducible grading criteria

---

## From paper labs to interactive notebooks

In image processing, I evolved the lab format from a Java skeleton to complete, into Jupyter notebooks accessible directly from the course page.

{{< figure src="captureNotebookTim.png" caption="Excerpt from an image processing lab: histogram stretching across RGB channels" >}}

Students work with a real image, see the result immediately, and iterate — rather than filling in a code skeleton blind, with no intermediate visual feedback.

---

## Learning by doing: where teaching meets prototyping

> *GMCAO and TDM2i courses, co-created with Emmanuel Promayon — 5th-year TIS programme, Polytech Grenoble*
> *Integrative Applied Project — L3 MIAGE (launched in 2015)*

With Emmanuel Promayon, I co-designed the GMCAO and TDM2i courses (Technology for Smart and Innovative Medical Devices) for TIS engineering students, built entirely around project-based learning.

The logic mirrors that of a medical prototype climbing the TRL scale: state a clinical problem, iterate on a technical solution, confront it with a real need. That's also the spirit of the Integrative Applied Project I launched in L3 MIAGE in 2015, bringing together teachers and students from several courses (Networks, HCI, FDD, APO, Operations Research) around a shared project.

### Skills involved

- Designing curricula with progressive, staged complexity
- Coordinating a multidisciplinary teaching team
- Assessing deliverables under near-real conditions

---

## Making it accessible to non-technical audiences

Teaching algorithms and programming to students who didn't choose computer science (TIS and Géothec programmes at Polytech Grenoble) demands a precise skill: demystify, ground examples in their own field, never lose the pedagogical thread.

That's exactly the skill called on when working with clinicians or business teams on a medical prototyping project: translating a non-technical need into a workable specification, and back again.

---

## What this practice has taught me

Twenty years of teaching have taught me to design systems — not just content. A good course, like a good prototype, is defined by a clear contract, fast feedback on practice, and constant iteration on what isn't working.

Responsible for several courses, co-creator of two of them, active contributor to the Caseine platform: these teaching responsibilities have forged a method I now put to work in medical application prototyping.
