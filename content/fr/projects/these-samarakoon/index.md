---
title: "Localiser automatiquement les organes dans le scanner"
subtitle: "Encadrement de thèse — le machine learning au service du geste assisté"
summary: "Co-encadrement de la thèse de Prasad Samarakoon (2016) : des forêts de régression plus légères et plus robustes pour localiser automatiquement les organes dans des images scanner, dans le cadre du LPR. Mon premier virage vers le machine learning."
date: 2016-09-30
lastmod: 2016-09-30
tags:
  - "ia-sante"
  - "machine-learning"
  - "regression-forest"
  - "pilotage-projets"
  - "analyse-images-medicales"

image:
  filename: featured.png
  caption: "Localisation automatique des reins dans un volume scanner, par boîtes englobantes"
  focal_point: Smart
---


*Mon premier virage vers le machine learning — pris, avec cet étudiant, deux ans avant l'explosion du deep learning.*

Dans le prolongement du projet [LPR](/fr/projects/lpr/), j'ai co-encadré avec Emmanuel Promayon la thèse de **Prasad Samarakoon**, soutenue le 30 septembre 2016 à l'Université Grenoble Alpes (financement ANR TecSan « Robacus »). C'est le projet qui m'a fait basculer vers le **machine learning** appliqué à l'image médicale. Nous avons commencé deux ans *avant* l'essor de la segmentation par deep learning : nous avons donc misé, non sur les réseaux de neurones profonds, mais sur les **forêts d'arbres décisionnels** (*random forests*) — un choix lucide pour l'époque, et formateur.

> Ce que cette thèse m'a vraiment apporté, ce n'est pas une méthode de plus : c'est une familiarité précoce avec les **forces et les limites** des approches par apprentissage — au premier rang desquelles leur étonnante robustesse.

## L'enjeu : localiser, pas segmenter

Pour planifier une ponction assistée par le robot LPR, il faut d'abord situer dans le scanner les organes cibles et ceux à éviter — une étape encore réalisée *à la main* par le clinicien, fastidieuse et coûteuse en temps d'expert. Plutôt que de viser d'emblée la segmentation complète (délimiter chaque contour), nous avons attaqué le problème plus abordable et tout aussi utile de la **localisation** : encadrer chaque organe par une boîte englobante, automatiquement.

## La contribution

Au-delà d'une analyse fine de la méthode, la thèse a produit deux apports à réelle portée pratique :

- les **Light Random Regression Forests** : un modèle plus rapide et bien plus économe en mémoire, à précision équivalente — donc plus facile à embarquer et à déployer ;
- une **paramétrisation automatique** qui supprime des réglages jusque-là fixés « à la main », rendant la méthode plus robuste et plus reproductible d'un jeu de données à l'autre.

{{< figure src="pipeline-rrf.png" caption="Le pipeline des forêts de régression : préparation des données, prétraitement, entraînement, puis prédiction (en jaune les données, en bleu les traitements)" >}}

## Robustesse — et biais : l'anecdote du rein fantôme

Une expérience reste, pour moi, l'illustration parfaite de ce que sont vraiment ces méthodes. Pour apprendre à localiser les reins, notre base d'entraînement — constituée de segmentations manuelles d'experts (nous-mêmes et les doctorants de l'équipe) — ne contenait que des patients **à deux reins**. En phase d'essai, le radiologue nous a soumis l'image d'un patient n'en ayant **qu'un seul**. L'algorithme a consciencieusement trouvé… **deux boîtes englobantes**, plaçant un « rein fantôme » là où la statistique l'attendait.

Nous étions, dès cette époque, sensibilisés à une vérité qui n'a rien perdu de son actualité : **un modèle n'est que le reflet des données qu'on lui montre.** La qualité et la représentativité du jeu d'apprentissage comptent autant que l'algorithme lui-même.

## Ce que ce projet a représenté

Avec l'essor du deep learning, cette stratégie de localisation par forêts a ensuite été mise de côté — mais elle aura été décisive. Elle m'a permis d'aborder le tournant du machine learning **par les fondations**, à un moment où l'on prenait encore le temps de comprendre *pourquoi* une méthode fonctionne, ce qu'elle garantit, et où elle se trompe. C'est ce regard — robustesse, généralisation, vigilance sur les données — que je mobilise aujourd'hui dans le prototypage d'applications médicales.

**Compétences mises en œuvre :** co-encadrement doctoral · machine learning appliqué à l'image médicale · conception de méthodes robustes et automatiques · constitution et critique de bases d'apprentissage.

## Publications liées

{{< pubs_by_tag tag="prasad" >}}
