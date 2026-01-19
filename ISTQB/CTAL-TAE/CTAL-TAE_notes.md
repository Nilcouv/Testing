# Notes CTAL-TAE - Test Automation Engineering

## 0.3 Ressources

| Ressource | Description |
|-----------|-------------|
| [ISTQB TEST AUTOMATION ENGINEER V2.0 (2025)](https://www.youtube.com/playlist?list=PLj5VKaW115t2z4bsJDcPJRJwKEQpv1QNF) | Playlist de vidéos youtube de cours |
| [ISTQB CTAL-TAE Syllabus v2.0](https://www.istqb.org/sdm_downloads/istqb_ctal-tae_syllabus_v2-0/) | Syllabus de la certification |

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

### Objectifs

Dans ce chapitre vous en apprendrez plus sur :
- **Les objectifs de l'Automatisation des tests**
  - Que ce soit les avantages ou les inconvénients de l'Automatisation des tests (*TAE-1.1.1 (K2)*)
- **L'Automatisation des tests dans les différents modèles de cycle de vie du développement logiciel**
  - Comment l'Automatisation des tests est appliquée dans les différents modèles de cycle de vie du développement logiciel (*TAE-1.2.1 (K2)*)
  - Comment sélectionner les outils d'Automatisation des tests appropriés pour un "système sous test" (*SUT - System Under Test*) donné (*TAE-1.2.2 (K2)*)

### Mots-clés

| **Mot** | **Définition** |
|---------------|-----------------|
| **Système sous test** <br> (*SUT - System Under Test*) | Système qui est testé pour un fonctionnement correct. Selon ISTQB, il s'agit de l'objet de test. |
| **Automatisation des tests** <br> (*TA - Test Automation*) | Utilisation de logiciels pour effectuer ou soutenir les activités de test, par exemple la gestion des tests, la conception des tests, l'exécution des tests et la vérification des résultats. |
| **Ingénieur en Automatisation des tests** <br> (*TAE - Test Automation Engineer*) | Professionnel spécialisé dans la conception, le développement et la maintenance de solutions d'automatisation des tests. |

### 1.1 Objectif de l'Automatisation des tests

#### **TAE-1.1.1 (K2)** : Expliquer les avantages et les inconvénients de l'Automatisation des tests

L'Automatisation des tests implique :

- Le contrôle et la mise en place de suites de test par l'utilisation d'outils logiciels,
- L'exécution automatisée de ces tests, sans intervention manuelle,
- La comparaison automatique des résultats réels aux résultats attendus.

Dans le but :

- D'accroître l'efficacité des tests (*volume accru, temps réduit, déclenchement automatique via CI/CD*),
- D'contenir les coûts de test (*coûts optimisés, réduction des ressources humaines requises*),
- D'augmenter la fiabilité des tests (*réduction des erreurs d'exécution, couverture accrue des tests*),
- De réaliser des tests qui sont non-réalisables manuellement (*performance, charge, etc.*).

Et est réalisé par un **ingénieur en Automatisation des tests** (*TAE - Test Automation Engineer*), dont la responsabilité couvre :

- La conception,
- Le développement et
- La maintenance des solutions d'Automatisation des tests (*TAS - Test Automation Solution*).

Les avantages et inconvénients de l'Automatisation des tests sont les suivants :

| **AVANTAGES** | **Description** | **Exemple** |
|---------------|-----------------|-------------------|
| **Efficience accrue** | Capacité d'exécuter un volume massif de tests par build | Passage de 50 tests manuels/jour à des milliers de tests en quelques minutes |
| **Tester l'impossible** | Réalisation de tests non réalisables manuellement | Tests de charge (1000 utilisateurs simultanés), vérification de réponses en millisecondes, exécution multi-dispositifs/multi-sites |
| **Scénarios complexes** | Création et exécution de cas de test très sophistiqués | Flux métier multi-systèmes avec nombreuses conditions et variations |
| **Rapidité d'exécution** | Vitesse d'exécution largement supérieure aux tests manuels | Test exécuté en quelques secondes au lieu de 5 minutes manuellement |
| **Élimination des erreurs humaines** | Exécution identique à chaque itération, sans oubli ni distraction | Saisie de milliers de combinaisons de données sans erreur de frappe |
| **Rentabilité à long terme** | Investissement initial élevé mais coût réduit dans la durée | Coûts récurrents diminués par rapport aux tests manuels répétés |
| **Cohérence et fiabilité** | Exécution standardisée sans fatigue ni variation | Même séquence de 200 étapes exécutée identiquement à chaque fois, 24/7 |

| **INCONVÉNIENTS** | **Description** | **Exemple** |
|-------------------|-----------------|------------|
| **Investissement initial élevé** | Coûts importants de démarrage (TAE spécialisés, outils, matériel, formation) | Recrutement d'ingénieurs automation, achat de licences d'outils, formation de l'équipe existante |
| **Temps de mise en place** | Construction d'un framework robuste nécessite patience et temps | Création des fondations (architecture, bibliothèques, standards) avant l'automatisation effective |
| **Maintenance continue** | Les scripts de test nécessitent une maintenance régulière | Mise à jour des tests à chaque évolution de l'application pour maintenir leur validité |
| **Rigidité face aux changements** | Sensibilité aux modifications fréquentes de l'application | Petits changements d'UI causant l'échec de tests même si la fonctionnalité est correcte |
| **Introduction de nouveaux défauts** | Les scripts d'automatisation peuvent contenir des bugs | Faux positifs/négatifs dus à des erreurs dans le code de test, feedback erroné aux équipes |

Toutefois, l'Automatisation des tests présente également des limites :
| **LIMITES** | **Description** | **Exemple** |
|-------------|-----------------|--------------|
| **Automatisation partielle** | Tests nécessitant un jugement humain non automatisables | Évaluation de l'intuitivité d'une interface utilisateur, ressenti utilisateur global |
| **Portée restreinte** | Chaque test vérifie uniquement le scénario spécifique pour lequel il est conçu | Nombreuses zones à vérifier mais test limité à un scénario précis, laissant d'autres scénarios non vérifiés |
| **Interprétation limitée** | Vérification limitée à ce que la machine peut interpréter techniquement | Incapacité à juger si un élément "paraît correct" ou "semble agréable" à l'utilisateur |
| **Oracle de test complexe** | Difficulté à définir automatiquement les critères de succès/échec | Situations avec plusieurs réponses valides possibles, ou données changeant en temps réel (ex: disponibilité de vols) |

**En conclusion :**

L'automatisation des tests est un outil puissant, mais ce n'est pas une solution magique. La clé du succès réside dans l'**équilibre approprié entre tests automatisés et tests manuels**, adapté au contexte spécifique de chaque projet.

Une automatisation efficace agit comme un **collaborateur fiable** qui prend en charge les tâches répétitives, libérant ainsi les testeurs humains pour se concentrer sur des activités à plus forte valeur ajoutée : tests exploratoires, évaluation de l'expérience utilisateur, et analyse critique nécessitant le jugement humain.

### 1.2 L'Automatisation des tests dans le cycle de vie du développement logiciel

#### **TAE-1.2.1 (K2)** : Expliquer comment l'Automatisation des tests est appliquée dans les différents modèles de cycle de vie du développement logiciel


L'implémentation de l'automatisation varie selon le modèle SDLC utilisé. Chaque approche présente des caractéristiques spécifiques qui influencent la stratégie d'automatisation :

| **Modèle SDLC** | **Caractéristiques clés** | **Implémentation TA** | **Exécution TA** |
|-----------------|----------------------|----------------------------------|------------------------|
| **Cascade** | • Modèle linéaire et séquentiel<br>• Phases distinctes (exigences, conception, implémentation, vérification, maintenance)<br>• Documentation approuvée à chaque phase<br>• Processus rigide, changements coûteux | En parallèle ou après la phase d'implémentation | Phase de vérification uniquement |
| **Modèle en V** | • Modèle séquentiel<br>• construit par niveau d'exigence (haut -> bas)<br>• Activités de test validant chaque niveau (composant, intégration, système, intégration système, acceptation) | TAF spécifique pour chaque niveau | À chaque niveau |
| **Agile** | • Possibilités d'automatisation innombrables<br>• Planification décidée par TAE + représentants métier<br>• Pas de silos (développeurs, testeurs, BA, etc. travaillent ensemble. Ex : revues code, programmation binôme)<br>• Automatisation in-sprint | Intégrée dans chaque sprint<br>Couverture tous niveaux de test | Exécutions (intégration, acceptation, régression) à chaque sprint |


#### **TAE-1.2.2 (K2)** : Sélectionner les outils d'Automatisation des tests appropriés pour un système sous test donné

Afin de sélectionner des outils adaptés, le TAE doit prendre en compte plusieurs facteurs critiques :

**Contraintes techniques des outils :**
- Spécificité langage/plateforme (ex: Java, .NET, Python)
- Compétences requises (frameworks, APIs, scripting)
- Champ d'application limité (performance ≠ régression)
- Effort d'intégration variable (Open Source vs Commercial)

**Adaptation au contexte projet :**
L'évaluation doit considérer les contraintes projet (technologies, budget, objectifs) et l'expertise de l'équipe. Une équipe sans connaissances programmation privilégiera des solutions "low-code/no-code", tandis qu'une équipe technique bénéficiera d'outils alignés avec le langage du SUT pour faciliter collaboration développeurs-testeurs (débogage des tests, cross-training, etc.).

La sélection d'outils d'automatisation appropriés nécessite une analyse multicritères du contexte projet et technique :

| **Critère d'analyse** | **Questions clés** | **Impact sur choix outil** |
|-----------------------|-------------------|---------------------------|
| **Nature du SUT** | Type de système (web, mobile, API, desktop) ?<br>Technologies/langages utilisés ?<br>Contraintes techniques spécifiques ? | Compatibilité langage/plateforme<br>Outils spécialisés requis |
| **Besoins et contraintes projet** | Objectifs métier et timeline ?<br>Budget disponible ?<br>Types de tests requis ? | Champ d'application outil<br>Performance vs régression |
| **Taille équipe** | Nombre et disponibilité des testeurs ?<br>Expériences et expertises ? | Licences et infrastructure<br>Formation nécessaire |
| **Expertise équipe** | Niveau technique des testeurs ?<br>Connaissances programmation ?<br>Expérience frameworks ? | **Low-code/no-code** si peu technique<br>**Langage SUT** si technique |
| **Coût/Budget** | Budget acquisition et maintenance ?<br>TCO long terme ?<br>ROI attendu ? | **Commercial** (clé en main)<br>**Open Source** (intégration lourde) |
| **Type de collaboration** | Travail avec développeurs ?<br>Intégration CI/CD ?<br>Débogage partagé ? | Outils communs pour collaboration<br>Formation croisée possible |


**Stratégies de sélection selon le contexte :**

**🎯 Équipe peu technique :**
- Solutions "low-code/no-code" avec interface graphique
- Formation minimale requise, prise en main rapide
- Réduction des compétences programmation nécessaires

**🎯 Équipe technique :**
- Outils alignés avec le langage du SUT (Java, .NET, Python)
- Collaboration développeurs-testeurs facilitée
- Débogage partagé et formation croisée (cross-training)

**🎯 Contraintes budgétaires :**
- **Commercial :** Solution clé en main, support inclus, coût initial élevé
- **Open Source :** Coût licence faible, intégration plus lourde, maintenance interne

**🎯 Champ d'application :**
- Outils spécialisés par type de test (performance ≠ régression ≠ sécurité)
- Compatibilité plateforme/technologie obligatoire
- Évolutivité selon croissance projet

## Chapitre 2 : Se préparer à l'Automatisation des tests (180 minutes - K4)

### Objectifs

En apprendre plus sur :

- La conception pour la testabilité du SUT (observabilité, contrôlabilité, transparence de l'architecture)
- L'Automatisation des tests dans différents environnements
- Les exigences nécessaires à l'audit d'une solution d'Automatisation des tests appropriée
- Les considérations techniques nécessaires pour développer des recommandations sur l'Automatisation des tests

### **Mots-clés**

| **Mot** | **Définition** |
|---------------|-----------------|
| **Tests d'API** | Tests réalisés en soumettant des commandes au logiciel testé via les interfaces de programmation de l'application directement. |
| **Tests de l'interface graphique** | Tests réalisés en interagissant avec le logiciel testé via l'interface utilisateur graphique. |
| **Testabilité** | Degré d'efficacité et d'efficience avec lequel les critères de test peuvent être établis pour un système et les tests peuvent être effectués. |

### 2.1 Comprendre la configuration d'une infrastructure permettant l'Automatisation des tests

#### **TAE-2.1.1 (K2)** : Décrire les besoins de configuration d'une infrastructure permettant l'implémentation de l'Automatisation des tests

La **testabilité du SUT** est une exigence non fonctionnelle critique qui doit être conçue et implémentée parallèlement aux autres caractéristiques du système. Cette responsabilité incombe généralement à l'architecte logiciel, souvent accompagné d'un TAE pour identifier les domaines d'amélioration spécifiques.

**Solutions pour améliorer la testabilité :**

| **Solution** | **Description** | **Exemple d'implémentation** |
|--------------|-----------------|------------------------------|
| **Identifiants d'accessibilité** | Attributs ou propriétés ajoutés au code source permettant l'identification automatique des éléments pour les tests automatisés | `id="login-button"`, `data-testid="submit-form"`, `aria-label="search input"` |
| **Variables d'environnement système** | Paramètres système configurables qui permettent d'adapter le comportement de l'application selon l'environnement de test | `DATABASE_URL=test-db:5432`, `API_ENDPOINT=https://test-api.com`, `LOG_LEVEL=DEBUG`, `FEATURE_FLAG_NEW_UI=true` |
| **Variables de déploiement** | Paramètres définis avant le déploiement pour configurer l'application selon l'environnement cible | Configuration de build, variables d'environnement CI/CD |

**Explications détaillées des solutions de testabilité :**

**🔍 Identifiants d'accessibilité :**
- **Objectif** : Permettre aux outils d'automatisation de localiser et interagir avec les éléments de l'interface
- **Exemples concrets** :
  ```html
  <!-- HTML/Web -->
  <button id="submit-button" data-testid="login-submit">Connexion</button>
  <input aria-label="email input" data-testid="email-field" />
  
  <!-- Mobile (iOS) -->
  accessibilityIdentifier="loginButton"
  
  <!-- Mobile (Android) -->
  android:contentDescription="login button"
  ```

- **Implémentation par framework** :
  ```javascript
  // Playwright
  await page.getByTestId('login-submit').click();
  await page.getByRole('button', { name: 'Connexion' }).click();
  await page.getByLabel('email input').fill('test@example.com');
  ```
  
  ```robot
  # Robot Framework
  Click Element    data-testid=login-submit
  Click Element    id=submit-button
  Input Text    aria-label=email input    test@example.com
  ```

**🔧 Variables d'environnement système :**
- **Objectif** : Configurer dynamiquement l'application pour différents environnements de test
- **Exemples concrets** :
  ```bash
  # Base de données
  DATABASE_URL=postgresql://test:password@test-db:5432/testdb
  DATABASE_NAME=test_database
  
  # APIs et services
  API_BASE_URL=https://test-api.company.com
  PAYMENT_SERVICE_URL=https://test-payment.stripe.com
  
  # Configuration application
  LOG_LEVEL=DEBUG
  DEBUG_MODE=true
  FEATURE_FLAG_NEW_UI=true
  
  # Sécurité
  JWT_SECRET=test-secret-key
  ENCRYPTION_KEY=test-encryption-key
  ```

- **Implémentation par framework** :
  ```javascript
  // Playwright - playwright.config.js
  module.exports = {
    use: {
      baseURL: process.env.BASE_URL || 'http://localhost:3000',
      timeout: parseInt(process.env.TIMEOUT) || 30000,
    },
    projects: [
      {
        name: 'test',
        use: { baseURL: process.env.TEST_API_URL }
      }
    ]
  };
  ```
  
  ```robot
  # Robot Framework - Variables
  *** Variables ***
  ${BROWSER}    %{BROWSER|chrome}
  ${BASE_URL}    %{BASE_URL|http://localhost:3000}
  ${TIMEOUT}    %{TIMEOUT|30s}
  ```

**🚀 Variables de déploiement :**
- **Objectif** : Configurer l'application au moment du déploiement selon l'environnement cible
- **Exemples concrets** :
  ```yaml
  # Docker Compose
  environment:
    - NODE_ENV=test
    - PORT=3000
    - DATABASE_URL=${DATABASE_URL}
  
  # Kubernetes
  env:
    - name: ENVIRONMENT
      value: "test"
    - name: API_VERSION
      value: "v2"
  ```

**Aspects fondamentaux de la testabilité :**

| **Aspect** | **Définition** | **Implémentation** |
|------------|----------------|-------------------|
| **Observabilité** | Capacité du SUT à fournir des interfaces donnant un aperçu de son état interne | Logs, métriques, APIs de monitoring, interfaces de débogage |
| **Contrôlabilité** | Capacité du SUT à accepter des actions via des interfaces | Éléments UI, appels de fonction, protocoles de communication (TCP/IP, USB) |
| **Transparence de l'architecture** | Documentation claire des composants et interfaces pour tous les niveaux de test | Architecture documentée, interfaces bien définies, composants modulaires |

#### **TAE-2.1.2 (K2)** : Expliquer comment l'Automatisation des tests est exploitée dans différents environnements

L'automatisation des tests s'adapte aux différents environnements selon les besoins spécifiques de chaque phase du développement. Ces environnements peuvent être créés via conteneurs, virtualisation ou autres approches techniques.

**Typologie des environnements de test :**

| **Environnement** | **Objectif principal** | **Types de tests** | **Caractéristiques** |
|-------------------|------------------------|-------------------|---------------------|
| **Développement local** | Création initiale et test des composants | • Tests de composants<br>• Tests GUI<br>• Tests API<br>• Tests boîte blanche | IDE intégré, tests unitaires, débogage direct |
| **Build** | Construction du logiciel et vérification de l'exactitude | • Tests de bas niveau<br>• Tests d'intégration continue<br>• Analyse statique | Agent CI/CD, pas de déploiement réel |
| **Intégration** | Test du SUT entièrement intégré avec d'autres systèmes | • Tests d'interface utilisateur<br>• Tests API<br>• Tests d'intégration système<br>• Tests d'acceptation | Monitoring présent, tests boîte noire uniquement |
| **Préproduction** | Audit des caractéristiques de qualité non fonctionnelles | • Tests de performance<br>• Tests d'acceptation utilisateurs<br>• Tests non fonctionnels | Ressemble à la production, monitoring avancé |
| **Production/Exploitation** | Évaluation en temps réel pendant l'utilisation | • Tests fonctionnels et non fonctionnels<br>• Monitoring continu | Tests A/B, déploiement canari, blue/green |

**Stratégies d'implémentation par environnement :**

**🎯 Environnement de développement :**
- Tests unitaires automatisés dans l'IDE
- Intégration continue locale
- Feedback immédiat pour les développeurs

**🎯 Environnement de build :**
- Pipeline CI/CD automatisé
- Tests de régression rapides
- Validation de la qualité du code

**🎯 Environnement d'intégration :**
- Tests d'intégration complets
- Validation des interfaces entre systèmes
- Détection précoce des problèmes d'intégration

**🎯 Environnement de préproduction :**
- Tests de performance et charge
- Validation des exigences non fonctionnelles
- Simulation des conditions de production

**🎯 Environnement de production :**
- Monitoring continu et tests de surveillance
- Tests A/B pour validation des nouvelles fonctionnalités
- Détection des problèmes en temps réel

### 2.2 Processus d'évaluation pour sélectionner les bons outils et stratégies

#### **TAE-2.2.1 (K4)** : Analyser un système sous test pour déterminer la solution d'Automatisation des tests appropriée

L'analyse d'un SUT pour déterminer la TAS (Test Automation Solution) appropriée nécessite une approche structurée et collaborative. Le TAE doit rassembler les exigences en tenant compte du périmètre et des capacités du système.

**Facteurs d'analyse critique :**

| **Facteur** | **Questions clés** | **Impact sur la TAS** |
|-------------|-------------------|----------------------|
| **Type d'application** | Web, mobile, desktop, API, service ? | Outils spécialisés requis |
| **Technologies utilisées** | Langages, frameworks, plateformes ? | Compatibilité technique obligatoire |
| **Types de tests requis** | Fonctionnels, performance, sécurité, API ? | Couverture d'outils nécessaire |
| **Niveaux de test** | Unitaires, intégration, système, acceptation ? | Architecture en couches |
| **Rôles et compétences** | Développeurs, testeurs, BA, DevOps ? | Formation et support requis |
| **Périmètre et durée de vie** | Produit unique, ligne de produits, famille ? | Évolutivité et maintenance |
| **Données de test** | Disponibilité, qualité, gestion ? | Stratégie de données |
| **Intégrations tierces** | Applications externes, APIs, services ? | Stratégies de simulation |

**Exigences de la TAS :**

**📋 Activités à automatiser :**
- Gestion des tests (planification, suivi, reporting)
- Conception des tests (génération de cas de test)
- Exécution des tests (automatisation des procédures)
- Vérification des résultats (comparaison automatique)

**📋 Niveaux de test à supporter :**
- Tests unitaires (développement)
- Tests d'intégration (build)
- Tests système (intégration)
- Tests d'acceptation (préproduction)

**📋 Types de tests à supporter :**
- Tests fonctionnels (validation des fonctionnalités)
- Tests non fonctionnels (performance, sécurité)
- Tests d'API (validation des interfaces)
- Tests GUI (validation de l'interface utilisateur)

**📋 Méthodes d'émulation :**
- Simulation d'applications tierces
- Mocking des services externes
- Stubbing des composants non disponibles
- Virtualisation des environnements

#### **TAE-2.2.2 (K4)** : Illustrer les constatations techniques d'une évaluation d'outil

Après l'analyse du SUT et la collecte des exigences, l'évaluation des outils nécessite une approche comparative structurée. Il est rare qu'un seul outil réponde à toutes les exigences, nécessitant souvent une combinaison d'outils.

**Critères d'évaluation des outils :**

| **Critère** | **Éléments d'évaluation** | **Impact sur la décision** |
|-------------|---------------------------|---------------------------|
| **Langage/Technologie** | Compatibilité avec le SUT, IDE supporté | Alignement avec l'équipe technique |
| **Configuration** | Support multi-environnements, valeurs dynamiques/statiques | Flexibilité d'adaptation |
| **Gestion des données** | Intégration référentiel central, contrôle de versions | Traçabilité et maintenance |
| **Spécialisation** | Outils différents par type de test | Complexité d'intégration |
| **Reporting** | Fonctionnalités de rapport, alignement projet | Communication avec parties prenantes |
| **Intégration** | CI/CD, suivi tâches, gestion tests, autres outils | Écosystème technique |
| **Évolutivité** | Maintenabilité, facilité modification, compatibilité, fiabilité | Viabilité long terme |

**Tableau comparatif d'évaluation :**

Exemple:
| Exigence (priorité) | Outil A | Outil B | Outil C |
|---------------------|---------|---------|---------|
| Compatibilité Java (haute) | ✅ | ⚠️ | ❌ |
| Tests API (haute) | ✅ | ✅ | ⚠️ |
| Intégration CI/CD (moyenne) | ✅ | ✅ | ✅ |
| Coût licence (moyenne) | ❌ | ✅ | ✅ |
| Formation requise (basse) | ⚠️ | ✅ | ❌ |


**Processus de décision :**

**🎯 Phase 1 - Évaluation technique :**
- Analyse des capacités fonctionnelles
- Tests de preuve de concept
- Validation de la compatibilité

**🎯 Phase 2 - Évaluation organisationnelle :**
- Analyse des coûts (acquisition, maintenance, formation)
- Évaluation de l'impact sur les processus existants
- Validation de l'acceptation par les équipes

**🎯 Phase 3 - Recommandation :**
- Présentation des options aux parties prenantes
- Justification des choix techniques et business
- Plan d'implémentation et de migration

**Facteurs de succès de l'évaluation :**

**✅ Collaboration multi-parties prenantes :**
- Implication des testeurs manuels
- Participation des analystes métier
- Consultation des équipes techniques

**✅ Approche itérative :**
- Évaluation progressive des outils
- Tests pilotes pour validation
- Ajustements basés sur les retours

**✅ Vision long terme :**
- Considération de l'évolutivité
- Évaluation des coûts de maintenance
- Planification de l'évolution technologique

## Chapitre 3 : Architecture d'Automatisation des tests (210 minutes - K3)

### Objectifs

En apprendre plus sur :

- L'architecture d'Automatisation des tests et ses composants menant à une solution d'Automatisation des tests
- Les couches d'un framework d'Automatisation des tests et leur application
- Les approches d'utilisation des outils d'Automatisation des tests
- L'application des principes de conception et des canevas de conception à l'Automatisation des tests

### **Mots-clés**

| **Mot** | **Définition** |
|---------------|-----------------|
| **développement piloté par les comportements** | Approche collaborative de développement où l'équipe se concentre sur la livraison du comportement attendu d'un composant pour le client. |
| **capture/rejeux** | Approche d'automatisation des tests où les entrées vers l'objet de test sont enregistrées pendant les tests manuels pour générer des scripts automatisés. |
| **tests génériques d'Automatisation des tests** | Représentation des couches, composants et interfaces d'une architecture d'automatisation des tests, permettant une approche structurée et modulaire. |
| **architecture d'Automatisation des tests** | Structure organisationnelle et technique d'un système d'automatisation des tests, définissant les composants, leurs relations et les principes directeurs. |
| **tests pilotés par les mots-clés** | Technique de script qui utilise des fichiers de données contenant non seulement les données de test mais aussi des mots-clés liés à l'application testée. |
| **scripting linéaire** | Technique de script simple sans structure de contrôle dans les scripts de test. |
| **tests basés sur des modèles** | Tests basés sur ou impliquant des modèles du système ou de ses composants. |
| **scripting structuré** | Technique de script qui utilise des structures de contrôle et une organisation hiérarchique pour améliorer la maintenabilité. |
| **couche d'adaptation des tests** | Couche dans une architecture d'automatisation des tests qui fournit les interfaces nécessaires pour interagir avec le système sous test. |
| **harnais de tests** | Collection d'outils logiciels et de données de test configurés pour tester un programme en simulant l'environnement d'exécution. |
| **test piloté par les données** | Technique de script qui stocke les données de test et les résultats attendus dans un tableau, permettant à un script de contrôle d'exécuter tous les tests. |
| **étape de test** | Action individuelle la plus petite dans un script de test ou un cas de test. |
| **solution d'Automatisation des tests** | Ensemble complet d'outils, de processus et de ressources mis en place pour automatiser les activités de test dans un contexte donné. |
| **développement piloté par les tests** | Pratique de développement où les tests sont écrits avant le code de production. |
| **script de test** | Séquence d'instructions qui peut être exécutée par un outil d'exécution de test. |

### 3.1 Concepts de conception utilisés dans l'Automatisation des tests

#### **TAE-3.1.1 (K2)** : Expliquer les principales fonctionnalités d'une architecture d'Automatisation des tests

**Architecture générique d'Automatisation des tests (gTAA)**

La gTAA est un concept de conception de haut niveau qui fournit une vue abstraite de la communication entre l'automatisation des tests et les systèmes connectés. Elle définit les capacités nécessaires lors de la conception d'une architecture d'automatisation des tests (TAA).

**Interfaces de la gTAA :**

| **Interface** | **Description** | **Fonction** |
|---------------|-----------------|--------------|
| **Interface SUT** | Connectivité entre le SUT et le TAF | Communication directe avec le système testé |
| **Interface gestion projet** | Avancement du développement de l'automatisation | Reporting et suivi de progression |
| **Interface gestion tests** | Cartographie des définitions et cas de test automatisés | Traçabilité entre tests manuels et automatisés |
| **Interface gestion configuration** | Pipelines CI/CD, environnements et testware | Déploiement et versioning |

**Diagramme de l'Architecture générique d'Automatisation des tests (gTAA) :**

```
                           🏢 Gestion de projet
                           (Interface gestion projet)
                                     ↕
    ⚙️ Gestion de              ╔═══════════════════════════╗              📋 Gestion des tests
       configuration    ←→     ║  Framework d'automatisation ║     ←→    (Interface gestion tests)
    (Interface gestion         ║        des tests           ║
     configuration)            ║                            ║
                               ║  🔄 Génération des tests   ║
                               ║  📝 Définition des tests   ║
                               ║  ▶️  Exécution des tests   ║
                               ║  🔧 Adaptation des tests   ║
                               ╚═══════════════════════════╝
                                          ↕
                              🖥️ Système sous test
                                 (Interface SUT)
```

**Capacités principales du Framework d'Automatisation des tests :**

| **Capacité** | **Description** | **Caractéristiques** |
|--------------|-----------------|---------------------|
| **Génération des tests** | Conception automatisée des cas de tests basés sur des modèles | • Capacité optionnelle<br>• Utilise les tests basés sur modèles (MBT)<br>• Référence : Syllabus CT-MBT ISTQB |
| **Définition des tests** | Implémentation des cas de test et/ou suites de tests | • Séparation définition/SUT/outils<br>• Tests haut et bas niveau<br>• Gestion données/cas/bibliothèques |
| **Exécution des tests** | Exécution automatique et logging | • Outil d'exécution automatique<br>• Composant de logging<br>• Reporting des résultats |
| **Adaptation des tests** | Adaptation aux différents composants/interfaces du SUT | • Adaptateurs multiples<br>• Connexion via API, protocoles, services<br>• Flexibilité d'intégration |

#### **TAE-3.1.2 (K2)** : Expliquer comment concevoir une solution d'Automatisation des tests

**Définition d'une Solution d'Automatisation des tests (TAS)**

Une TAS est définie par la compréhension des exigences fonctionnelles, non fonctionnelles et techniques du SUT, ainsi que des outils existants ou requis pour l'implémentation.

**Éléments de conception de l'Architecture d'Automatisation des tests (TAA) :**

| **Élément** | **Description** | **Considérations techniques** |
|-------------|-----------------|------------------------------|
| **Spécification d'outils** | Outils d'automatisation et bibliothèques spécifiques | Compatibilité, licences, support |
| **Extensions et composants** | Développement de composants personnalisés | Réutilisabilité, maintenance, documentation |
| **Connectivité et interfaces** | Exigences de connexion système | Pare-feu, BD, URLs, mocks/stubs, files d'attente, protocoles |
| **Intégration outils** | Connexion aux outils de gestion | Tests, défauts, traçabilité |
| **Contrôle de version** | Système de versioning et référentiels | Git, SVN, gestion des branches, releases |

**Implémentation TAS :**
- **Outils commerciaux** : Solutions clé en main, support inclus
- **Outils open-source** : Flexibilité, coût réduit, maintenance interne
- **Adaptateurs spécifiques** : Développement sur mesure selon SUT

#### **TAE-3.1.3 (K3)** : Appliquer la stratification des frameworks d'Automatisation des tests

**Framework d'Automatisation des tests (TAF)**

Le TAF constitue la base d'une TAS et comprend souvent un harnais de test (également appelé test runner), des bibliothèques de test, des scripts de test et des suites de tests.

**Couches du TAF (TAF Layers)**

Les couches TAF définissent une frontière distincte de classes ayant des objectifs similaires tels que :
- Cas de test
- Reporting de tests  
- Logging de tests
- Chiffrement
- Harnais de test

En introduisant une couche pour chaque objectif unique, la conception peut devenir compliquée. Il est donc recommandé de **garder le nombre de couches TAF faible**.

**Diagramme des Couches du Framework d'Automatisation des tests (TAF) :**

```
    ╔═══════════════════════════════════════════════════════════════════════════════════╗
    ║                            📝 SCRIPTS DE TESTS                                   ║
    ║                                                                                   ║
    ║  • Référentiel cas de test du SUT      • Annotations suites                      ║
    ║  • Appels services logique métier      • Étapes de test, flux utilisateur, API  ║
    ║  ⚠️ Aucun appel direct aux bibliothèques principales                             ║
    ╚═══════════════════════════════════════════════════════════════════════════════════╝
                                           ↕ Appels services
    ╔═══════════════════════════════════════════════════════════════════════════════════╗
    ║                            🔧 LOGIQUE MÉTIER                                     ║
    ║                                                                                   ║
    ║  • Bibliothèques dépendantes SUT       • Configuration TAF                       ║
    ║  • Interface entre couches             • Héritage/façades des bibliothèques      ║
    ║  • Configuration TAF pour SUT          • Configurations supplémentaires           ║
    ╚═══════════════════════════════════════════════════════════════════════════════════╝
                                         ↕ Héritage/Façades
    ╔═══════════════════════════════════════════════════════════════════════════════════╗
    ║                         ⚙️ BIBLIOTHÈQUES PRINCIPALES                             ║
    ║                                                                                   ║
    ║  • Bibliothèques indépendantes SUT     • Composants réutilisables                ║
    ║  • Base commune multiple TAF           • Pile développement partagée             ║
    ║  • Réutilisables dans tout projet partageant la même pile de développement      ║
    ╚═══════════════════════════════════════════════════════════════════════════════════╝
```

**Architecture en couches du TAF :**

| **Couche** | **Responsabilité** | **Contenu** | **Interactions** |
|------------|-------------------|-------------|------------------|
| **Scripts de tests** | Référentiel de cas de test du SUT et annotations suites | • Cas de test<br>• Annotations suites<br>• Appels services logique métier<br>• Étapes de test, flux utilisateur, API | ⚠️ **Aucun appel direct aux bibliothèques principales** |
| **Logique métier** | Bibliothèques dépendantes du SUT | • Configuration TAF pour SUT<br>• Héritage/façades des bibliothèques principales<br>• Configurations supplémentaires<br>• Configuration TAF pour exécution contre SUT | Interface entre scripts et bibliothèques |
| **Bibliothèques principales** | Bibliothèques indépendantes du SUT | • Composants réutilisables<br>• Base commune pour multiple TAF<br>• Pile de développement partagée<br>• Réutilisables dans tout projet partageant la même pile de développement | Fondation technique réutilisable |

**Mise à l'échelle de l'automatisation :**

**Diagramme d'Application des bibliothèques principales à des TAFs multiples :**

```mermaid
graph TD
    subgraph P1["🏗️ PROJET #1"]
        S1["📝 Scripts Tests App #1"]
        M1["🔧 Logique Métier App #1"]
        S2["📝 Scripts Tests App #2"]
        M2["🔧 Logique Métier App #2"]
        
        S1 --> M1
        S2 --> M2
    end
    
    subgraph P2["🏗️ PROJET #2"]
        S3["📝 Scripts Tests App #3"]
        M3["🔧 Logique Métier App #3"]
        
        S3 --> M3
    end
    
    LIB["⚙️ Bibliothèques Principales"]
    
    M1 --> LIB
    M2 --> LIB
    M3 --> LIB
```

Les bibliothèques principales fournissent une base réutilisable pour plusieurs TAF :
- **Projet #1** : 2 TAF (App #1, App #2) construits sur les mêmes bibliothèques principales
- **Projet #2** : 1 TAF (App #3) réutilisant les bibliothèques principales existantes
- **Avantages** : Réduction coûts, standardisation, maintenance centralisée

**Organisation des TAE :**
- **Un TAE** construit les TAFs pour le Projet #1
- **Un second TAE** construit le TAF pour le Projet #2

#### **TAE-3.1.4 (K3)** : Appliquer différentes approches pour l'automatisation des cas de test

**Approches de développement pour cas de tests automatisés :**

| **Approche** | **Description** | **Avantages** | **Inconvénients** |
|--------------|-----------------|---------------|-------------------|
| **Capture/rejeu** | Capture interactions manuelles pour générer scripts | • Facile à mettre en place<br>• Aucune programmation | • Difficile à maintenir/évoluer<br>• SUT doit être disponible<br>• Périmètre restreint<br>• Forte dépendance version SUT |
| **Scripting linéaire** | Programmation simple sans bibliothèques personnalisées | • Facile démarrage<br>• Scripts modifiables vs capture/rejeu | • Difficile maintenance/évolution<br>• Périmètre restreint<br>• Connaissances programmation requises |
| **Scripting structuré** | Bibliothèques avec éléments réutilisables | • Maintenabilité élevée<br>• Évolutivité<br>• Séparation logique métier | • Connaissances programmation requises<br>• Investissement initial important |
| **TDD (Test-Driven Development)** | Tests définis avant implémentation ("red, green, refactor") | • Qualité code améliorée<br>• Testabilité renforcée<br>• Communication équipe | • Temps adaptation initial<br>• Risque fausse confiance si mal appliqué |
| **DDT (Data-Driven Testing)** | Scripts alimentés par données externes (.csv, .xlsx, BD) | • Extension rapide cas de test<br>• Coût ajout réduit<br>• Autonomie analystes test | • Gestion données complexe |
| **KDT (Keyword-Driven Testing)** | Liste/tableau d'étapes dérivées de mots-clés utilisateur | • Implication analystes métier<br>• Utilisable tests manuels<br>• Référence ISO/IEC/IEEE 29119-5 | • Implémentation/maintenance complexe<br>• Effort considérable petits systèmes |
| **BDD (Behavior-Driven Development)** | Format langage naturel (Given, When, Then) stocké en fichiers features | • Communication équipe améliorée<br>• Couverture spécifications<br>• Multi-niveaux pyramide tests | • Cas limites à définir séparément<br>• Confusion avec simple langage naturel<br>• Implémentation/maintenance complexe |

#### **TAE-3.1.5 (K3)** : Appliquer les principes et les modèles de conception dans l'Automatisation des tests

**Principes de programmation orientée objet :**

| **Principe** | **Définition** | **Application en automatisation** |
|--------------|----------------|-----------------------------------|
| **Encapsulation** | Masquage des détails d'implémentation | Classes de test avec méthodes privées/publiques |
| **Abstraction** | Simplification de concepts complexes | Interfaces génériques pour interactions SUT |
| **Héritage** | Réutilisation de code via classes parentes | Bibliothèques de base étendues par projets |
| **Polymorphisme** | Comportements différents pour même interface | Adaptateurs multiples pour différents SUT |

**Principes SOLID :**

| **Principe** | **Acronyme** | **Bénéfice** |
|--------------|--------------|--------------|
| **S** - Single Responsibility | Une classe = une responsabilité | Lisibilité code |
| **O** - Open-Closed | Ouvert extension, fermé modification | Maintenabilité |
| **L** - Liskov Substitution | Substituabilité objets dérivés | Évolutivité |
| **I** - Interface Segregation | Interfaces spécialisées vs générales | Modularité |
| **D** - Dependency Inversion | Dépendance abstractions vs concrétions | Flexibilité |

**Patterns de conception essentiels :**

| **Pattern** | **Objectif** | **Application TAE** | **Avantages** |
|-------------|--------------|---------------------|---------------|
| **Façade** | Masquer détails implémentation | Interface simplifiée pour testeurs | Abstraction, facilité utilisation |
| **Singleton** | Instance unique | Un seul driver communication SUT | Cohérence, gestion ressources |
| **Page Object Model** | Encapsulation éléments page | Classe par page, localisateurs centralisés | Maintenance centralisée, réutilisabilité |
| **Flow Model** | Extension Page Object | Façade supplémentaire pour actions utilisateur | Double abstraction, réutilisabilité étapes |

**Architecture Flow Model :**
```
Scripts de test → Flow Model (actions utilisateur) → Page Object Model (éléments page) → SUT
```

Cette architecture à double façade améliore l'abstraction et la maintenabilité en permettant la réutilisation des étapes de test dans plusieurs scripts.

## Chapitre 4 : Implémentation de l'Automatisation des tests (150 minutes - K4)

### Objectifs

En apprendre plus sur :

- La planification et le déploiement d'un projet pilote d'Automatisation des tests
- Les risques de déploiement et les stratégies d'atténuation
- Les facteurs qui améliorent la maintenabilité du code d'Automatisation des tests

### **Mots-clés**

| **Mot** | **Définition** |
|---------|----------------|
| **risque** | A factor that could result in future negative consequences. |
| **contexte de test** | Environnement dans lequel un test est exécuté, incluant les préconditions, les données de test et les configurations nécessaires. |

### 4.1 Développement de l'Automatisation des tests

#### **TAE-4.1.1 (K3)** : Appliquer des lignes directrices qui soutiennent des activités efficaces de pilotage et de déploiement de l'Automatisation des tests

**Définition du périmètre du projet pilote**

Un projet pilote d'Automatisation des tests ne prend pas beaucoup de temps à mener, mais le résultat peut avoir un impact significatif sur la direction que prend le projet. Il est crucial de définir clairement le périmètre de validation.

**Évaluation des éléments clés pour les lignes directrices :**

| **Élément** | **Description** | **Impact sur la stratégie** |
|-------------|-----------------|----------------------------|
| **Langage(s) de programmation** | Choix des technologies de développement | Alignement avec l'équipe technique et le SUT |
| **Outils commerciaux clé en main/Open-source** | Sélection des outils d'automatisation | Budget, support, flexibilité d'implémentation |
| **Niveaux de test à couvrir** | Unitaires, intégration, système, acceptation | Architecture en couches du TAF |
| **Cas de test sélectionnés** | Priorisation des tests à automatiser | ROI et validation de l'approche |
| **Approche de développement** | TDD, DDT, KDT, BDD, etc. | Maintenabilité et collaboration équipe |

**Définition de l'approche initiale :**

Sur la base des points énumérés ci-dessus, les TAE peuvent définir une approche initiale à suivre. Plusieurs prototypes initiaux différents peuvent être créés pour montrer les avantages et inconvénients des différentes approches. À partir de là, les TAE peuvent décider du chemin à suivre.

**Planification et suivi du projet pilote :**

- **Définition d'un calendrier** : Élément important pour respecter les délais et garantir le succès du projet pilote
- **Vérification périodique** : Recommandation courante de vérifier périodiquement l'avancement du projet pilote afin d'identifier les risques éventuels et de les atténuer

**Intégration CI/CD pendant le pilote :**

Il est recommandé d'essayer d'intégrer la solution et le code déjà implémenté dans le CI/CD. Cela peut mettre en évidence des problèmes précoces, soit dans le SUT, soit dans la TAS, soit dans l'intégration globale des différents outils au sein de l'organisation.

Au fur et à mesure que le nombre de cas de test augmente, les TAE peuvent penser à modifier la configuration initiale du CI/CD pour exécuter les tests de différentes manières et à différents temps de réflexion.

**Évaluation des aspects non-techniques :**

Au cours du projet pilote, il est nécessaire d'évaluer d'autres aspects non-techniques :

| **Aspect** | **Description** | **Impact sur le projet** |
|------------|-----------------|--------------------------|
| **Connaissances et expérience** | Niveau technique des membres de l'équipe | Formation et support requis |
| **Structure de l'équipe** | Organisation et rôles | Collaboration et communication |
| **Règles de licence et d'organisation** | Contraintes légales et politiques | Conformité et gouvernance |
| **Plan de test** | Type de plan de test et niveaux de test ciblés à couvrir pendant l'automatisation des cas de test | Couverture et stratégie d'automatisation |

**Évaluation finale :**

Une fois le projet pilote terminé, l'effort doit être évalué par les TAE et les Test Managers afin d'évaluer la réussite ou la défaillance et de prendre une décision appropriée.

### 4.2 Risques associés au développement de l'Automatisation des tests

#### **TAE-4.2.1 (K4)** : Analyser les risques liés au déploiement et planifier des stratégies d'atténuation des risques pour l'Automatisation des tests

**Considérations architecturales initiales :**

L'interface entre le TAF et le SUT doit être prise en compte dans le cadre de la conception architecturale. Cette interface détermine la façon dont l'automatisation interagit avec le système testé et influence directement la sélection des outils de :

- **Packaging** : Gestion des versions et distribution du testware
- **Logging des tests** : Capture des informations d'exécution et de débogage
- **Harnais de test** : Infrastructure d'exécution des tests automatisés

**Facteurs critiques d'évaluation du pilote :**

Au cours de l'implémentation du projet pilote, l'expansion et la maintenance du code d'Automatisation des tests doivent être prises en compte. Ce sont des facteurs cruciaux de la phase d'évaluation du pilote et ils peuvent sérieusement affecter la décision finale.

| **Facteur** | **Description** | **Impact sur la décision** |
|-------------|-----------------|----------------------------|
| **Évolutivité** | Capacité à étendre le code de la solution d'automatisation | Évolutivité et viabilité long terme |
| **Maintenabilité** | Facilité de maintenance à long terme | Coûts opérationnels et durabilité |

**🌐 Risques d'infrastructure et stratégies d'atténuation :**

Différents risques liés au déploiement peuvent être identifiés à partir du pilote. Il faut se préparer aux risques liés au déploiement, tels que les problèmes de pare-feu, l'utilisation des ressources, la connexion au réseau et la fiabilité. Ces éléments ne sont pas strictement liés à l'Automatisation des tests, mais les TAE doivent s'assurer que toutes les conditions sont réunies pour fournir des points de contrôle de qualité fiables et bénéfiques dans leur processus de développement.

| **Catégorie de risque** | **Description** | **Impact** | **Stratégie d'atténuation** | **Implémentation** |
|------------------------|-----------------|------------|----------------------------|-------------------|
| **Configuration** | • Pare-feu bloquant les communications<br>• Ports réseau fermés<br>• Règles de sécurité restrictives<br>• Configuration DNS incorrecte | Tests indisponibles | Configuration réseau appropriée | • Ouverture des ports nécessaires<br>• Règles de pare-feu spécifiques<br>• Tests de connectivité automatisés<br>• Validation de la configuration |
| **Performance** | • Consommation excessive CPU/RAM<br>• Concurrence entre tests<br>• Timeouts d'exécution<br>• Ressources partagées insuffisantes | Tests lents ou échecs | Monitoring et optimisation | • Monitoring en temps réel<br>• Limitation des ressources par test<br>• Optimisation des scripts<br>• Planification des exécutions |
| **Stabilité** | • Services SUT indisponibles<br>• Instabilité des connexions réseau<br>• Pannes système intermittentes<br>• Défaillances des composants | Tests intermittents ou impossibles | Redondance et monitoring | • Health checks automatisés<br>• Services de backup<br>• Connexions multiples<br>• Retry automatique |

**📱 Risques spécifiques (mobile) et stratégies d'atténuation :**

L'utilisation d'appareils réels pour l'Automatisation des tests mobiles en est un exemple. Les appareils mobiles doivent être mis sous tension, disposer d'une autonomie de batterie suffisante pour fonctionner pendant le test, être connectés à un réseau et avoir accès au SUT.

| **Catégorie de risque** | **Description** | **Impact** | **Stratégie d'atténuation** | **Implémentation** |
|------------------------|-----------------|------------|----------------------------|-------------------|
| **Alimentation** | • Appareils éteints ou en veille<br>• Batterie insuffisante pour la durée du test<br>• Coupures de courant<br>• Recharge incomplète | Tests non exécutables ou interrompus | Alimentation continue et monitoring | • Alimentations de secours (UPS)<br>• Scripts de réveil automatique<br>• Alertes de batterie faible<br>• Recharge automatique |
| **Connectivité** | • Perte de connectivité réseau<br>• SUT inaccessible depuis l'appareil<br>• Configuration réseau incorrecte<br>• Problèmes de sécurité réseau | Tests échoués ou impossibles | Redondance et configuration | • Connexions multiples (WiFi/4G)<br>• Tests de connectivité<br>• Configuration réseau appropriée<br>• Basculement automatique |

**⚙️ Risques techniques de déploiement et stratégies d'atténuation :**

Les risques techniques liés au déploiement peuvent inclure le packaging, le logging, la structuration des tests et la mise à jour. Chaque aspect présente des défis spécifiques qui peuvent compromettre la réussite du déploiement.

| **Catégorie de risque** | **Description** | **Impact** | **Stratégie d'atténuation** | **Implémentation** |
|------------------------|-----------------|------------|----------------------------|-------------------|
| **Versioning** | **Packaging** : Perte de versions, distribution complexe, incompatibilité entre versions<br><br>**Mise à jour** : Mises à jour automatiques non contrôlées, changements de version des appareils | Tests instables ou impossibles | Contrôle de version et compatibilité | • Git/SVN avec tags de version<br>• Repository centralisé<br>• Pipeline de validation<br>• Lock files et environnements virtuels |
| **Observabilité** | **Journalisation** : Logs insuffisants, trop verbeux, perte de logs critiques<br><br>**Monitoring** : Manque de visibilité sur l'état des systèmes | Difficulté d'investigation | Journalisation structurée et monitoring | • Configuration des niveaux de log<br>• Stockage centralisé et backup<br>• Health checks automatisés<br>• Rotation et archivage |
| **Architecture** | **Structuration des tests** : Harnais instable, dispositifs défaillants, tests non atomiques, organisation chaotique du code | Tests non reproductibles | Infrastructure robuste et organisation | • Monitoring du harnais<br>• Scripts de setup/teardown<br>• Isolation des tests<br>• Structure logique et documentation |

**📝 Notes contextuelles :**

- **Packaging** : Il s'agit de "conditionner" le code d'automatisation des tests pour le distribuer et le déployer. Comme le SUT, l'automatisation doit être versionnée, compilée et déployée. Sans packaging approprié, les tests ne peuvent pas être exécutés sur différents environnements (dev, test, prod).

- **Logging** : La journalisation capture les informations pendant l'exécution des tests. Sans logs, impossible de savoir pourquoi un test a échoué : était-ce un vrai bug du SUT ou un problème d'automatisation ? Les logs permettent de diagnostiquer et déboguer les échecs.

- **Test structuring** : Il s'agit d'organiser l'architecture des tests (harnais, dispositifs, suites). Une mauvaise structuration rend les tests fragiles et difficiles à maintenir. Par exemple, si les tests partagent des données, un échec peut en causer d'autres.

- **Updating** : Les mises à jour automatiques peuvent casser l'automatisation. Par exemple, une mise à jour de Selenium peut rendre les tests incompatibles, ou un changement d'OS sur un appareil mobile peut faire échouer les tests.

**Journalisation - Typologie recommandée :**

Les types suivants permettent d'avoir une vision exhaustive de l'ensemble des événements rencontrés dans les entrées du journal. Et permettent de les hiérarchiser et catégoriser rapidement afin de diagnotiquer efficacement les échecs de tests.

| **Type** | **Usage** | **Exemple d'utilisation** | **Contexte d'utilisation** |
|------------|-----------|---------------------------|----------------------------|
| **Fatal** | Événements d'erreur conduisant à l'abandon de l'exécution | Erreur critique système | Arrêt immédiat requis |
| **Erreur** | Condition/interaction échouée, cas de test échoué | Assertion échouée | Échec de test à signaler |
| **Avertissement** | Condition/action inattendue sans interruption | Valeur par défaut utilisée | Situation anormale mais récupérable |
| **Info** | Informations de base sur l'exécution | Début/fin de test | Suivi du flux d'exécution |
| **Débogage** | Détails spécifiques pour investigation | Variables intermédiaires | Analyse des problèmes |
| **Trace** | Informations maximales d'exécution | Flux complet d'exécution | Investigation approfondie |

### 4.3 Maintenabilité de la solution d'Automatisation des tests

#### **TAE-4.3.1 (K2)** : Expliquer quels sont les facteurs qui soutiennent et affectent la maintenabilité de la solution d'Automatisation des tests

**Facteurs influençant la maintenabilité :**

La maintenabilité est fortement influencée par les normes de programmation et les attentes des TAE les uns envers les autres.

### **A. Problèmes qui AFFECTENT la maintenabilité :**

**1. Codage en dur :**
Valeurs intégrées directement dans le code sans possibilité de modification externe (ex. `password123` vs `user.password`), ce qui:

- contraint à réaliser des modifications manuelles du code à chaque changement,
- rend les tests non portables,
- rend la maintenance coûteuse.

**2. Manque de standards :**
Absence de conventions et de règles communes pour l'écriture du code (ex. `btnLogin` vs `login_button`), ce qui:

- complique la compréhension du code par l'équipe
- augmente le temps de formation des nouveaux développeurs
- rend le code difficile à déboguer et maintenir

**3. Outils inadéquats :**
Absence ou utilisation inappropriée d'outils de développement et de qualité (ex. pas d'analyseurs statiques, branches Git désorganisées), ce qui:

- retarde la détection des problèmes de qualité
- produit un code peu lisible et mal formaté
- complique la collaboration avec risque de perte de code

### **B. Solutions qui SOUTIENNENT la maintenabilité :**

**1. Principes "Clean Code" (Robert C. Martin, 2008) :**

Le "Clean Code" est une approche de programmation qui vise à écrire du code lisible, maintenable et de qualité. Ces principes permettent d'établir des standard partagés au sein de l'équipe, rendant le code compréhensible et modifiable par tous.

| **Principe** | **Application** | **Bénéfice** |
|--------------|-----------------|--------------|
| **Convention de nommage** | Noms significatifs (`loginButton`, `resetPasswordButton`) | Identification claire des composants |
| **Structure de projet** | Organisation logique et commune | Navigation facilitée |
| **Éviter le codage en dur** | Variables d'environnement, configuration | Flexibilité |
| **Paramètres limités** | 3-4 paramètres maximum | Lisibilité |
| **Méthodes courtes** | Une méthode = une responsabilité | Compréhension |
| **Logging approprié** | Niveaux adaptés selon le contexte | Diagnostic |
| **Patterns de conception** | Page Object Model, Façade, Singleton | Code structuré |
| **Testabilité** | Séparation des responsabilités | Qualité |

**2. Stratégies anti-codage en dur :**

Le codage en dur (voir A.1) consiste à intégrer des valeurs directement dans le code sans pouvoir les modifier. La solution consiste à créer des "alias" (références) vers des sources externes :

| **Solution** | **Méthode** | **Bénéfice** |
|--------------|-------------|-------------|
| **Tests pilotés par les données** | Créer des alias vers des sources de données externes (CSV, base) | Données maintenues dans une source commune, modification facile |
| **Constantes centralisées** | Créer des alias vers des constantes dans un fichier de configuration | Réduction des sources à maintenir, modification en un seul endroit |
| **Configuration externalisée** | Créer des alias vers des variables d'environnement | Adaptation sans recompilation, maintenance simplifiée |

**3. Outils de qualité :**

| **Outil** | **Fonction** |
|-----------|--------------|
| **Analyseurs statiques** | Vérification automatique du code |
| **Formateurs de code** | Mise en forme automatique |
| **IDE intégrés** | Outils de développement |

**4. Gestion de version :**

- **Branches de fonctionnalités** : Développement de nouvelles features
- **Branches de versions** : Gestion des releases  
- **Branches de corrections** : Fixes de bugs
- **Structure de projet** : Organisation logique

**5. Patterns de conception :**

L'utilisation de canevas de conception est fortement recommandée. Les patterns - tels que décrits au point 3.1.5 - permettent d'implémenter un code d'Automatisation des tests structuré et correctement maintenable, à condition qu'ils soient utilisés correctement.

## Chapitre 5 : Stratégies d'implémentation et de déploiement (90 minutes - K3)

### Objectifs

En apprendre plus sur :

- Les pipelines CI/CD et l'éxécution des tests dans les différents niveaux de test
- La gestion de la configuration pour les composants de l'automatisation (testware)
- les dépendances liées aux tests d'API et aux tests de contrat

### Mots-clés

| **Mot** | **Définition** |
|---------|----------------|
| **test de contrat** | Type de test d'intégration vérifiant que les interfaces sont utilisées comme spécifié dans leurs contrats. |

### Introduction

Quand le produit croît, la complexité explose tandis que les ressources restent finies: la qualité manuelle ne tient pas. La solution est un système d'automatisation autonome, maintenable, ancré dans les pipelines CI/CD, qui contrôle la qualité à chaque changement de façon traçable et reproductible. 

Ce chapitre traite trois aspects stratégiques de ce déploiement: le **placement** des tests dans le flux CI/CD (5.1.1), la **configuration** permettant de tourner sur tout environnement (5.1.2), et la **maîtrise des dépendances** en infrastructure API (5.1.3).

### 5.1 Intégration aux pipelines CI/CD

Les tests automatisés s'exécutent sans surveillance: on peut donc les intégrer aux pipelines CI/CD ou les planifier périodiquement. Le défi est de déterminer **où** les exécuter (à quelle étape du pipeline), **comment** les déclencher (sur chaque push, merge, ou déploiement), et **avec quelle politique de blocage** (point de contrôle bloquant ou informatif). La réponse à ces trois questions transforme un ensemble de scripts en garde‑fou opérationnel.

### **5.1.1 (K3) : Appliquer l'automatisation à différents niveaux de test dans les pipelines**

Principes
- Exécuter chaque niveau de test à l’étape du pipeline où il apporte le meilleur rapport «contrôle qualité / coût et délai».
- Utiliser des points de contrôle bloquants là où un échec doit empêcher la progression (merge ou déploiement).

Intégration par niveau

| **Niveau** | **Étape du pipeline** | **Point de contrôle (bloquant)** | **Déclencheur** | **Objectif** |
|------------|-----------------------|-------------------------------|------------------|-------------|
| Config TAF/TAS | Build | Oui | à chaque push/PR | Fail‑fast (chemins/fichiers/configs valides) |
| Composant | Build | Oui | à chaque push/PR | Qualité des unités/bibliothèques |
| Intégration composant | Build/Intégration | Oui (si bas niveau) | à chaque push/merge | Interfaces entre composants |
| Système | Déploiement (CD) | Oui (si bloque release) | au déploiement | Dernier garde‑fou du SUT |
| Intégration système / Acceptation | Livraison | Oui/Non (contexte) | à la livraison | Fonctionnement bout‑à‑bout |

Modes d’intégration des tests système/acceptation
1) En phase de déploiement (bloquant): échec ⇒ déploiement annulé/rollback; limite: relancer implique redéployer.
2) Pipeline séparé (non bloquant): utile si suites longues/variées; prévoir une procédure de rollback/feature‑flag.

Exécutions périodiques
- Régression nocturne (suites longues) pour fournir un état de santé chaque matin.
- Non‑fonctionnels (ex. performance) en continu ou en pipeline dédié pour la surveillance.

À retenir
- Placer les tests là où ils protègent au meilleur coût; rendre bloquants ceux qui doivent empêcher la progression.
- Choisir déploiement (bloquant) vs pipeline séparé (non bloquant) selon l’enjeu et la durée.
- Programmer des exécutions périodiques pour la régression longue et les non‑fonctionnels.

Bonnes pratiques (5.1.1)
- Tests rapides en build; lents/longs hors chemin critique (mais référencés).
- Quality gates explicites (seuils, critères d’échec, ownership).
- Environnements éphémères, artefacts immuables, données seed contrôlées.

Anti‑patterns (5.1.1)
- Tout miser sur des E2E lents et fragiles.
- Absence de gates (tests “informés” mais non bloquants par erreur).
- Flaky non traités, envs partagés et non isolés.

**→ Transition :** Une fois le placement défini, il faut garantir que l’automatisation tourne partout: place à la **gestion de la configuration**.

### **5.1.2 (K2) : Expliquer la gestion de configuration pour les testware**

Contexte/Problème/Objectif/Solution
- Contexte: mêmes tests, environnements et versions multiples.
- Problème: dérive de config/données → échecs non reproductibles.
- Objectif: portabilité et traçabilité du testware.
- Solution: checklists Env/Données/Suites + versioning.

Checklists de configuration

Environnements
- URLs, credentials et secrets externalisés (pas dans le code)
- Conventions de nommage, variables standardisées, stockage versionné
- Environnements éphémères quand possible

Données de test
- Jeux par environnement/release, stratégie seed/refresh
- Anonymisation/pseudonymisation si données réelles
- Ownership clair et traçabilité des datasets

Suites de tests
- Suites taggées par objectif: smoke, régression, acceptation, non‑fonctionnels
- Mapping suites ↔ étapes du pipeline
- Temps cible par suite (rapide vs longue)

Stratégies de versioning
- Feature toggles: pour activer/neutraliser des features selon release/env
- Versioning aligné SUT↔testware via tags/branches quand compatibilité stricte

**→ Transition :** La configuration étant en place, la fiabilité en architectures API dépend des **dépendances**: contrats, auth, données et observabilité.

### **5.1.3 (K2) : Expliquer les dépendances pour une infrastructure API**

Contexte/Problème/Objectif/Solution
- Contexte: microservices, interfaces inter‑équipes, fournisseurs.
- Problème: intégrations instables sans contrats/données/observabilité.
- Objectif: fiabilité mesurable des tests API.
- Solution: checklist dépendances + contract testing opérationnel.

Checklist dépendances API
- Contrats (OpenAPI/AsyncAPI) versionnés et partagés
- Authentification/autorisation (modes, scopes) documentées
- Idempotence, limites, timeouts, ordonnancement d’appels
- Mocks/stubs/virtualisation disponibles pour intégration
- Données seed de référence et jeux contrôlés
- Observabilité: logs corrélables, métriques, traces

Contract testing (quand/comment)
- Quand: microservices, interfaces inter‑équipes, fournisseurs externes, SLA stricts.
- Consumer‑driven: besoins client priment; Provider‑driven: surface stable, forte réutilisation.
- “Done”: contrat versionné + vérifié en CI; rupture de contrat = gate fail.

Exemple end‑to‑end (compact)
- PR: unit + config (gate < 10 min).
- Merge: intégration composant (gate < 15 min).
- Deploy: smoke système (gate), rollback auto si échec.
- Nuit: régression longue + perf (non‑gate), rapports au matin.

Mini‑glossaire (chapitre)
- Gate: test bloquant qui empêche merge/déploiement s’il échoue.
- Delivery vs Deploy: livraison (release) vs déploiement (mise en env).
- Éphémère: environnement recréé à chaque exécution.
- Artefact immuable: build signé, non modifié après création.
- Seed: initialisation contrôlée des données de test.
- Contract testing: vérifie qu’un service respecte les interactions convenues.

## Chapitre 6 : Reporting et métriques (150 minutes - K4)

### Objectifs

En apprendre plus sur :

- Les sources de données (SUT et Automatisation) pour l'analyse et le reporting
- L'analyse des données pour découvrir les causes des défaillances
- L'utilisation des rapports de test et tableaux de bord pour informer les parties prenantes

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

### Objectifs

En apprendre plus sur :

- L'examen et la vérification du bon fonctionnement des composants et de l'environnement d'Automatisation des tests
- Les mesures pour s'assurer que les scripts et suites de tests s'exécutent correctement
- Le moment où effectuer une analyse des causes racines
- Les techniques d'analyse de la qualité du code d'Automatisation des tests

### **Mots-clés**
- analyse statique

### **Objectifs d'apprentissage**

#### 7.1 Vérification de l'infrastructure d'Automatisation des tests
- **TAE-7.1.1 (K3)** : Planifier la vérification de l'environnement d'Automatisation des tests, y compris la configuration des outils de test
- **TAE-7.1.2 (K2)** : Expliquer le comportement correct pour un script de test automatisé donné et/ou une suite de tests
- **TAE-7.1.3 (K2)** : Identifier les cas où l'Automatisation des tests produit des résultats inattendus
- **TAE-7.1.4 (K2)** : Expliquer comment l'analyse statique peut contribuer à la qualité du code d'Automatisation des tests

## Chapitre 8 : Amélioration continue (210 minutes - K4)

### Objectifs

En apprendre plus sur :

- D'autres domaines d'analyse de données pour l'amélioration des cas de test
- Les façons d'apporter des améliorations et des mises à niveau à une solution d'Automatisation des tests et à ses composants
- L'identification et les moyens de consolider et rationaliser l'Automatisation des tests
- La contribution des outils d'Automatisation des tests au soutien et à la mise en place des tests

### **Mots-clés**
- validation de schéma
- histogramme de test

### **Objectifs d'apprentissage**

#### 8.1 Possibilités d'amélioration continue de l'Automatisation des tests
- **TAE-8.1.1 (K3)** : Découvrir les opportunités d'amélioration des cas de test par la collecte et l'analyse de données
- **TAE-8.1.2 (K4)** : Analyser les aspects techniques d'une solution d'Automatisation des tests déployée et fournir des recommandations d'amélioration
- **TAE-8.1.3 (K3)** : Restructurer le testware automatisé pour l'aligner sur les mises à jour du SUT
- **TAE-8.1.4 (K2)** : Résumer les opportunités d'utilisation des outils d'Automatisation des tests
