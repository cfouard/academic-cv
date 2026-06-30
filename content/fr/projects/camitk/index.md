---
title: "CamiTK : un atelier pour prototyper des applications médicales"
subtitle: "Du logiciel à la méthode — capitaliser le savoir-faire interdisciplinaire pour aller plus vite, du concept au prototype validé."
summary: "Co-fondatrice de CamiTK, un atelier open source de prototypage d'applications médicales. Une brique logicielle devenue méthodologie de montée en maturité (TRL), adoptée depuis plus de 15 ans — intégrée à Debian, toujours développée aujourd'hui (version 6.0)."
date: 2011-11-01
lastmod: 2026-06-19
tags:
  - camitk
  - prototypage
  - genie-logiciel
  - open-source
  - interdisciplinarite
image:
  filename: featured.png
  caption: "CamiTK — Computer Assisted Medical Intervention ToolKit"
  focal_point: "Center"
---

*Du logiciel à la méthode — capitaliser le savoir-faire interdisciplinaire pour aller plus vite, du concept au prototype validé.*

Concevoir une application pour le bloc opératoire, ce n'est jamais « juste du code ». C'est faire dialoguer des images médicales, des capteurs, des modèles biomécaniques, parfois un robot, et surtout des spécialistes qui ne parlent pas la même langue technique. **CamiTK** est l'outil que j'ai co-fondé avec Emmanuel Promayon **pour que ce dialogue produise des prototypes** — vite, proprement, et de façon réutilisable. C'est aussi le socle d'expertise sur lequel je m'appuie aujourd'hui pour accompagner des entreprises dans le prototypage d'applications médicales.

<div class="camitk-logo"><style>.camitk-logo{display:flex;justify-content:center;margin:1.75rem 0;}.camitk-logo img{max-width:240px;height:auto;}</style>{{< figure src="camitk-logo.png" alt="Logo CamiTK" >}}</div>

## Le problème : l'interdisciplinarité coûte cher

Dans le domaine des gestes médico-chirurgicaux assistés par ordinateur, chaque équipe arrive avec son monde : son système d'exploitation, son langage de prédilection, ses bibliothèques, ses habitudes — et son niveau de maturité, du prototype jetable au logiciel de qualité clinique. À chaque nouveau projet, la tentation est de tout réécrire. On réinvente la roue, on perd des mois, et le savoir-faire repart avec la personne qui quitte l'équipe.

Pour une entreprise, c'est exactement le point de douleur : *comment éviter de repartir de zéro à chaque innovation, tout en gardant la rigueur exigée par le médical ?*

## La réponse : un socle logiciel commun

Avec Emmanuel Promayon, nous avons conçu CamiTK comme un **atelier modulaire** : un cœur stable qui prend en charge ce qui est commun à tous les projets — visualisation 3D, interaction, gestion des données et des entrées/sorties, abstraction des formats médicaux (DICOM, maillages…) — et autour duquel chaque spécialiste vient brancher son **extension** métier, sans toucher au reste.

<div class="camitk-archi"><style>.camitk-archi{width:100%;margin:1.75rem 0;}.camitk-archi figure{width:100%;margin:0;}.camitk-archi img{width:100%;height:auto;max-width:100%;}</style>{{< figure src="camitk-architecture.svg" alt="Architecture modulaire de CamiTK : un cœur commun et des extensions par discipline" caption="L'architecture en briques de CamiTK : un cœur commun, une couche d'interfaçage, et une extension par expertise métier." >}}</div>

Ce choix d'architecture (un cœur en C++/Qt/VTK, suivant une ingénierie logicielle par composants) apporte ce qu'une entreprise recherche dans un socle technique. Et depuis la version 5, CamiTK accepte aussi des **extensions en Python** : on peut prototyper une idée en quelques lignes, puis la consolider en C++ une fois validée — exactement le bon compromis entre rapidité d'exploration et robustesse de production.

Concrètement, le socle apporte :

- **Multiplateforme** — le même code tourne sous Linux, Windows et macOS.
- **Interopérabilité** — les briques d'un projet se réutilisent dans le suivant.
- **Comportements par défaut** — un·e spécialiste branche son algorithme et obtient immédiatement une application fonctionnelle, sans réécrire l'interface.
- **Garantie de la propriété intellectuelle** — chaque module garde sa propre licence ; l'open source du cœur coexiste avec des extensions propriétaires (ce fut le cas des modules confidentiels du LPR).
- **Pérennité** — la connaissance reste dans l'outil, pas seulement dans les têtes.

<!-- Captures d'écran d'applications développées sous CamiTK (segmentation, recalage, guidage robot, etc.) -->
{{< figure src="camitk-capture-1.png" alt="Application prototypée sous CamiTK" caption="Exemple d'application prototypée sous CamiTK." >}}

## De la brique logicielle à la méthode

L'apport le plus précieux de CamiTK n'est pas le code : c'est ce que sa pratique nous a appris. En accompagnant des projets réels jusqu'au transfert technologique — au premier rang desquels le [robot de ponction LPR](/fr/projects/lpr/) — nous avons **généralisé une méthodologie de montée en maturité** des briques logicielles pour les dispositifs médicaux, calée sur l'échelle des TRL (*Technology Readiness Levels*).

Concrètement : savoir à quel niveau de maturité se situe un prototype, ce qu'il faut faire pour passer au suivant, et où placer l'effort de validation et de qualité logicielle pour ne pas se retrouver bloqué·e au moment du transfert industriel ou clinique. C'est précisément le type de cap qu'une entreprise a besoin de tenir quand elle fait passer une idée du laboratoire au produit.

CamiTK est ainsi devenu, au fil des projets, un **double outil méthodologique** : pour faire collaborer des disciplines, et pour structurer la montée en TRL.

## L'adoption comme preuve

Une méthode ne vaut que si elle survit à ses auteur·rices. CamiTK a franchi cette épreuve : diffusé en open source, **intégré au paquet officiel `debian-med`**, adopté par des projets internes et nationaux, et — preuve la plus parlante — **toujours développé activement** plus de quinze ans après ses débuts (version 6.0, avec de nouveaux outils comme DevStudio pour créer une extension en quelques minutes).

{{< figure src="camitk-timeline.svg" alt="Frise chronologique de l'adoption de CamiTK de 2008 à aujourd'hui" caption="Une trajectoire d'adoption continue, du laboratoire à l'écosystème open source." >}}

Ce projet m'a aussi donné l'occasion de **coordonner et coencadrer une équipe d'ingénieur·es** — jusqu'à quatre simultanément — sur plusieurs années : recrutement, organisation du développement, revue de code, documentation, animation d'une communauté d'utilisateur·rices.

## Ce que j'en retire — et ce que je peux apporter

> **J'ai fondé et structuré CamiTK ; aujourd'hui, je l'utilise au quotidien comme experte.** Cette double position — celle qui a conçu l'architecture *et* celle qui s'en sert — me permet d'apporter à une entreprise :
>
> - une **architecture logicielle durable** pensée pour la réutilisation et le multiplateforme ;
> - une **méthode de montée en maturité (TRL)** éprouvée sur de vrais transferts technologiques ;
> - la capacité à faire **collaborer des profils très différents** (clinique, recherche, ingénierie, industrie) autour d'un même prototype ;
> - une gestion fine de la **propriété intellectuelle** dans un écosystème mêlant open source et briques propriétaires ;
> - l'**encadrement d'équipes techniques** dans la durée.

## Publications

{{< pubs_by_tag tag="camitk" >}}

---

*CamiTK est le fil rouge qui relie tous mes projets, du [robot de ponction LPR](/fr/projects/lpr/) à l'[analyse d'images médicales](/fr/projects/imageanalysis/) : la conviction qu'un bon prototype médical naît d'abord d'une bonne ingénierie, partagée et faite pour durer.*
