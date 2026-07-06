# CTAL-TAE - Test Automation Engineering - Flashcards

## Chapitre 5 : Stratégies d'implémentation et de déploiement

## Pourquoi intégrer l'automatisation dans les pipelines ?

Question sur les avantages de l'intégration de l'automatisation des tests dans les pipelines CI/CD.

%

**Avantages clés :**
- **Exécution sans surveillance** : Tests automatisés peuvent tourner 24/7
- **Points de contrôle qualité automatiques** à chaque étape
- **Feedback rapide** sur la qualité du code
- **Exécution périodique** (régression nocturne, tests de performance)
- **Intégration continue** avec validation automatique

[#pipeline]() [#avantages]() [#automatisation]()

## Dans quelle phase du pipeline s'intègrent les tests de composants ?

Question sur l'intégration des tests de composants dans les pipelines.

%

**Phase build** car :
- Tests exécutés sur composants individuels (classes, bibliothèques)
- Points de contrôle qualité pour le pipeline
- Partie cruciale de l'intégration continue
- Validation avant déploiement

**Exemples d'outils :** JUnit, NUnit, pytest

[#composants]() [#build]() [#integration]()

## Dans quelle phase du pipeline s'intègrent les tests système ?

Question sur l'intégration des tests système dans les pipelines.

%

**Phase déploiement** car :
- Dernier point de contrôle qualité du SUT livré
- Validation complète du système
- Exécution après déploiement des composants
- Peut faire échouer le déploiement si tests échouent

**Exemples d'outils :** Selenium, Playwright, Cypress

[#systeme]() [#deploiement]() [#validation]()

## Quelles sont les deux approches pour intégrer les tests système dans les pipelines ?

Question sur les différentes stratégies d'intégration des tests système.

%

**1. Tests dans la phase de déploiement :**
- Tests exécutés après déploiement du composant
- Déploiement peut échouer et être annulé si tests échouent
- Inconvénient : redéploiement nécessaire pour réexécuter les tests

**2. Tests en pipeline séparé :**
- Tests déclenchés par la réussite du déploiement
- Avantage : différentes suites de tests peuvent s'exécuter
- Inconvénient : tests ne constituent pas un point de contrôle qualité

[#approches]() [#systeme]() [#pipeline]()

## Quels sont les 3 éléments de la gestion de configuration pour les testware ?

Question sur les éléments de configuration à gérer.

%

**1. Configuration environnement de test :**
- URLs, identifiants, paramètres par environnement
- Stockée avec le testware ou dans bibliothèque commune

**2. Données de test :**
- Spécifiques à l'environnement/version du SUT
- Stockées dans TAFs ou systèmes de gestion dédiés

**3. Suites de tests/cas de tests :**
- Organisation par objectif (smoke, régression, acceptation)
- Exécution selon niveaux et environnements

[#configuration]() [#testware]() [#elements]()

## Qu'est-ce que la bascule de caractéristiques (feature toggle) ?

Question sur le mécanisme de gestion des versions et fonctionnalités.

%

**Feature toggle** :
- Mécanisme permettant d'activer/désactiver des fonctionnalités
- Contrôle l'exécution selon la version ou l'environnement
- Permet d'identifier les suites de tests à exécuter
- Correspondance exacte entre version SUT et testware

**Usage :** Gestion des versions avec différentes fonctionnalités

[#feature-toggle]() [#versioning]() [#fonctionnalites]()

## Quelles sont les 2 dépendances critiques pour l'automatisation des tests d'API ?

Question sur les prérequis pour automatiser les tests d'API.

%

**1. Connexions API :**
- Compréhension de la logique métier testable automatiquement
- Relations entre les APIs
- Définition des scénarios de test

**2. Documentation API :**
- Ligne de base pour l'automatisation
- Paramètres, en-têtes, types de données
- Schémas de requête/réponse

**Impact :** Essentiels pour construire une stratégie d'automatisation adéquate

[#api]() [#dependances]() [#documentation]()

## Qu'est-ce qu'un test de contrat ?

Question sur la définition et l'objectif des tests de contrat.

%

**Définition :** Test d'intégration vérifiant que les interfaces sont utilisées comme spécifié dans leurs contrats.

**Objectif :**
- Vérifier que les services peuvent communiquer entre eux
- S'assurer que les données partagées sont conformes aux règles spécifiées
- Détection précoce des défauts d'intégration
- Source des défauts plus facilement identifiable

[#contrat]() [#integration]() [#definition]()

## Quelle est la différence entre test de contrat piloté par le consommateur et par le fournisseur ?

Question sur les deux approches des tests de contrat.

%

**Piloté par le consommateur :**
- Le consommateur définit ses attentes
- Détermine comment le fournisseur doit répondre
- Garantit que le fournisseur répond aux besoins
- Usage : Microservices, APIs externes

**Piloté par le fournisseur :**
- Le fournisseur crée le contrat
- Indique comment ses services fonctionnent
- Contrôle de l'interface
- Usage : APIs internes, services propriétaires

[#contrat]() [#consommateur]() [#fournisseur]()

## Quels sont les avantages des tests de contrat ?

Question sur les bénéfices des tests de contrat.

%

**Avantages clés :**
- **Défauts trouvés plus tôt** dans le cycle de développement
- **Source des défauts plus facilement identifiable**
- **Compatibilité entre services distincts** (ex: microservices)
- **Évolution contrôlée** des interfaces
- **Validation des interactions** entre services

[#contrat]() [#avantages]() [#benefices]()

## Comment gérer le versioning du testware avec le SUT ?

Question sur la synchronisation des versions entre testware et SUT.

%

**Stratégies de versioning :**

**1. Bascule de caractéristiques :**
- Configuration pour chaque version/environnement
- Identification des suites de tests à exécuter
- Gestion par feature toggles

**2. Versioning synchronisé :**
- Testware versionné avec le SUT
- Correspondance exacte entre version SUT et testware
- Implémentation via système de gestion des livraisons
- Utilisation de balises ou branches

[#versioning]() [#testware]() [#sut]()

## Qu'est-ce que la régression nocturne ?

Question sur l'exécution périodique des tests.

%

**Régression nocturne :**
- Exécution périodique de suites de tests de régression
- Particulièrement pour les tests de longue durée
- Image claire de la qualité du SUT le matin
- Utilise les pipelines pour automatisation

**Avantages :**
- Feedback matinal sur la qualité
- Tests non bloquants pour l'équipe
- Détection précoce des régressions

[#regression]() [#nocturne]() [#periodique]()

---

*Compatible avec l'extension "Anki for VSCode" (jasew.anki)*