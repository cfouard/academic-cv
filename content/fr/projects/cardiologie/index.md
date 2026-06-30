---
title: Cardiologie interventionnelle
subtitle: "Du besoin clinique au prototype : guider le geste au cœur du bloc"
summary: "Guider le geste en cardiologie interventionnelle, depuis l'imagerie préopératoire jusqu'à la salle d'intervention. Un projet où une contrainte de données a été transformée en une innovation clinique mieux ciblée — de la thérapie cellulaire à la cartographie pour la biopsie endomyocardique."
tags:
  - cardiologie
  - "pilotage-projets"
  - "analyse-images-medicales"
  - "ia-sante"
  - "navigation-robotique"
image:
  filename: featured.png
  caption: "Guidage par l'image en cardiologie interventionnelle"
  focal_point: Smart
---

*Du besoin clinique au prototype : guider le geste au cœur du bloc.*

La cardiologie interventionnelle se pratique sous imagerie, mais le ou la clinicien·ne doit souvent agir sans voir directement la cible : la lésion à traiter ou à biopsier n'apparaît pas sur l'image temps réel de la salle. Mené avec le Pr Gilles Barone-Rochette (CHU Grenoble Alpes) et le laboratoire LTSI de Rennes, ce projet poursuit un seul objectif décliné en deux questions cliniques : **fournir au cardiologue un guidage fiable, construit à partir de l'imagerie préopératoire et utilisable directement au bloc.**

## Le fil rouge : rebondir quand les données manquent

Le projet a démarré sur le guidage de la **thérapie cellulaire**. Le premier essai clinique a recruté moins de patients que prévu : les données nécessaires à la suite n'étaient pas au rendez-vous. Plutôt que d'abandonner, nous avons **redéployé les briques techniques déjà construites** (segmentation d'images, navigation) vers un besoin clinique connexe, à la valeur plus immédiate et au verrou mieux identifié : la **biopsie endomyocardique**.

Ce pivot est, en soi, un livrable : il illustre une capacité à **dérisquer un projet, préserver les actifs développés et réorienter l'effort** vers là où la valeur clinique est la plus forte — exactement le type d'arbitrage qu'attend une entreprise face à un programme de R&D qui ne se déroule pas comme prévu.

## Sous-projet 1 — Guider la thérapie cellulaire post-infarctus

Après un infarctus, certaines thérapies consistent à réinjecter des cellules dans le myocarde. Tout l'enjeu est la **précision** : atteindre les bonnes zones, en s'appuyant sur des informations (l'étendue de la fibrose, les régions viables) qui ne sont visibles que sur l'imagerie préopératoire, pas sur l'image temps réel de la salle.

Notre approche : **fusionner l'imagerie multimodale** pour reporter, pendant l'intervention, les cibles repérées en préopératoire. La brique centrale est la **segmentation automatique du myocarde et de la fibrose en IRM de rehaussement tardif (IRM-LGE)**, développée par apprentissage profond dans le cadre de la thèse d'Erwan Lecesne (co-dirigée avec le LTSI de Rennes), puis intégrée dans [CamiTK](/fr/projects/camitk/) pour être présentée au clinicien en salle.

{{< figure src="injection-cellules.png" caption="Réinjecter les cellules au bon endroit : la précision du geste conditionne l'efficacité de la thérapie." >}}

CamiTK est un **atelier de prototypage** : il permet d'aller vite du concept au prototype évalué, mais son résultat n'a pas vocation à être un dispositif marqué CE. Cette brique constitue donc une **preuve de concept** ; son **transfert industriel est aujourd'hui en discussion** avec des partenaires du domaine.

## Sous-projet 2 — Une cartographie pour la biopsie endomyocardique

Trois pathologies — sarcoïdose cardiaque, myocardite chronique et cardiomyopathie arythmogène — peuvent présenter un **tableau clinique proche mais appellent des traitements opposés**. Pour trancher, il faut une biopsie… encore faut-il prélever **au bon endroit**.

<div style="display: flex; justify-content: center;">{{< figure src="ponction-endomyocardique.png" caption="La biopsie endomyocardique : prélever un échantillon de tissu cardiaque, là où se trouve la lésion." >}}</div>

L'état de l'art laisse un vrai manque :

- la biopsie « à l'aveugle » est peu spécifique, car la fibrose à cibler reste invisible pendant le geste ;
- le guidage électro-anatomique est long et, lui aussi, **aveugle à la fibrose**.

Notre solution agit comme un **« GPS » pour le cathéter de biopsie** : elle reporte la cible issue de l'imagerie préopératoire sur l'image temps réel, pour guider le prélèvement. Deux choix de conception en font une solution **pensée pour l'adoption** : elle est **indépendante du matériel** (compatible avec une salle existante) et fonctionne **en fluoroscopie temps réel, sans étape de fusion complexe**. Elle **réemploie directement** la brique de segmentation du premier sous-projet.

{{< figure src="systeme-biopsie.png" caption="Schéma du système de guidage proposé pour la biopsie endomyocardique (publié)." >}}

Statut actuel : nous **préparons les premiers essais cliniques au laboratoire** ; le transfert industriel viendra ensuite.

## Ce que ce projet démontre

- **Concevoir à partir d'un besoin clinique réel**, en dialogue étroit avec les praticiens, plutôt qu'autour d'une prouesse technique.
- **Maîtriser le traitement d'images médicales et l'IA** et les mettre au service d'une cible précise et utile.
- **Mener un prototype du laboratoire vers la clinique**, avec une conscience claire des étapes de maturité (TRL), du cadre des essais et du marquage CE.
- **Architecturer pour l'adoption** : indépendance vis-à-vis du matériel, intégration dans un atelier de prototypage, réemploi des briques.
- **Réorienter un projet pour en préserver la valeur** : agilité et dérisquage face à l'imprévu.
- **Piloter une collaboration multi-site** (Grenoble–Rennes) et co-encadrer une thèse de doctorat.

## Financements obtenus

| Financement | Montant | Objet |
| --- | --- | --- |
| Projet Famtastic (France Life Imaging) | 20 000 € | Amorçage de la collaboration avec le LTSI (Rennes) |
| PUI (UGA) | 60 000 € | Maturation du prototype vers les premiers essais cliniques |
| Thèse de doctorat (LabeX CAMI) | 170 000 € | Co-direction de la thèse d'Erwan Lecesne |
| Post-doctorat (LabeX CAMI) | 56 000 € | Une année d'ingénierie post-doctorale |
| **Total** | **306 000 €** | |

## Collaborations et encadrement

- **Pr Gilles Barone-Rochette** — cardiologue interventionnel, CHU Grenoble Alpes : partenaire clinique du projet.
- **Laboratoire LTSI (Rennes)** — Professeure Mireille Garreau et Antoine Simon (maître de conférences) : collaboration sur le traitement d'images cardiaques.
- **Thèse d'Erwan Lecesne** (2020–2024), co-dirigée à 50 % avec Mireille Garreau (LTSI) : traitement d'images multimodales pour améliorer la thérapie cellulaire post-infarctus.
- **Thèse de Théophile Tiffet** — interne en médecine : calibrage échographie / SPECT pour la cardiologie interventionnelle.

## Publications associées

{{< pubs_by_tag tag="cardiologie" >}}
