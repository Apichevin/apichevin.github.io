---
title: "Détection automatique de chiroptères par intelligence artificielle"
excerpt: "Pipeline multi-modèles : détection, comptage par densité et classification d’espèces à partir d’images réelles."
header:
    image: /assets/images/bat-preview.jpg
    teaser: /assets/images/bat-illustration.png
layout: single
show_taxonomy: true
tags:
  - Python
  - YOLO
  - PyTorch
  - Swin Transformer
sidebar : 
  - title: "Stack"
    #text: "python"
    #image: /assets/images/python-logo.png
    #image_alt: "logo"
    tag: 
        - python
        - YOLO
        - Pytorch
        - Swin Transformer
read_time: true
---


## Aperçu

**Domaine :** Computer Vision appliquée à la conservation  
**Structure d’accueil :** Air & D   
**Objectif principal :** Automatiser la détéction et l'identification de chiroptère 
**Impact clé :** F1-score global de 0,93 avec sélection adaptative


## Stack & compétences clés

**Outils principaux :**  
Python · PyTorch · YOLO · CSRNet · Swin Transformer · Scikit-learn  

**Compétences mobilisées :**  
- Conception d’architecture multi-modèles  
- Vision par ordinateur  
- Estimation par cartes de densité  
- Gestion du déséquilibre de classes  
- Évaluation statistique (MAE, RMSE, F1)

---

## Contexte écologique et réglementaire

Les chiroptères sont des espèces strictement protégées en France.  
Dans le cadre de projets d’aménagement (démolition, rénovation, infrastructures), la destruction d’un gîte occupé peut nécessiter la mise en œuvre de **mesures compensatoires**, conformément à la séquence ERC (Éviter – Réduire – Compenser).

Ces mesures consistent notamment à :

- installer des gîtes artificiels (nichoirs) pour permettre la relocalisation des individus,
- assurer un **suivi écologique régulier** des colonies,
- vérifier l’occupation effective des gîtes,
- estimer les effectifs,
- identifier les espèces présentes,
- évaluer l’efficacité des mesures dans le temps.

Ce suivi repose aujourd’hui en grande partie sur des comptages visuels et des interventions de terrain répétées, mobilisant du temps, des ressources et pouvant générer un dérangement des colonies.


## Objectif du projet

Ce projet, développé chez [Air & D](https://air-d.fr/) en collaboration avec un bureau d’études spécialisé dans les chiroptères, vise à automatiser une partie de ce suivi.

L’outil a pour finalité de :

- détecter automatiquement la présence d’individus dans des gîtes artificiels équipés de caméras,
- estimer les effectifs, y compris dans des colonies denses,
- classifier les individus au niveau spécifique,
- produire des indicateurs exploitables pour la validation des mesures compensatoires.

Il s’agit d’un **outil d’aide au suivi écologique**, destiné à compléter l’expertise naturaliste, en améliorant la traçabilité et l’homogénéité des estimations.

---

# Fonctionnement général du système

Les images collectées présentent une forte hétérogénéité :

- conditions d’éclairage variables,
- arrière-plans complexes (bois, pierre, béton),
- individus partiellement occultés,
- colonies de forte densité avec chevauchement,
- espèces morphologiquement proches.

Aucun modèle unique ne permet de traiter efficacement l’ensemble de ces situations.

Le système repose donc sur une **architecture multi-modèles adaptative**, combinant détection, estimation par densité et classification spécifique.


## 1. Détection et segmentation des individus

Un modèle de vision par ordinateur identifie et segmente les chiroptères présents sur l’image.

Performances (validation) :

- Précision : 93 %  
- F1-score : 0,87  

Ce module est particulièrement performant pour les images à faible ou moyenne densité (1 à 10 individus).


## 2. Estimation des effectifs en colonies denses

Lorsque la densité est élevée et que les individus se chevauchent, un second modèle basé sur des cartes de densité est activé.

Principe :  
chaque individu est représenté par une distribution gaussienne, et l’intégrale de la carte permet d’estimer le nombre total d’individus.

Performances (validation) :

- MAE : 3,68 individus  
- MAPE : 12,9 %  

Ce module corrige les sous-estimations observées dans les scènes à forte densité.


## 3. Classification spécifique

Un modèle de type Vision Transformer analyse les caractéristiques morphologiques fines (texture, forme des ailes, proportions) pour distinguer plusieurs espèces de chiroptères.

Performances globales :

- F1-score : 78,9 %  
- Performances élevées pour les espèces les plus représentées  

La gestion du déséquilibre interspécifique a été intégrée dans l’entraînement.

## 4. Sélection adaptative de la méthode de comptage

Un méta-modèle détermine automatiquement, pour chaque image, la méthode de comptage la plus pertinente (détection directe ou estimation par densité).

Comparaison :

| Méthode        | F1-score |
|---------------|----------|
| Seuil fixe     | 0,87     |
| Méta-modèle    | 0,93     |

Cette approche améliore la robustesse globale du système.


# Apports pour le suivi écologique

Cet outil permet :

- de réduire la fréquence des interventions terrain,
- de limiter le dérangement des colonies,
- d’homogénéiser les estimations d’effectifs,
- de renforcer la traçabilité des suivis,
- de faciliter l’évaluation de l’efficacité des mesures compensatoires.

L’automatisation partielle du suivi des chiroptères devient ainsi techniquement envisageable dans un cadre opérationnel.


# Détail technique

## Données

- 2 860 images collectées  
- 2 109 images annotées  
- 7 espèces cibles + catégorie « non identifiée »  
- Masques de segmentation annotés manuellement  



## Architecture

### Détection & segmentation  
YOLOv11 segmentation (transfer learning COCO)

### Estimation de densité  
CSRNet (cartes de densité, perte MAE + pixel-wise)

### Classification  
Swin Transformer V2 (recadrage via détection, suppression arrière-plan, Focal Loss)

### Méta-modèle  
Random Forest (sélection dynamique du meilleur estimateur)


## Perspectives

- Renforcement du jeu de données pour espèces rares  
- Intégration d’un module d’active learning avec validation naturaliste  
- Développement d’un tableau de bord opérationnel pour bureaux d’études  
- Génération automatisée de rapports compatibles avec les dossiers réglementaires ERC  


## Documentation scientifique

L’ensemble du projet est détaillé dans un article scientifique structuré (méthodologie, métriques, comparaisons de modèles).

[Consulter le manuscrit (PDF)](../../assets/pdf/Adaptive_Deep_Learning_for_Automated_Detection_Density_Estimation_and_Species_Identification_of_Bats.pdf){: .btn .btn--info}    




