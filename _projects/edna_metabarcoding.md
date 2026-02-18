---
title: "Détection et quantification de poissons marins par ADN environnemental (ADNe)"
excerpt: "Analyse de données eDNA pour évaluer la capacité du metabarcoding à détecter et quantifier des assemblages de poissons marins."
header:
    image: /assets/images/edna-illustration.jpg
    teaser: /assets/images/edna-preview.jpg
sidebar : 
  - title: "Role"
    image: http://placehold.it/350x250
    image_alt: "logo"
    text: "Designer, Front-End Developer"
  - title: "Responsibilities"
    text: "Reuters try PR stupid commenters should isn't a business model"
read_time: true
---


## Aperçu

**Domaine :** Écologie moléculaire & analyse quantitative  
**Structure d’accueil :** INRAE x IFREMER   
**Objectif principal :** Évaluer la capacité de l’ADNe à détecter et quantifier des poissons marins  
**Impact clé :** 66 % des genres détectés en milieu semi-contrôlé



## Stack & compétences clés

**Outils principaux :**  
R · Python · Bash · Illumina sequencing  

**Compétences mobilisées :**  
- Pipeline bioinformatique reproductible  
- Modélisation statistique (GLMM, AIC)  
- Analyse de données écologiques  
- Identification et analyse de biais méthodologiques  



## Contexte scientifique

Ce projet a été réalisé à l’INRAE, au sein de l’UMR DECOD (INRAE – IFREMER – Institut Agro Rennes-Angers), dont les travaux portent sur la dynamique et la durabilité des écosystèmes aquatiques, du continuum terre-mer jusqu’à l’océan.

L’unité développe notamment des outils permettant :

- d’évaluer l’état de la biodiversité aquatique,
- d’anticiper les impacts des pressions anthropiques,
- d’appuyer les politiques publiques nationales et européennes.

Dans ce contexte, l’ADN environnemental (ADNe) constitue un outil émergent pour le suivi non invasif des communautés de poissons.



## Enjeu écologique

Le suivi des communautés de poissons marins repose historiquement sur :

- des campagnes de pêche scientifique,
- des observations visuelles,
- des méthodes invasives ou coûteuses.

L’ADNe permet de détecter des espèces à partir de traces génétiques présentes dans l’eau, sans capture ni perturbation directe.

Cependant, plusieurs questions demeurent :

- La détection est-elle exhaustive ?
- Quels facteurs influencent la probabilité de détection ?
- Peut-on relier le signal génétique à l’abondance réelle ?
- Quels biais méthodologiques limitent l’interprétation ?



## Objectifs du projet

Deux axes principaux :

1. Évaluer la capacité de l’ADNe à détecter des espèces de poissons marins dans un milieu semi-contrôlé (grand aquarium public, communautés connues).
2. Tester de manière exploratoire une méthode alternative d’extraction et d’amplification visant à améliorer la quantification.



# Résultats principaux

### Détection des espèces

L’analyse montre que :

- 47 % des espèces présentes ont été détectées,
- 66 % des genres ont été détectés 

Les taux de détection varient selon :

- la rareté des espèces,
- leur biomasse,
- leur taille,
- leur appartenance taxonomique.

Les espèces rares et de faible biomasse sont moins détectées, ce qui confirme des tendances observées dans la littérature.



### Facteurs influençant la détection

L’analyse statistique met en évidence l’influence de :

- facteurs biologiques (biomasse, taille),
- biais d’amplification liés aux amorces utilisées (MiFish-U),
- limites des bases de données de référence (fragment mitochondrial 12S),
- biais PCR pouvant empêcher l’amplification de certaines lignées 

Certaines espèces présentes dans les aquariums n’ont pas été détectées malgré leur présence dans les bases de référence, illustrant les limites actuelles du métabarcoding.



### Quantification

La relation entre quantité d’ADN détectée et abondance réelle s’est révélée complexe.

La méthode expérimentale testée pour améliorer la quantification n’a pas apporté les gains attendus, soulignant les limites actuelles de l’ADNe pour estimer précisément les effectifs.



# Apports du projet

Ce travail m’a permis de :

- analyser de manière critique un outil émergent de suivi écologique,
- identifier les limites méthodologiques d’un dispositif moléculaire,
- relier processus écologiques et signaux génétiques,
- produire une interprétation scientifique nuancée des résultats.

L’ADNe apparaît comme un outil puissant pour la détection de la biodiversité, mais dont l’usage nécessite une compréhension fine des biais techniques et biologiques.



# Détail méthodologique et compétences mobilisées

## Pipeline bioinformatique

- Traitement de séquences issues de séquençage haut débit (Illumina)
- Nettoyage et filtrage qualité
- Attribution taxonomique
- Construction de matrices de présence/absence
- Chaînage reproductible via Bash / Python / R

## Analyses statistiques

- Modèles linéaires généralisés mixtes (GLMM)
- Sélection de modèle par AIC
- Analyse des effets fixes et aléatoires 
- Corrélations et régressions
- Analyses multivariées

## Compétences développées

- Bioinformatique appliquée à l’écologie
- Analyse de données environnementales complexes
- Modélisation statistique avancée
- Interprétation écologique de signaux moléculaires
- Esprit critique vis-à-vis des biais expérimentaux


# Perspectives

Les travaux sur l’ADNe constituent un levier majeur pour :

- le suivi non invasif de la biodiversité aquatique,
- l’amélioration des indicateurs d’état écologique,
- le développement d’outils d’aide à la décision pour la gestion des milieux aquatiques.

Ce projet s’inscrit dans la continuité de mon parcours : mobiliser des outils quantitatifs et technologiques au service de la compréhension et de la conservation du vivant.

