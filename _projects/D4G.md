---
title: "Contribution au projet EurosForDocs – Transparence des liens d’intérêt en santé"
excerpt: "Participation à l’amélioration continue d’un projet open data de transparence des liens d’intérêts entre l’industrie pharmaceutique et les acteurs de santé, pour le rendre exploitable par citoyens, journalistes et chercheurs."
header:
    image: /assets/images/eurosfordocs-preview.webp
    teaser: /assets/images/eurosfordocs-preview.webp
tags:
  - SQL
  - Python
  - Open Data
  - Data Engineering
  - GitLab
read_time: true
---

{% include project-tags.html %}

## Aperçu

**Organisation :** Data For Good  
**Projet :** EurosForDocs  
**Domaine :** Open Data & transparence en santé  
**Objectif principal :** Améliorer la qualité et la structuration des données issues de la base Transparence-Santé  
**Statut :** Contribution bénévole en cours  


## Stack & compétences clés

**Outils principaux :**  
SQL · DuckDB · Python · pytest · Git · GitLab  

**Compétences mobilisées :**  
- Nettoyage et fiabilisation de données publiques volumineuses  
- Écriture et optimisation de requêtes SQL (CTE, jointures, filtrage conditionnel)  
- Intégration de transformations dans un pipeline Python existant  
- Conception et adaptation de tests unitaires  
- Travail collaboratif sur code versionné  


## Contexte

 [EurosForDocs](https://eurosfordocs.fr/)  est un projet associatif open source visant à rendre accessibles et exploitables les données publiques relatives aux liens d’intérêts entre l’industrie des produits de santé et les professionnels ou établissements de santé.

Les données sources sont volumineuses, hétérogènes et comportent de nombreuses incohérences.  
Le projet repose sur une chaîne de traitement structurée permettant :

- le nettoyage et l’harmonisation des identifiants,
- la réduction des doublons,
- la consolidation des informations,
- l’alimentation d’une plateforme publique d’exploration.


## Mon rôle

Je contribue à l’amélioration continue du pipeline de traitement des données, notamment sur :

- la fiabilisation des identifiants (SIREN, institutions),
- l’écriture et l’optimisation de requêtes SQL,
- l’intégration des règles de transformation dans le pipeline Python,
- la création et l’adaptation de tests unitaires,
- la collaboration via GitLab (branches, merge requests, revue de code).

Je participe également aux réunions techniques hebdomadaires avec l’équipe de contributeurs.



## Exemple d’intervention

Dans le cadre d’un ticket récent, j’ai développé une règle permettant d’identifier et supprimer les institutions dont les identifiants SIREN n’étaient pas présents dans la base de référence officielle.

Cette contribution a impliqué :

- écrire une requête SQL pour identifier et supprimer les entrées d’institutions avec des identifiants SIREN non valides     
- l’intégrer dans le pipeline Python d’agrégation des données   
- ajouter un test unitaire associé pour assurer la robustesse de cette transformation.    

## Apport personnel

Ce projet me permet d’évoluer dans un environnement proche des conditions professionnelles :

- travail sur une base de code existante,
- gestion de tickets,
- revue de code,
- amélioration progressive de la qualité des données,
- contribution à un projet à impact sociétal.

Je poursuis actuellement mon engagement au sein de l’équipe.