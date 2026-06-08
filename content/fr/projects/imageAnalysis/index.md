---
title: "Analyse d'images médicales"
summary: "Trois projets pionniers en vision par ordinateur et traitement d'images pour la chirurgie assistée : laparoscopie répartie, suivi osseux par ultrasons et curiethérapie de la prostate."
date: 2014-10-01
lastmod: 2014-10-01
tags:
  - "vision par ordinateur"
  - "échographie 3D"
  - "curiethérapie"
  - "laparoscopie"
  - "segmentation"
  - "CamiTK"
image:
  filename: featured.webp
  caption: "Implantation transpérinéale guidée par échographie — curiethérapie de la prostate"
  focal_point: Smart
---

À mon arrivée dans l'équipe [GMCAO](https://www.timc.fr/gmcao) du laboratoire TIMC en 2006, j'ai rejoint trois projets applicatifs portés par mes collègues, en apportant mon expertise en traitement et analyse d'images médicales. Ces collaborations m'ont permis de contribuer concrètement à des problématiques cliniques variées — de la vision chirurgicale en temps réel au calcul de dose en radiologie oncologique — tout en m'appropriant les outils et la culture de l'équipe.

> Ces trois projets s'inscrivent dans un travail académique rigoureux de production de connaissances : chaque contribution a donné lieu à des publications dans des journaux et conférences internationaux à comité de lecture, ou à un dépôt de brevet. Les compétences décrites ici ont été forgées *en plus* de cet effort de formalisation scientifique — elles en sont le produit direct.

Ces trois projets illustrent une conviction fondatrice de ma démarche : **une image médicale ne vaut que si elle est exploitable par le clinicien au bon moment et dans le bon contexte**.

---

## Curiethérapie de la prostate — Orientation des grains d'iode 125

> *Projet porté par Jocelyne Troccaz (TIMC-GMCAO)*  
> Co-encadrement du post-doctorant **Giao Nguyen** à 50 % avec Jocelyne Troccaz

{{< figure src="prostateBrachytherapy-context.webp" caption="Implantation transpérinéale guidée par échographie — contexte clinique" >}}

### Contexte

La curiethérapie prostatique consiste à implanter des grains radioactifs d'iode 125 directement dans la glande prostatique. Le calcul de la dose absorbée par le tissu tumoral — la **dosimétrie** — est crucial pour évaluer l'efficacité du traitement et anticiper les effets secondaires. Or, les outils de dosimétrie de l'époque modélisaient les grains comme des **sources ponctuelles isotropes**, négligeant leur orientation réelle dans le tissu.

La question posée : *l'orientation des grains influence-t-elle suffisamment la dosimétrie pour justifier sa prise en compte dans les logiciels cliniques ?*

### Contributions

Pour répondre à cette question, il fallait d'abord **détecter et localiser automatiquement les grains** dans les images scanner post-opératoires — une tâche difficile car les grains sont petits, proches les uns des autres et peuvent se chevaucher en projection.

{{< figure src="prostateBrachytherapy-02.png" caption="Grains implantés visibles dans une coupe CT : grains individuels, grains jointifs et os pelviens" >}}

Nous avons développé une méthode complète de :

- **Segmentation** des grains d'iode dans les images CT
- **Séparation** des grains qui se touchent ou se superposent
- **Estimation de la pose** (position + orientation 3D) de chaque grain

{{< figure src="prostateBrachytherapy-01.png" caption="Localisation 3D des grains de curiethérapie dans la prostate (visualisation CamiTK)" >}}

Les résultats ont permis de conclure que l'orientation des grains avait bien un **impact mesurable sur la dosimétrie** — une avancée cliniquement significative pour l'évaluation post-opératoire.

### Compétences mobilisées

- Traitement d'images 3D (scanner CT)
- Modélisation géométrique de sources radioactives
- Développement et intégration dans la plateforme **CamiTK** pour utilisation clinique
- Protocoles d'évaluation sur données réelles

### Publications associées

- **[IEEE TBME 2015]** H.-G. Nguyen, C. Fouard, J. Troccaz — *Segmentation, separation and pose estimation of prostate brachytherapy seeds in CT images* — [lire](/fr/publication/2014-nguyen-isbi/)
- **[Cancer/Radiothérapie 2014]** F. Meneu, H. Nguyen, C. Fouard et al. — *Impact de l'orientation des grains iode 125 dans l'évaluation de la dosimétrie à 1 mois* — [lire](/fr/publication/2014-meneu-cancer/)
- **[Physica Medica 2013]** F. Meneu, G. Nguyen et al. — *Consideration of seeds orientation in prostate brachytherapy and dosimetry analysis* — [lire](/fr/publication/2013-meneu-physicamedica/)

---

## Suivi de structures osseuses par échographie 3D

> *Co-direction à 50 % avec Jocelyne Troccaz*  
> Thèse de **Jonathan Schers** (2006–2009)

{{< figure src="us-bone-tracking-02.png" caption="Intervention orthopédique guidée par ultrasons : le contexte clinique" >}}

### Contexte

Les interventions orthopédiques — pose de prothèses, ostéotomies — nécessitent un **suivi en temps réel des structures osseuses** pendant l'opération. Les techniques classiques impliquent soit l'utilisation de rayons X (irradiation), soit la fixation de repères invasifs sur l'os (marqueurs osseux). L'objectif de ce projet était d'explorer une alternative **minimalement invasive** : le suivi par **ultrasons (échographie 3D)**.

### Contributions

Nous avons proposé une méthode de suivi per-opératoire basée sur le **recalage 3D/3D d'images échographiques** : à partir d'un volume de référence acquis en début d'intervention, on suit les déplacements de l'os en recalant chaque nouvelle acquisition sur ce volume.

{{< figure src="us-bone-tracking-03.png" caption="Segmentation de la surface osseuse dans une image échographique" >}}

Les principaux verrous scientifiques levés :

- Développement d'algorithmes de **segmentation des surfaces osseuses** dans les images échographiques (signal bruité, artefacts de réflexion)
- Méthode de **recalage déformable et rigide** adaptée à la modalité ultrasonore
- **Reconstruction panoramique** à partir de plusieurs acquisitions partielles
- Évaluation sur pièces anatomiques


### Compétences mobilisées

- Traitement du signal ultrasonore
- Recalage d'images médicales multimodales
- Mise au point d'une méthode de validation de recalage sans réalité terrain
- Co-encadrement doctoral (50 %)

### Publications associées

- **[IUS 1007]** J. Schers, J. Troccaz, V. Daanen, C. Fouard, C. Plaskos, P. Kilian - *3D/4D ultrasound registration of bone* - [read](/fr/publication/2007-schers-ius/)
- **[IJCARS 2009]** J. Schers, J. Troccaz, C. Fouard, C. Plaskos, O. Palombi — *3D/3D ultrasound registration for panoramic volume reconstruction* — [lire](/fr/publication/2009-schers-cars/)
- **[CAOS 2010]** J. Schers, C. Fouard, J. Troccaz — *Non invasive ultrasound-based bone tracking* — [lire](/fr/publication/2010-schers-caos/)

---

## Laparoscopie répartie — Vue étendue du champ opératoire

> *Co-direction à 50 % avec Philippe Cinquin*  
> Thèse de **Christophe Boschet** (2007–2010)

{{< figure src="distributive-laparoscopy-02.jpg" caption="Laparoscopie standard : une seule caméra, un champ de vision étroit" >}}

### Contexte

Lors d'une intervention laparoscopique, le chirurgien dispose d'un champ de vision **très limité** : sa caméra endoscopique, introduite par un trocart, ne voit qu'une zone restreinte de la cavité abdominale. Il est contraint de déplacer continuellement la caméra pour explorer le champ opératoire, ce qui nuit à sa concentration et augmente la durée de l'intervention.

L'idée : remplacer une unique caméra haute résolution par **plusieurs petites caméras miniatures** distribuées (du type de celles des téléphones portables de l'époque), et **reconstruire en temps réel une vue panoramique 3D** de la zone opérée.

{{< figure src="distributive-laparoscopy-01.jpg" caption="Laparoscopie standard : une seule caméra, un champ de vision étroit" >}}

### Contributions

Ce projet posait des défis inédits à la croisée de la vision par ordinateur et de l'informatique embarquée :

- **Étalonnage** de plusieurs caméras miniatures en configuration endoscopique
- **Reconstruction 3D** du champ opératoire par stéréovision répartie
- **Fusion des flux vidéos** pour produire une vue augmentée cohérente
- Intégration dans la plateforme CamiTK et prototypage pour expérimentation préclinique

{{< figure src="distributive-laparoscopy-03.jpg" caption="Reconstruction 3D du champ opératoire à partir de caméras multiples (CamiTK)" >}}

Ce projet est resté à l'état de prototype de recherche mais a donné lieu à une **protection industrielle** (brevet européen).

### Compétences mobilisées

- Vision par ordinateur stéréoscopique
- Calibration de systèmes optiques multi-caméras
- Intégration matérielle/logicielle
- Rédaction de brevet

### Productions associées

- **[Brevet EP 2016]** P. Cinquin, S. Voros, C. Boschet, C. Fouard, A. Moreau-Gaudry — *Imaging system for the three dimensional observation of an operation field* — [lire](/fr/publication/2008-cinquin-patent/)

---

## Ce que ces projets m'ont appris

Ces trois collaborations ont été pour moi **une école pratique du prototypage médical** — et bien davantage qu'une liste de compétences techniques.

J'y ai appris à travailler sur des données cliniques réelles, imparfaites, souvent sans réalité terrain disponible pour valider les algorithmes. J'y ai développé le réflexe de **concevoir des protocoles d'évaluation rigoureux** là où les benchmarks standards n'existaient pas, et d'**intégrer les contraintes du bloc opératoire** dès la phase de conception — contraintes de temps, de stérilité, d'ergonomie pour le chirurgien.

J'y ai aussi forgé ma manière de collaborer : apprendre à poser les bonnes questions aux cliniciens, à traduire un besoin médical en problème algorithmique, à livrer des outils intégrés dans une plateforme logicielle utilisable par des non-informaticiens.

Ces savoir-faire — construits *en parallèle* d'un travail soutenu de publication et de production scientifique formalisée — sont ceux que je mets aujourd'hui au service du prototypage d'applications médicales.
