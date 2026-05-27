---
title: "Analyse automatisée de données de pièges photographiques"
excerpt: "Application web interactive pour le traitement et la visualisation de données issues de pièges photographiques : filtrage des détections, tableaux de bord dynamiques et export de graphiques."
header:
    image: /assets/images/cam-trap-preview.jpg
    teaser: /assets/images/cam-trap-teaser.png
layout: single
show_taxonomy: true
tags:
  - Analyse de données
  - Écologie numérique
  - Visualisation interactive
  - Piège photographique
  - Python
  - Streamlit
sidebar:

read_time: true
---
{% include project-tags.html %}

<div class="notice--warning">
  <h4>Projet en cours de développement</h4>
  <p>Cette application est actuellement en phase de développement actif. Les fonctionnalités présentées ci-dessous constituent le cœur fonctionnel de l'outil ; de nouveaux modules sont en cours d'intégration.</p>
</div>

<div class="notice">
  <h4>En bref</h4>
  <p><strong>Domaine :</strong> Data science appliquée à la biodiversité<br>
  <strong>Contexte :</strong> Suivi de la faune sauvage par piège photographique<br>
  <strong>Objectif principal :</strong> Faciliter l'analyse et la visualisation de données de détection pour les écologues<br>
  <strong>Statut :</strong> MVP fonctionnel – développement en cours</p>

  <p><strong>Outils principaux :</strong><br>
  Python · Streamlit · Polars · Plotly</p>

  <p><strong>Compétences mobilisées :</strong></p>
  <ul>
    <li>Développement d'application web de données</li>
    <li>Pipeline de traitement et filtrage de données temporelles</li>
    <li>Visualisation interactive</li>
    <li>Conception orientée utilisateur (écologues de terrain)</li>
  </ul>
</div>


## Contexte

Les pièges photographiques sont des outils incontournables dans le suivi de la faune sauvage. Couplés à des systèmes de détection automatique par intelligence artificielle — comme [DeepFaune](https://www.deepfaune.cnrs.fr/), développé par le CNRS — ils permettent de générer automatiquement des données d'identification d'espèces à grande échelle.

Ces systèmes produisent des fichiers CSV contenant l'ensemble des détections horodatées. Cependant, plusieurs difficultés rendent leur exploitation directe complexe pour les écologues :

- un même individu peut déclencher plusieurs fois le capteur en quelques minutes, générant des **détections redondantes** qui faussent les comptages,
- les données brutes nécessitent des **retraitements** avant toute analyse (nettoyage, extraction de variables temporelles, exclusion de catégories non pertinentes comme les détections humaines),
- la **visualisation** des patterns d'activité (par espèce, par heure, par période) requiert des outils adaptés à des non-spécialistes de la data.


## Objectif du projet

Ce projet vise à développer une application web simple d'utilisation, destinée aux écologues et gestionnaires d'espaces naturels, pour :

- importer et nettoyer des exports CSV issus de DeepFaune,
- filtrer automatiquement les détections redondantes selon un intervalle de temps paramétrable,
- visualiser les données sous forme de tableaux de bord interactifs,
- exporter les graphiques pour intégration dans des rapports.

L'objectif est de rendre l'analyse de données de pièges photographiques **accessible sans compétences en programmation**.


## Fonctionnalités développées

### Import et validation des données

L'utilisateur dépose son fichier CSV via une interface de glisser-déposer. L'application vérifie la présence des colonnes requises (`date`, `prediction`, `score`) et applique automatiquement le pipeline de traitement.

### Filtrage des détections indépendantes

Un algorithme de filtrage temporel élimine les détections multiples d'un même individu sur une fenêtre de temps configurable (par défaut : 5 minutes). Ce paramètre est ajustable directement depuis l'interface, permettant à l'utilisateur d'adapter le traitement à ses protocoles de terrain.

### Tableau de bord général

La vue d'ensemble présente :

- les indicateurs clés : nombre total de détections, nombre d'espèces identifiées, plage de dates couverte,
- un graphique en barres interactif de la distribution des espèces détectées.

### Activité horaire par espèce

Un second module permet de sélectionner une ou plusieurs espèces et de visualiser leur **profil d'activité sur 24 heures**, sous forme de courbes interactives. Ce type de visualisation est utile pour caractériser les comportements nocturnes ou crépusculaires.

### Export des graphiques

Chaque graphique Plotly intègre un bouton de téléchargement au format PNG, pour une intégration directe dans des rapports ou présentations.


## Architecture technique

| Composant | Technologie |
|-----------|-------------|
| Interface web | Streamlit |
| Traitement des données | Polars |
| Visualisation | Plotly |
| Configuration | TOML |
| Langage | Python 3.11+ |

L'application suit une architecture modulaire : le pipeline de traitement des données, la génération des graphiques et la configuration sont chacun isolés dans des modules dédiés, facilitant l'ajout de nouvelles fonctionnalités.


## Perspectives

- Ajout de visualisations complémentaires (activité mensuelle, carte de chaleur horaire × espèce, richesse spécifique dans le temps)
- Comparaison entre plusieurs sites ou campagnes de terrain
- Statistiques descriptives exportables (tableaux récapitulatifs par espèce)
- Compatibilité avec d'autres formats d'export (autres logiciels de détection)
- Déploiement en ligne pour un accès sans installation locale