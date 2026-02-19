---
title: "Veille Scientifique Automatisée"
excerpt: "Outil Python modulaire permettant de collecter, résumer et structurer automatiquement une veille thématique à partir de flux RSS."
header:
    image:  /assets/images/veille-preview.jpg
    teaser: /assets/images/veille-illustration.jpg 
tags:
  - NLP
  - Automatisation
  - Pipeline de données
  - Web scraping
  - Génération de rapports
# sidebar : 
#   - title: "Role"
#     image: http://placehold.it/350x250
#     image_alt: "logo"
#     text: "Designer, Front-End Developer"
#   - title: "Responsibilities"
#     text: "Reuters try PR stupid commenters should isn't a business model"
read_time: true
---
{% include project-tags.html %}

## Aperçu

**Domaine :** NLP appliqué à la veille / automatisation de reporting  
**Type de projet :** Projet personnel  
**Objectif principal :** produire automatiquement une veille thématique à partir de sources hétérogènes (RSS, blogs, articles techniques)  
**Impact clé :** génération d’un rapport structuré (Markdown) avec résumés automatiques + envoi régulier (mail)  



## Stack & compétences clés

**Outils principaux :**  
Python · pandas · transformers · PyTorch · feedparser · requests · BeautifulSoup · Jinja2 · YAML · Markdown

**Compétences mobilisées :**  
- Conception d’un pipeline de collecte et traitement de données texte  
- Nettoyage, normalisation et déduplication (historique persistant)  
- Résumé automatique (modèle `transformers`)  
- Génération de rapports reproductibles (templating Jinja2)  
- Automatisation (cron / planificateur Windows / GitHub Actions)  
- Structuration d’un projet Python maintenable (config, logs, séparation des modules)  


## Contexte

Dans les domaines techniques et scientifiques, l’information évolue rapidement. Rester à jour demande du temps, une sélection rigoureuse des sources et une capacité à synthétiser des contenus hétérogènes.

Les outils de veille existants sont souvent rigides, peu personnalisables ou trop généralistes.  
Ce projet est né d’un besoin simple : disposer d’un système maîtrisé, flexible et automatisable pour produire une veille structurée, adaptée à des thématiques choisies.

## Objectif

Concevoir un outil capable de :

- collecter automatiquement des articles depuis différentes sources (RSS, blogs, sites spécialisés)  
- nettoyer et structurer les données  
- générer un résumé synthétique des contenus  
- produire un rapport formaté et prêt à être diffusé  
- automatiser l’envoi régulier de cette veille  

L’enjeu était de construire un pipeline simple, robuste et entièrement configurable.


## Exemple du rendu

![Exemple de rapport](/assets/images/apercu_veille_auto.png)


## Approche

Le projet repose sur une architecture modulaire organisée en plusieurs étapes :

1. **Collecte des sources**  
   Récupération de flux RSS et scraping lorsque nécessaire.

2. **Nettoyage & déduplication**  
   Structuration des données, gestion d’un historique local pour éviter les doublons.

3. **Résumé automatique**  
   Génération de synthèses à l’aide d’un modèle de la bibliothèque `transformers`.

4. **Génération du rapport**  
   Production d’un document Markdown à partir d’un template Jinja2.

5. **Automatisation**  
   Exécution planifiée (cron, planificateur Windows ou GitHub Actions).

L’ensemble est configurable via des fichiers YAML, ce qui permet d’adapter facilement les sources, la profondeur de recherche ou le format de sortie.



## Ce que montre ce projet

- Capacité à concevoir un pipeline complet (collecte → traitement → production d’un livrable)  
- Intégration d’un composant NLP dans un workflow opérationnel  
- Gestion d’un historique et prévention des doublons sur des données en flux  
- Génération automatisée de livrables reproductibles (format stable, templating)  
- Structuration propre d’un projet Python (config, logs, modules, exécution planifiée)  



## Limites et points d’attention

- La qualité du résumé dépend du contenu source et du modèle utilisé (textes très techniques ou très longs).  
- Les performances et la robustesse du scraping varient selon la structure des sites (risque de pages non parsables).  
- La quantification “qualité” d’un résumé reste en partie subjective : l’outil vise surtout la rapidité de lecture et la priorisation.



## Code source

Le projet complet, avec documentation détaillée et instructions d’installation, est disponible ici :

[Voir le repository](https://github.com/Apichevin/veille_automatique){: .btn .btn--info}  

