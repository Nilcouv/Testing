# Notes CTAL-TAE - Test Automation Engineering

## 0.4 Objectifs métier

Cette section énumère les objectifs métier attendus d'un candidat ayant obtenu la certification en Automatisation des tests - Ingénierie.

### **Compétences acquises après certification**

Un candidat ayant obtenu la certification en Automatisation des tests peut :

| Code | Objectif métier |
|------|-----------------|
| **TAE-B01** | Décrire l'objectif de l'Automatisation des tests |
| **TAE-B02** | Comprendre l'Automatisation des tests à travers le cycle de vie du développement logiciel |
| **TAE-B03** | Comprendre la configuration d'une infrastructure pour permettre l'Automatisation des tests |
| **TAE-B04** | Apprendre le processus d'évaluation pour sélectionner les bons outils et les bonnes stratégies |
| **TAE-B05** | Comprendre les préceptes de conception pour concevoir des solutions d'Automatisation des tests modulaires et évolutives |
| **TAE-B06** | Choisir une approche, y compris un pilote, pour planifier le déploiement de l'Automatisation des tests dans le cycle de vie du développement logiciel |
| **TAE-B07** | Concevoir et développer des solutions d'Automatisation des tests (nouvelles ou modifiées) qui répondent aux besoins techniques |
| **TAE-B08** | Considérer le périmètre et l'approche de l'Automatisation des tests et de la maintenance des testware |
| **TAE-B09** | Comprendre comment les tests automatisés s'intègrent dans les pipelines CI/CD |
| **TAE-B10** | Comprendre comment collecter, analyser et faire des rapports sur les données d'Automatisation des tests afin d'informer les parties prenantes |
| **TAE-B11** | Vérifier l'infrastructure d'Automatisation des tests |
| **TAE-B12** | Définir les opportunités d'amélioration continue pour l'Automatisation des tests |

### **Domaines de compétences clés**

- **Fondamentaux** : Objectifs et intégration dans le SDLC (TAE-B01, TAE-B02)
- **Infrastructure** : Configuration et vérification (TAE-B03, TAE-B11)
- **Stratégie** : Évaluation d'outils et approches (TAE-B04, TAE-B06)
- **Conception** : Solutions modulaires et évolutives (TAE-B05, TAE-B07)
- **Maintenance** : Périmètre et testware (TAE-B08)
- **Intégration** : Pipelines CI/CD (TAE-B09)
- **Reporting** : Collecte et analyse de données (TAE-B10)
- **Amélioration** : Processus d'amélioration continue (TAE-B12)

## 0.5 Objectifs d'apprentissage examinables et niveau cognitif

Les objectifs d'apprentissage soutiennent les objectifs métier et sont utilisés pour créer les examens de Testeur certifié Automatisation des tests - Ingénierie.

### **Niveaux cognitifs**

En général, tous les contenus de ce syllabus sont examinables aux niveaux K2, K3 et K4, à l'exception de l'Introduction et des Annexes.

- **K2 : Comprendre** - Reconnaître, mémoriser ou rappeler un concept
- **K3 : Appliquer** - Utiliser une procédure dans une situation donnée
- **K4 : Analyser** - Décomposer en éléments constitutifs et déterminer les relations

### **Mots-clés**

Tous les termes listés comme mots-clés sous les titres de chapitres doivent être retenus, même s'ils ne sont pas explicitement mentionnés dans les objectifs d'apprentissage.

## 0.11 Organisation du syllabus

Il y a huit chapitres dont le contenu peut faire l'objet d'un examen. Le syllabus exige un minimum de **21 heures d'enseignement**.

### **Tableau des chapitres et compétences**

| Chapitre | Titre | Durée | Niveau | Compétences visées |
|----------|-------|-------|--------|-------------------|
| **1** | Introduction et objectifs | 45 min | K2 | Avantages/limites, intégration SDLC, sélection d'outils |
| **2** | Se préparer à l'Automatisation | 180 min | K4 | Configuration infrastructure, évaluation SUT, recommandations techniques |
| **3** | Architecture d'Automatisation | 210 min | K3 | Conception gTAA, frameworks en couches, principes et patterns |
| **4** | Implémentation | 150 min | K4 | Déploiement pilote, gestion des risques, maintenabilité |
| **5** | Stratégies d'implémentation | 90 min | K3 | Intégration CI/CD, gestion configuration, dépendances API |
| **6** | Reporting et métriques | 150 min | K4 | Collecte de données, analyse des résultats, rapports d'avancement |
| **7** | Vérification de la solution | 135 min | K3 | Vérification environnement, comportement scripts, analyse statique |
| **8** | Amélioration continue | 210 min | K4 | Opportunités d'amélioration, recommandations, restructuration testware |

## Chapitre 1 : Introduction et objectifs de l'Automatisation des tests (45 minutes - K2)

### **Mots-clés**
- système sous test
- Automatisation des tests  
- ingénieur en Automatisation des tests

### **Objectifs d'apprentissage**

#### 1.1 Objectif de l'Automatisation des tests
- **TAE-1.1.1 (K2)** : Expliquer les avantages et les inconvénients de l'Automatisation des tests

#### 1.2 L'Automatisation des tests dans le cycle de vie du développement logiciel
- **TAE-1.2.1 (K2)** : Expliquer comment l'Automatisation des tests est appliquée dans les différents modèles de cycle de vie du développement logiciel
- **TAE-1.2.2 (K2)** : Sélectionner les outils d'Automatisation des tests appropriés pour un système sous test donné

## Chapitre 2 : Se préparer à l'Automatisation des tests (180 minutes - K4)

### **Mots-clés**
- Tests d'API
- tests de l'interface graphique
- testabilité

### **Objectifs d'apprentissage**

#### 2.1 Comprendre la configuration d'une infrastructure permettant l'Automatisation des tests
- **TAE-2.1.1 (K2)** : Décrire les besoins de configuration d'une infrastructure permettant l'implémentation de l'Automatisation des tests
- **TAE-2.1.2 (K2)** : Expliquer comment l'Automatisation des tests est exploitée dans différents environnements

#### 2.2 Processus d'évaluation pour sélectionner les bons outils et les bonnes stratégies
- **TAE-2.2.1 (K4)** : Analyser un système sous test pour déterminer la solution d'Automatisation des tests appropriée
- **TAE-2.2.2 (K4)** : Illustrer les constatations techniques d'une évaluation d'outil

## Chapitre 3 : Architecture d'Automatisation des tests (210 minutes - K3)

### **Mots-clés**
- développement piloté par les comportements
- capture/rejeux
- tests génériques d'Automatisation des tests
- architecture d'Automatisation des tests
- tests pilotés par les mots-clés
- scripting linéaire
- tests basés sur des modèles
- scripting structuré
- couche d'adaptation des tests
- harnais de tests
- test piloté par les données
- étape de test
- solution d'Automatisation des tests
- développement piloté par les tests
- script de test

### **Objectifs d'apprentissage**

#### 3.1 Concepts de conception utilisés dans l'Automatisation des tests
- **TAE-3.1.1 (K2)** : Expliquer les principales fonctionnalités d'une architecture d'Automatisation des tests
- **TAE-3.1.2 (K2)** : Expliquer comment concevoir une solution d'Automatisation des tests
- **TAE-3.1.3 (K3)** : Appliquer la stratification des frameworks d'Automatisation des tests
- **TAE-3.1.4 (K3)** : Appliquer différentes approches pour l'automatisation des cas de test
- **TAE-3.1.5 (K3)** : Appliquer les principes et les modèles de conception dans l'Automatisation des tests

## Chapitre 4 : Implémentation de l'Automatisation des tests (150 minutes - K4)

### **Mots-clés**
- risque
- contexte de test

### **Objectifs d'apprentissage**

#### 4.1 Développement de l'Automatisation des tests
- **TAE-4.1.1 (K3)** : Appliquer des lignes directrices qui soutiennent des activités efficaces d'Automatisation des tests en matière de pilotage et de déploiement

#### 4.2 Risques associés au développement de l'Automatisation des tests
- **TAE-4.2.1 (K4)** : Analyser les risques liés au déploiement et planifier des stratégies d'atténuation des risques pour l'Automatisation des tests

#### 4.3 Maintenabilité de la solution d'Automatisation des tests
- **TAE-4.3.1 (K2)** : Expliquer quels sont les facteurs qui soutiennent et affectent la maintenabilité de la solution d'Automatisation des tests

## Chapitre 5 : Stratégies d'implémentation et de déploiement (90 minutes - K3)

### **Mots-clés**
- test de contrat

### **Objectifs d'apprentissage**

#### 5.1 Intégration aux pipelines CI/CD
- **TAE-5.1.1 (K3)** : Appliquer l'Automatisation des tests à différents niveaux de test dans les pipelines
- **TAE-5.1.2 (K2)** : Expliquer la gestion de configuration pour les testware
- **TAE-5.1.3 (K2)** : Expliquer les dépendances de l'Automatisation des tests pour une infrastructure API

## Chapitre 6 : Reporting et métriques (150 minutes - K4)

### **Mots-clés**
- mesure
- métrique
- logging des tests
- rapport d'avancement des tests
- fin de test

### **Objectifs d'apprentissage**

#### 6.1 Collecte, analyse et reporting des données d'Automatisation des tests
- **TAE-6.1.1 (K3)** : Appliquer des méthodes de collecte de données à partir de la solution d'Automatisation des tests et du système sous test
- **TAE-6.1.2 (K4)** : Analyser les données de la solution d'Automatisation des tests et du système sous test pour mieux comprendre les résultats
- **TAE-6.1.3 (K2)** : Expliquer comment un rapport d'avancement des tests est construit et publié

## Chapitre 7 : Vérifier la solution d'Automatisation des tests (135 minutes - K3)

### **Mots-clés**
- analyse statique

### **Objectifs d'apprentissage**

#### 7.1 Vérification de l'infrastructure d'Automatisation des tests
- **TAE-7.1.1 (K3)** : Planifier la vérification de l'environnement d'Automatisation des tests, y compris la configuration des outils de test
- **TAE-7.1.2 (K2)** : Expliquer le comportement correct pour un script de test automatisé donné et/ou une suite de tests
- **TAE-7.1.3 (K2)** : Identifier les cas où l'Automatisation des tests produit des résultats inattendus
- **TAE-7.1.4 (K2)** : Expliquer comment l'analyse statique peut contribuer à la qualité du code d'Automatisation des tests

## Chapitre 8 : Amélioration continue (210 minutes - K4)

### **Mots-clés**
- validation de schéma
- histogramme de test

### **Objectifs d'apprentissage**

#### 8.1 Possibilités d'amélioration continue de l'Automatisation des tests
- **TAE-8.1.1 (K3)** : Découvrir les opportunités d'amélioration des cas de test par la collecte et l'analyse de données
- **TAE-8.1.2 (K4)** : Analyser les aspects techniques d'une solution d'Automatisation des tests déployée et fournir des recommandations d'amélioration
- **TAE-8.1.3 (K3)** : Restructurer le testware automatisé pour l'aligner sur les mises à jour du SUT
- **TAE-8.1.4 (K2)** : Résumer les opportunités d'utilisation des outils d'Automatisation des tests
