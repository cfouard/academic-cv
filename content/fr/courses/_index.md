---
title: "Enseignement : une pédagogie active, pensée comme une méthodologie"
summary: "Vingt ans à concevoir des dispositifs d'apprentissage qui fonctionnent : pédagogie inversée, outils d'évaluation automatisée, apprentissage par projet — des méthodes directement transposables à la conception de produits."
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
  caption: "Le contrat pédagogique APO, tel que présenté aux étudiant·e·s"
  focal_point: Smart
---

Vingt ans à concevoir des dispositifs d'apprentissage qui fonctionnent réellement — pas seulement à transmettre un cours. Depuis ma nomination en 2006, j'enseigne l'informatique du L1 au M2 à l'UFR IM2AG, en moyenne 217 heures équivalent TD par an, avec la responsabilité de plusieurs unités d'enseignement.

> Cette pratique pédagogique s'est construite dans la durée, remise en question et mesurée à chaque promotion : contrat pédagogique explicite, outils d'évaluation automatisée, apprentissage par projet. Les méthodes décrites ici ont été formalisées *en plus* de mon activité de recherche — elles en sont un prolongement naturel.

Une conviction commune traverse ces dispositifs : **un contenu pédagogique ne vaut que si l'étudiant·e peut se l'approprier de façon autonome, avec un retour rapide sur sa pratique** — exactement ce qu'on demande à un bon outil de prototypage.

---

## Le contrat pédagogique : la classe inversée en pratique

> *UE FDD XML (responsable 2010–2017, puis chargée de TP pour la continuité de l'équipe pédagogique) et APO — Algorithmique et Programmation Objet (responsable depuis 2018)*
> L3 MIAGE, Université Grenoble Alpes

Sur les UE dont j'ai pris la responsabilité, j'ai renversé le schéma classique : le cours magistral n'a plus lieu en classe. C'est un contrat explicite, formalisé et communiqué dès la première séance.

{{< figure src="contrat-pedagogique-capture.png" caption="Le contrat pédagogique APO, tel que présenté aux étudiant·e·s" >}}

### Comment ça fonctionne

- **À la maison** : un polycopié d'une centaine de pages, rédigé pour l'auto-apprentissage, à étudier avant chaque séance
- **En CTD** : un *Quick* de 10 minutes suivi d'exercices — jamais de rappel de cours
- **En TD** : des exercices d'approfondissement papier/crayon, en équipe
- **En TP** : un travail individuel en Java sur Caseine
- **Évaluation** : 2/3 examen terminal, 1/3 contrôle continu (moyenne des Quicks, partiels papier et machine)

> Ce principe est réaffirmé chaque année face à l'arrivée des LLM dans les usages étudiants : puisque seule la maîtrise réelle compte à l'examen, déléguer un TP à une IA générative n'apporte aucun bénéfice — un rappel qui a pris une importance nouvelle depuis 2023.

### Pourquoi c'est un savoir-faire transposable

Concevoir un contrat pédagogique, c'est concevoir un cahier des charges : définir precisément ce qui est attendu à chaque étape, avec quels livrables et quels critères de réussite. C'est aussi accepter de mesurer ce qui fonctionne — et de refondre un cours quand ce n'est pas le cas.

---

## Caseine : concevoir un outil d'évaluation plutôt que de le subir

Plutôt que d'utiliser un simple squelette de code à rendre, j'ai contribué à la plateforme [Caseine](https://caseine.org/), une instance Moodle enrichie d'un correcteur automatique de code (VPL — Virtual Programming Lab). Chaque TP devient un *lab* qui évalue en continu la compilation, l'exécution et la justesse du code produit, avec un retour individualisé.

{{< figure src="capture-caseine.png" caption="Un lab Caseine/VPL : compilation, exécution et notation automatiques, avec consignes intégrées" >}}

### Contexte

J'ai mis en place plusieurs dizaines de ces labs, pour des promotions de 40 à 95 étudiant·e·s — une échelle à laquelle une correction manuelle deviendrait ingérable. Chaque lab combine consignes, contraintes (fichiers autorisés/interdits, conditions d'examen) et retour de note en temps réel.

### Compétences mobilisées

- Conception d'un outil d'évaluation automatisée à grande échelle
- Contribution active à une plateforme numérique mutualisée (Caseine, instance Moodle de l'UGA)
- Formalisation de critères de correction objectifs et reproductibles

---

## Des TP papier aux notebooks interactifs

En traitement d'images, j'ai fait évoluer le format des travaux pratiques d'un squelette Java à compléter vers des notebooks Jupyter accessibles directement depuis la page du cours.

{{< figure src="captureNotebookTim.png" caption="Extrait d'un TP de traitement d'images : étalement d'histogramme sur les canaux RGB" >}}

Les étudiant·e·s manipulent une vraie image, visualisent le résultat immédiatement, et itèrent — plutôt que de remplir un squelette de code à l'aveugle sans retour visuel intermédiaire.

---

## Apprendre par projet : quand la pédagogie rejoint le prototypage

> *UE GMCAO et TDM2i, co-créées avec Emmanuel Promayon — 5ᵉ année TIS, Polytech Grenoble*
> *Projet Applicatif Intégrateur — L3 MIAGE (lancé en 2015)*

Avec Emmanuel Promayon, j'ai co-conçu les UE GMCAO et TDM2i (Technologie pour les Dispositifs Médicaux Intelligents et Innovants) pour les élèves-ingénieur·e·s TIS, entièrement construites en mode apprentissage par projet.

La logique est la même que celle d'un prototype médical qui monte en TRL : poser un problème clinique, itérer une solution technique, la confronter à un besoin réel. C'est aussi l'esprit du Projet Applicatif Intégrateur que j'ai lancé en L3 MIAGE en 2015, pour faire travailler ensemble les enseignant·e·s et les étudiant·e·s de plusieurs matières (Réseau, IHM, FDD, APO, RO) sur un projet commun.

### Compétences mobilisées

- Conception de cursus par montée en complexité progressive
- Coordination d'une équipe pédagogique pluridisciplinaire
- Évaluation de livrables en conditions proches du réel

---

## Vulgariser pour des publics non techniques

Enseigner l'algorithmique et la programmation à des étudiant·e·s qui n'ont pas choisi l'informatique (filières TIS et Géothec de Polytech Grenoble) demande une compétence précise : démystifier, prendre des exemples ancrés dans leur domaine, ne jamais perdre le fil pédagogique.

C'est exactement la compétence qu'on mobilise face à des cliniciens ou des équipes métier dans un projet de prototypage médical : traduire un besoin non technique en spécification exploitable, et inversement.

---

## Ce que cette pratique m'a appris

Vingt ans d'enseignement m'ont appris à concevoir des dispositifs — pas seulement des contenus. Un bon cours, comme un bon prototype, se définit par un contrat clair, un retour rapide sur la pratique, et une itération constante à partir de ce qui ne fonctionne pas.

Responsable de plusieurs UE, co-créatrice de deux d'entre elles, contributrice active de la plateforme Caseine : ces responsabilités pédagogiques ont forgé une méthode que je mets aujourd'hui au service du prototypage d'applications médicales.
