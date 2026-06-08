---
title: "Des fondations mathématiques aux images médicales"
summary: "Postdoctorat à l'Université d'Uppsala (2005–2006) : extension des distances de chamfrein aux grilles anisotropes et preuve formelle de leurs propriétés métriques, avec une application directe aux images médicales volumiques."
date: 2006-08-01
lastmod: 2006-08-01
tags:
  - distances-de-chanfrein
image:
  filename: featured.png
  caption: "Grilles BCC et FCC — structures non standard pour l'imagerie médicale"
  focal_point: Smart
---

> Ce projet s'écarte délibérément du prototypage applicatif. Il témoigne d'une autre facette de ma démarche : la capacité à travailler à un niveau d'abstraction mathématique rigoureux, à produire des preuves formelles, et à publier dans des journaux de référence en mathématiques discrètes — tout en gardant en ligne de mire une application concrète en imagerie médicale.

Entre septembre 2005 et août 2006, j'ai effectué un postdoctorat au [Centre for Image Analysis](https://www.uu.se/en/centre/image-analysis) de l'Université d'Uppsala, en Suède — l'un des laboratoires fondateurs de la géométrie discrète appliquée à l'image. J'y ai eu l'opportunité de travailler aux côtés de [Gunilla Borgefors](https://en.wikipedia.org/wiki/Gunilla_Borgefors), pionnière du domaine, dont le papier de 1986 sur les transformées de distance dans les images numériques reste une référence incontournable citée par des milliers de chercheurs — y compris aujourd'hui dans le calcul des fonctions de perte pour les réseaux U-Net en segmentation par apprentissage profond.

---

## Le problème de départ : calculer des distances dans une image

Une **transformée de distance** est une opération fondamentale en traitement d'images : pour chaque pixel d'un objet, elle calcule sa distance au bord le plus proche. C'est un outil omniprésent — segmentation, squelettisation, recalage, calcul de fonctions de coût en apprentissage machine.

La distance euclidienne est la plus naturelle, mais elle pose deux problèmes pratiques :

- Elle est **continue**, donc coûteuse à calculer exactement sur une grille discrète.
- La distance euclidienne au **carré** (d²E), qui est discrète, ne vérifie pas l'inégalité triangulaire.

Ce dernier point mérite une illustration. L'inégalité triangulaire dit simplement que le chemin direct entre deux points ne peut jamais être plus long que de passer par un intermédiaire — c'est la propriété fondamentale de toute distance au sens mathématique.

{{< figure src="triangle_inequality.svg" caption="Exemple 2D : d²E(p,q) = 9 > d²E(p,o) + d²E(o,q) = 7. Passer par o revient moins cher que d'aller directement — le chemin le plus court n'est pas la ligne droite !" >}}

La **distance de chamfrein** résout ce problème : c'est une façon efficace de calculer des distances dans une image numérique sans avoir à examiner tous les chemins possibles. On affecte à chaque direction de déplacement (voisin 4-connexe, 8-connexe, etc.) un poids local, et on propage ces poids par un simple balayage en deux passes de l'image. Le résultat est une distance discrète, entière, rapide à calculer — et qui, sous certaines conditions sur les poids, vérifie toutes les propriétés d'une norme.

{{< figure src="chamfer_forward.png" caption="Algorithme de chamfrein — 1er passage : propagation de gauche à droite, de haut en bas" >}}

{{< figure src="chamfer_backward.png" caption="Algorithme de chamfrein — 2e passage : propagation de droite à gauche, de bas en haut" >}}

---

## Le problème spécifique : les images médicales sont anisotropes

Sur une grille **isotrope** (pixels carrés, voxels cubiques), les distances de chamfrein sont bien maîtrisées. Mais les images médicales sont rarement isotropes.

{{< figure src="anisotropic_medical.png" caption="Image médicale anisotrope : les voxels sont allongés dans la direction axiale" >}}

Un scanner CT typique a une résolution de 0,5 mm × 0,5 mm dans le plan axial, mais de 2 à 5 mm entre les coupes. Si l'on applique naïvement un algorithme de chamfrein calculé pour une grille isotrope à une telle image, les distances obtenues ne vérifient plus l'inégalité triangulaire — et peuvent mener à des absurdités géométriques où le chemin direct entre deux points semble plus long que de passer par un détour.

**La solution classique** est de rééchantillonner l'image pour la rendre isotrope avant de calculer les distances. Mais ce rééchantillonnage introduit des artefacts et alourdit considérablement le traitement.

---

## Ma contribution : une théorie unifiée pour les grilles quelconques

Mon travail de postdoctorat a consisté à développer un cadre mathématique général permettant de calculer des distances de chamfrein directement sur n'importe quelle grille — en particulier les grilles anisotropes des images médicales — avec la garantie formelle que la distance obtenue est bien une **norme** au sens mathématique (positive, symétrique, inégalité triangulaire, homogénéité).

La clé du résultat est la notion de **module** : en généralisant le cadre des grilles discrètes des entiers (Z²) à celui des modules sur les anneaux commutatifs, j'ai pu démontrer les conditions nécessaires et suffisantes sur les poids du masque de chamfrein pour garantir la propriété de norme — indépendamment de la géométrie de la grille.

Ce travail a abouti à trois contributions majeures :

### 1. Distances sur grilles générales — preuve de la norme

Le papier principal dans *Pattern Recognition* (2007) établit la théorie complète : définitions, propriétés (distance, métrique, norme), conditions sur l'algorithme de balayage séquentiel, et application aux grilles FCC (*face-centered cubic*) et BCC (*body-centered cubic*) — des structures cristallines qui présentent des propriétés d'échantillonnage optimales pour l'imagerie médicale 3D.

**Ma contribution** : j'étais autrice principale de ce papier. J'ai développé la généralisation aux modules, établi les conditions de validité de l'algorithme deux-passes sur des grilles quelconques, et calculé les poids optimaux pour les grilles FCC et BCC.

- **[Pattern Recognition 2007]** C. Fouard, R. Strand, G. Borgefors — *Weighted distance transforms generalized to modules and their computation on point lattices* — [lire](/fr/publication/2007-fouard-pr/)

### 2. Distances sur grilles non standard par séquences de voisinage

Une extension aux distances définies par séquences de voisinage (qui permettent une isotropie encore meilleure), avec preuve formelle des conditions pour que l'algorithme séquentiel produise des cartes de distances correctes sur les grilles carrée, cubique, FCC et BCC.

- **[DGCI 2006]** R. Strand, B. Nagy, C. Fouard, G. Borgefors — *Generating distance maps with neighbourhood sequences* — [lire](/fr/publication/2006-strand-dgci/)

### 3. Comparaison des transformées de distance sur niveaux de gris

Une étude comparative de deux définitions de distance sur images en niveaux de gris (GWDT et WDTOCS), avec analyse théorique et expérimentale de leurs comportements respectifs selon le type d'image (cartes de densité, cartes de hauteur).

- **[DGCI 2006]** C. Fouard, M. Gedda — *Distance transforms on curved spaces* — [lire](/fr/publication/2006-fouard-dgci/)

---

## Ce que ces travaux m'ont apporté

Ces douze mois à Uppsala m'ont appris à tenir deux postures simultanément : celle du mathématicien qui prouve, et celle de l'ingénieure qui cherche à résoudre un problème concret. La rigueur formelle n'est pas une fin en soi — elle est ce qui garantit qu'un algorithme se comportera correctement sur des données réelles, y compris dans les cas limites que l'on n'a pas anticipés.

L'impact indirect de ces travaux sur la pratique de l'imagerie médicale est réel : la plupart des outils de segmentation modernes, y compris les réseaux U-Net qui calculent leurs fonctions de perte à partir de cartes de distances, bénéficient de ces fondations théoriques. Je n'ai pas encore eu l'occasion d'appliquer directement ces distances anisotropes dans mes projets de recherche appliquée à Grenoble — mais c'est une piste que je garde en tête, notamment pour traiter les images médicales sans rééchantillonnage préalable.
