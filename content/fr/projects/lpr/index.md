---
title: "Un robot léger de ponction pour la radiologie interventionnelle"
subtitle: "Du concept à l'évaluation : concevoir un robot compatible scanner et IRM, robuste et automatique"
summary: "Coordination et conception du LPR (Light Puncture Robot) : un robot de ponction léger, posé sur le patient, compatible à la fois avec le scanner X et l'IRM, capable de se recaler automatiquement dans l'image. Un projet mené du concept à l'évaluation, à l'interface recherche / clinique / industrie."
date: 2016-07-01
lastmod: 2026-06-10
tags:
  - "robotique-medicale"
  - "radiologie-interventionnelle"
  - "recalage"

image:
  filename: featured.png
  caption: "Le LPR : un robot de ponction léger, posé sur le patient, compatible scanner et IRM"
  focal_point: Smart
---

*Concevoir un robot de ponction compatible à la fois avec le scanner et l'IRM, capable de se recaler tout seul dans l'image — et le mener du concept jusqu'à l'évaluation clinique.*

## Le geste à assister

Insérer une aiguille sous contrôle d'imagerie est un acte de radiologie interventionnelle courant : pour une biopsie ou l'ablation d'une tumeur, le clinicien acquiert une image volumique, repère une trajectoire sur une coupe, puis insère l'aiguille. Le geste est délicat : au moment de l'insertion, le radiologue dispose de très peu d'outils de guidage et se fie surtout à son expérience et à la mémorisation de la coupe choisie. Sous scanner, vérifier la trajectoire impose des images de contrôle répétées — donc de l'irradiation, des allers-retours, et un inconfort pour le patient. Sous IRM, le geste devient presque impossible à réaliser à la main dans le tunnel.

## Le LPR en action

Le LPR (*Light Puncture Robot*) est un robot léger, posé directement sur le patient pour suivre au plus près ses mouvements. La vidéo ci-dessous le montre en situation, du recalage automatique dans l'image jusqu'au positionnement de l'aiguille :

{{< video src="lpr-demo.mp4" controls="yes" >}}

> Léger, posé sur le patient, compatible scanner **et** IRM, et capable de se recaler tout seul : un même système qui passe d'une modalité d'imagerie à l'autre sans réglage manuel. La généricité n'est pas un confort, c'est ce qui rend une technologie transférable d'un contexte clinique à un autre.

## Des résultats à la hauteur de l'enjeu

L'évaluation sur fantôme a confirmé une précision compatible avec l'usage clinique visé :

- sous **scanner** : erreur de ciblage de **3,3 ± 1,7 mm** et orientation de l'aiguille à **moins de 1°** ;
- sous **IRM** : ciblage à **moins de 5 mm** (limité par la résolution des images) et orientation à **moins de 2°**.

La précision clinique visée — moins de 5 mm — était atteinte dans les deux modalités.

## Piloter le robot à distance, en temps réel

En collaboration avec l'équipe du **LIRMM (Montpellier)**, partenaire de l'ANR Robacus, nous avons démontré la commande à distance du robot en temps réel, via une interface de téléopération à retour d'effort. Une étape vers un geste où le radiologue piloterait l'insertion depuis la salle de contrôle, sans s'exposer aux rayonnements.

<!-- Vidéo de téléopération (teleoperation-lirmm.mp4) à insérer ici une fois le montage terminé. -->
{{< video src="teleoperation-lirmm.mp4" controls="yes" >}}

## Un projet de coordination

Au-delà de la technique, ce projet a été une longue aventure de **coordination à l'interface recherche / clinique / industrie**. J'ai été coordinatrice du projet **ANR-11-TECS-020-01 Robacus**, qui réunissait deux laboratoires (TIMC et LIRMM), un CHU (le CHU Grenoble Alpes, via le CIC-IT et le service de radiologie) et une entreprise (Axe Systems, pour la fabrication du robot). J'ai également coordonné le projet Carnot LSI LPROP, encadré trois post-doctorants (Nabil Zemiti, Nikolaï Hungr, Baptiste Veron) et une dizaine de stagiaires de Master.

Le logiciel de contrôle a été bâti sur [CamiTK](/fr/projects/camitk/), l'atelier de prototypage d'applications médicales que je co-développe. Sa modularité a permis de réutiliser le code d'une version du prototype à l'autre — exactement le type de méthode qui fait gagner du temps en prototypage industriel.

> Réutiliser une brique logicielle d'un prototype à l'autre plutôt que tout réécrire : c'est ce qui transforme une démonstration de laboratoire en une technologie qui avance vite.

## Vers la clinique

Cette phase de recherche a posé les bases d'une étape bien plus exigeante : amener le robot jusqu'aux premiers essais sur l'humain. C'est l'objet de la page [Montée en TRL du LPR](/fr/projects/lpr-trl/) — refonte sous assurance qualité, analyse de risques, essais précliniques sur sujets sains et maturation industrielle.

**Compétences mobilisées :** coordination de projet multi-partenaire (recherche · clinique · industrie) · conception d'algorithmes robustes et automatiques · portage multi-modalité (scanner / IRM) · architecture logicielle modulaire et réutilisable pour le prototypage d'applications médicales.

## Publications associées

{{< pubs_by_tag tag="lpr" >}}

