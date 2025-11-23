# 🧪 LAB 01 — Application Météo (Java / Maven / API REST)

Nous allons construire une application de meteo en console.

## 🎯 Objectif pédagogique

Ce laboratoire a pour but d’évaluer votre capacité à :
1. **Comprendre une spécification fonctionnelle**
2. **Analyser un besoin métier**
3. **Structurer un projet Maven**
4. **Consommer une API REST**
5. **Gérer les erreurs de manière professionnelle**
6. **Livrer un exécutable (JAR)**


## Compétences visées dans le LAB

Ce LAB cherche à développer et évaluer :

### 🧠 Compétences Techniques
- Compréhension d’une API REST
- Appels HTTP
- Lecture et parsing JSON
- Structure Maven 
- Gestion d’erreurs
- Production d’un JAR exécutable
- Organisation propre du code Java

### 🧩 Compétences Métiers
- Compréhension du besoin métier
- Lecture / analyse de spécification
- Rédaction claire (README + documentation)
- Capacité à travailler comme en entreprise
- Autonomie et investigation (Postman / documentation API)

---

## Prérequis indispensables pour suivre ce LAB

Pour réussir ce laboratoire, vous devez déjà posséder des bases solides en :

- **Java** (syntaxe, variables, types, boucles, conditions)
- **Programmation Orientée Objet (POO)** (classes, objets, encapsulation, héritage, polymorphisme)

Si ce n’est pas encore le cas, nous vous recommandons vivement de suivre des cours en ligne tels que :
- [Java sur OpenClassrooms](https://openclassrooms.com/fr/courses/6173501-apprenez-a-programmer-en-java)
- [Java sur Codecademy](https://www.codecademy.com/learn/learn-java)

Ces bases sont essentielles pour bien comprendre et réussir les consignes du laboratoire.

---
# 📋 Contexte & Mise en situation
Vous venez d'être recruté(e) comme développeur(se) Back-End Java au sein de MeteoCorp, une société spécialisée dans les solutions météorologiques.
L'équipe produit a identifié le besoin suivant : développer rapidement un prototype d'application console permettant de consulter les données météorologiques 
en temps réel. Cette application servira de preuve de concept (POC) pour valider l'intégration avec l'API [OpenWeatherMap](https://openweathermap.org) avant son déploiement dans des systèmes plus complexes.
## Contraintes techniques imposées par l'architecte :
1. Le projet doit être géré avec Maven pour assurer la standardisation avec les autres projets de l'entreprise
2. Utilisation obligatoire de l'archetype maven-archetype-quickstart
3. Bruno est l'outil imposé pour tester les API REST

### 🔧 Outils de test API - Bruno
Pourquoi Bruno et pas Postman ?
L'architecte de MeteoCorp a imposé Bruno comme client API pour les raisons suivantes :

🔒 Sécurité & Conformité
* Pas de compte cloud obligatoire : Bruno fonctionne 100% en local, vos clés API et données sensibles ne transitent jamais par des serveurs tiers
* Collections stockées localement : Contrairement à Postman qui synchronise par défaut dans le cloud, Bruno garde tout sur votre machine
* Open Source : Code source auditable, pas de télémétrie cachée
* Conforme RGPD : Aucune donnée n'est envoyée à l'extérieur de l'entreprise

💼 Avantages pour l'entreprise
* Gratuit et illimité : Pas de limitation sur le nombre de requêtes ou de collections
* Git-friendly : Les collections Bruno sont de simples fichiers texte versionnables
* Pas de licence : Économie sur les coûts de licence Postman Enterprise
* Collaboration sécurisée : Partage via Git plutôt que via cloud propriétaire

## 🎯 Objectif  du Lab
Développer une application Java en ligne de commande qui :

* Demande à l'utilisateur le nom d'une ville
* Récupère et affiche les informations météo actuelles via l'API OpenWeatherMap
* Gère les cas d'erreur de manière professionnelle
---

# 📘 Quelques Notion

Une **spécification fonctionnelle** décrit ce que doit faire l’application.  
Ce n’est pas du code : c’est une description de **fonctionnalités attendues**, d’objectifs et de comportements.

Dans un contexte entreprise, une spécification sert à :
- aligner le besoin du métier et le travail du développeur,
- clarifier ce qui doit être livré,
- éviter les malentendus.

---

### 🧩 Analyser un besoin métier

Le **besoin métier**, c’est *le problème réel* que le service ou l’utilisateur veut résoudre.  
Un développeur doit être capable de :
- comprendre la demande,
- clarifier la valeur produite,
- proposer une solution technique adaptée.

---

### 🧩 3. Structurer un projet Maven
Maven est un **outil de gestion de projet Java**.  
Il sert à :
- organiser les dossiers et packages du projet,
- gérer les dépendances,
- compiler le code,
- exécuter les tests,
- construire un JAR ou un WAR.

###  🚀 Maven Archetype
Un **archetype Maven** est un *modèle de projet déjà prêt*.  
Il crée :
- la structure de base,
- les dossiers nécessaires,
- un point d’entrée Java.

Vous devez partir d’un archetype pour suivre la bonne pratique entreprise.

####  🎯 Dans ce LAB vous devez
- initialiser le projet via un archetype,
- organiser vos dossiers proprement,
- mettre les bonnes dépendances,
- produire un JAR exécutable via Maven.

---

### 🧩 4. Consommer une API REST
Une **API REST** est un service web permettant d’obtenir des données via HTTP. 

Une API météo renvoie par exemple :
- la température,
- l’humidité,
- la description du climat,
- la localisation,
- etc.

### 📘 Format JSON
Les API REST renvoient souvent du JSON, un format facile à lire et représenter.

### 🧪 Pourquoi utiliser Postman ?
Postman sert à :
- tester une requête,
- valider les paramètres,
- inspecter la réponse,
- analyser les erreurs.

C’est un outil très utilisé par les développeurs pour **tester avant de coder**.

## 🎯 Dans ce LAB
Vous utiliserez **OpenWeatherMap** et testerez vos requêtes avec Postman avant de les intégrer dans votre application Java.

---

### 🧩 5. Gérer les erreurs
La gestion des erreurs consiste à anticiper :
- les entrées invalides,
- les problèmes réseau,
- les réponses d’erreur de l’API,
- les exceptions côté Java.

C’est une compétence clé en entreprise.
Exemples d’erreurs :
- ville inconnue,
- clé API incorrecte,
- API hors service,
- absence d’arguments.
- 
---

### 🧩 6. Livrer un exécutable JAR
Un **JAR** (Java ARchive) est un fichier contenant :
- votre code compilé,
- les ressources nécessaires,
- un point d’entrée (*main class*).

Ce fichier permet d’exécuter votre programme sans ouvrir l’IDE.
Exemple d’exécution :
```bash
java -jar meteo-app.jar Paris
```


