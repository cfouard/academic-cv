---
title: "REMI — Aide à la décision pour la revascularisation endovasculaire des membres inférieurs"
summary: "Comment aider un·e chirurgien·ne vasculaire à choisir la meilleure stratégie de revascularisation, quand le succès d'une technique reste difficile à prédire ? Un projet clinique pluridisciplinaire qui transforme l'expérience accumulée en système d'aide à la décision interprétable — du recueil de données réelles jusqu'au logiciel déployé en service."
date: 2021-09-01
lastmod: 2026-06-10
tags:
  - remi
  - raisonnement-par-cas
  - aide-a-la-decision
  - chirurgie-vasculaire
  - apprentissage-automatique
image:
  filename: featured.png
  caption: "Le cycle du Raisonnement à Partir de Cas (RAPC) appliqué à la décision chirurgicale (fig. 2.5, thèse M. Roux)"
  focal_point: Center
---

*Comment aider un·e chirurgien·ne vasculaire à choisir la meilleure stratégie de revascularisation, alors que le succès d'une technique reste difficile à prédire ? REMI explore une réponse : apprendre des cas passés — comme le fait un clinicien expérimenté — mais de façon outillée, traçable et interprétable.*

## Le résultat, d'abord

**REMI** (*Revascularisation Endovasculaire des Membres Inférieurs*) est un projet d'aide à la décision clinique que je coordonne depuis 2021, en collaboration étroite avec le service de chirurgie vasculaire du CHU Grenoble Alpes. En quelques années, il a permis de :

- concevoir et **déployer en service** un logiciel de recueil de données centré utilisateur ;
- transformer des données cliniques réelles — incomplètes et hétérogènes — en une **base de cas** exploitable ;
- démontrer la pertinence du **raisonnement à partir de cas** pour proposer à un nouveau patient les stratégies ayant réussi chez des patients similaires ;
- mener à terme une thèse de doctorat (**Margaux Roux**, soutenue avec brio le 16 décembre 2025) et fédérer une équipe pluridisciplinaire financée par cinq financements successifs.

Ce projet a consisté, à partir d'un besoin clinique concret, à le traduire en spécifications, à lever les verrous techniques *et* organisationnels, et à aller jusqu'à un prototype réellement utilisé.

## Le problème clinique : une décision difficile à anticiper

L'**artériopathie oblitérante des membres inférieurs (AOMI)** est une maladie des artères des jambes dont les symptômes principaux sont la douleur et les plaies ischémiques. Pour éviter les complications graves — amputation, décès — la **revascularisation** vise à restaurer le flux sanguin, par voie endovasculaire (angioplastie, stenting) ou par chirurgie ouverte.

Le problème : la probabilité de succès ou d'échec d'une technique reste **difficile à prédire**. Le·la chirurgien·ne s'appuie sur des arbres de décision, des scores (WIfI) et surtout sur son expérience. À ce jour, aucun outil ne l'aide pleinement à choisir, pour *ce* patient, la stratégie la plus prometteuse.

{{< figure src="techniques-endovasculaires.png" caption="Techniques endovasculaires de revascularisation : angioplastie et stenting (fig. 1.9, thèse M. Roux)." >}}

## Une méthode : le raisonnement à partir de cas

Les systèmes d'aide à la décision clinique se répartissent classiquement en deux familles : les approches **statistiques**, performantes mais souvent peu interprétables (« boîtes noires »), et les approches à base de **règles expertes**, transparentes mais difficiles à faire évoluer.

REMI explore une voie intermédiaire : le **Raisonnement à Partir de Cas (RAPC)**, ou *Case-Based Reasoning*. Son hypothèse — *« des problèmes similaires ont des solutions similaires »* — se traduit, en clinique, par : *des symptômes similaires, traités par des thérapies similaires, conduisent à des résultats similaires*. C'est une méthode d'apprentissage proche du raisonnement médical lui-même, et naturellement plus **explicable** : chaque recommandation s'appuie sur des cas réels que l'on peut examiner.

Le cycle RAPC se décompose en quatre temps (illustrés en image de couverture) : **remémorer** des cas semblables, **réutiliser** et adapter leur solution, **réviser** le résultat, puis **retenir** le nouveau cas pour enrichir la base.

## De la donnée clinique brute à une base de cas exploitable

C'est souvent l'étape la plus sous-estimée — et la plus structurante. Les données disponibles dans les dossiers patients informatisés sont incomplètes, hétérogènes et pensées pour le soin, non pour l'analyse. Le projet a donc dû :

- **modéliser un « cas »** : un jeu d'attributs décrivant le problème (sévérité, score WIfI, anatomie des lésions, comorbidités) et un second décrivant la solution chirurgicale et son issue ;
- traiter explicitement les **données manquantes** et le typage des attributs ;
- combiner données **rétrospectives** et **prospectives**, puis développer un protocole d'extraction et d'agrégation en **Python** transformant des données patient-centrées en une base orientée « aide à la décision ».

{{< figure src="modele-donnees.png" caption="Diagramme de classes du modèle de données implémenté dans le logiciel de collecte (fig. 3.9, thèse M. Roux)." >}}

## Un logiciel prototype, centré utilisateur et déployé en service

Pour collecter des données prospectives de qualité, nous avons conçu un **logiciel prototype** directement utilisable par les cliniciens, dans leur flux de travail. Il calcule automatiquement le **score WIfI** (et donc le risque d'amputation), modélise une opération comme une séquence de gestes appliqués à des lésions, et génère automatiquement un **compte-rendu opératoire**.

C'est exactement le type de livrable qui m'intéresse : un outil pensé *avec* et *pour* ses utilisateurs, robuste assez pour quitter la paillasse et entrer dans la pratique. Le développement de cette application a justifié le recrutement d'un ingénieur de recherche dédié.

{{< figure src="logiciel-prototype.png" caption="Interface du logiciel prototype de recueil de données (fig. 3.11, thèse M. Roux)." >}}

{{< video src="demo-logiciel.mp4" controls="yes" >}}

*Vidéo de démonstration du logiciel, présentée lors de la première conférence du projet (en français).*

## Représenter les cas pour les comparer

Comparer deux patients suppose une bonne mesure de **similarité** entre cas. Le projet s'appuie sur un **auto-encodeur** : un réseau de neurones qui apprend à représenter chaque cas dans un espace latent compact, où la proximité géométrique reflète la similarité clinique. La remémoration des cas pertinents se fait alors dans cet espace.

{{< figure src="espace-latent.png" caption="Remémoration des cas similaires dans l'espace latent appris (fig. 4.4, thèse M. Roux)." >}}

## Conduite de projet et financements

Démarré en 2021 avec la Pre Rafaëlle Spear, le projet a réuni au fil du temps trois sites (TIMC à Grenoble, LTSI à Rennes, CHU Grenoble Alpes) et a été soutenu par **284 450 €** levés auprès de quatre sources de financement.

| Période | Projet / dispositif | Co-porteur·euse·s | Financement obtenu | Source | Montant |
|---|---|---|---|---|---|
| 2021–2022 | REMI-ORIA | Rafaëlle Spear | Matériel | EMERGENCE (laboratoire TIMC) | 12 000 € |
| 2022–2023 | *User-centered development for data collection in endovascular revascularization* | Rafaëlle Spear & Alexandre Demeure | 2 stagiaires de Master 2 (Laure Chatenet & Clément Gasse) | MIAI@Grenoble Alpes (ANR-19-P3IA-0003) | 11 200 € |
| 2024–2025 | *CAMI-assistant chair* | Sandrine Voros | 1 ingénieur de recherche pendant 1 an (Romaric Ruga) + matériel | MIAI@Grenoble Alpes (ANR-19-P3IA-0003) | 66 056 € |
| 2024–2026 | Aide à la décision — REMI | Rafaëlle Spear & Pascal Haigron | 1 doctorante (Margaux Roux) | LabeX CAMI | 160 000 € |
| 2026–2027 | Déploiement et validation clinique d'un outil d'IA | Rafaëlle Spear | Fin de thèse + 1 stagiaire + sous-traitance logicielle | Fondation pour l'Avenir | 35 194 € |
| | | | | **Total** | **284 450 €** |

## Encadrement et collaborations

- **Margaux Roux**, doctorante — thèse *« Aide à la décision pour la revascularisation endovasculaire des membres inférieurs »*, soutenue le 16 décembre 2025 (co-direction à 33 % avec R. Spear et P. Haigron).
- **Laure Chatenet** et **Clément Gasse**, stagiaires de Master 2.
- **Romaric Ruga**, ingénieur de recherche (finalisation du logiciel de recueil de données).
- **Pre Rafaëlle Spear** (PU-PH, chirurgie vasculaire, CHU Grenoble Alpes) — co-porteuse clinique depuis l'origine du projet.
- **Pr Pascal Haigron** (Université de Rennes, LTSI) — co-encadrant de la thèse.
- **Sandrine Voros** (TIMC) et **Alexandre Demeure** — co-porteurs de dispositifs de financement.

## Publications

{{< pubs_by_tag tag="remi" >}}

---

*Ce projet marque, avec la thèse de [Prasad Samarakoon](/fr/projects/these-samarakoon/), mon ancrage dans l'[IA appliquée à la santé](/fr/topic/ia-sante/) — avec une exigence constante : des méthodes interprétables, des outils réellement utilisables, et un dialogue permanent avec les cliniciens.*
