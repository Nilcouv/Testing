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

### **Mots-clés**

| **Mot** | **Définition** |
|---------------|-----------------|
| **système sous test** | Système qui est testé pour un fonctionnement correct. Selon ISTQB, il s'agit de l'objet de test. |
| **Automatisation des tests** | Utilisation de logiciels pour effectuer ou soutenir les activités de test, par exemple la gestion des tests, la conception des tests, l'exécution des tests et la vérification des résultats. |
| **ingénieur en Automatisation des tests** | Professionnel spécialisé dans la conception, le développement et la maintenance de solutions d'automatisation des tests. |

### 1.1 Objectif de l'Automatisation des tests

#### **TAE-1.1.1 (K2)** : Expliquer les avantages et les inconvénients de l'Automatisation des tests

L'Automatisation des tests comprend :
- l'**utilisation d'outils logiciels** pour contrôler et mettre en place des suites de tests,
- l'**exécution automatisée** des tests,
- la **comparaison automatique** des résultats réels aux résultats attendus.

Cette approche couvre divers types de SUT (System avec/sans UI, applications mobiles, protocoles réseau) et va au-delà des simples "frameworks" pour constituer un écosystème complet d'outils incluant l'établissement automatisé de rapports.

| **AVANTAGES** | **Description** | **Exemple concret** |
|---------------|-----------------|-------------------|
| **Plus de tests par build** | Exécution massive automatisée | 5000 tests vs 50 manuels |
| **Tests impossibles manuellement** | Capacités dépassant l'humain | Tests temps réel <1ms, 10k utilisateurs simultanés |
| **Tests plus complexes** | Scénarios sophistiqués | Intégration multi-systèmes |
| **Rapidité d'exécution** | Vitesse supérieure | 2h vs 40h pour régression |
| **Réduction erreurs humaines** | Élimination variations manuelles | Saisie 1000 jeux de données sans erreur |
| **Efficience des ressources** | Optimisation temps/coût/personnel | 1 TAE remplace 5 testeurs manuels |
| **Feedback rapide** | Retour immédiat sur qualité | Résultats en temps réel |
| **Amélioration fiabilité** | Disponibilité et récupération | Tests de robustesse continus |
| **Cohérence d'exécution** | Standardisation des tests | Même séquence à chaque fois |

| **INCONVÉNIENTS** | **Description** | **Impact** |
|-------------------|-----------------|------------|
| **Coûts supplémentaires** | TAE, matériel, formation | Investissement initial élevé |
| **Temps développement** | Création et maintenance | ROI différé |
| **Objectifs clairs requis** | Définition précise nécessaire | Risque d'échec si flou |
| **Rigidité des tests** | Moins d'adaptabilité | Maintenance lors changements SUT |
| **Défauts supplémentaires** | Bugs dans l'automatisation | Faux positifs/négatifs |

| **LIMITES** | **Description** | **Exemples** |
|-------------|-----------------|--------------|
| **Automatisation partielle** | Tous tests manuels non automatisables | Tests exploratoires, utilisabilité |
| **Portée limitée** | Ne vérifie que ce pour quoi programmé | Pas de découverte fortuite |
| **Oracle machine uniquement** | Résultats interprétables par machine | Pas d'évaluation esthétique/ergonomique |
| **Caractéristiques qualité** | Certains aspects non testables | Intuitivité, ressenti utilisateur |

#### **Analyse comparative des coûts**

L'évolution des coûts entre tests manuels et automatisation suit des trajectoires opposées selon la complexité et la durée de vie du système :

```mermaid
xychart-beta
    title "Évolution des coûts : Tests Manuels vs Automatisation"
    x-axis "Projet" 0 --> 4
    y-axis "Coût" 0 --> 4
    line "Tests Manuels" [0, 0.05, 0.08, 0.1, 0.12, 0.15, 0.18, 0.2, 0.22, 0.25, 0.28, 0.3, 0.32, 0.35, 0.38, 0.4, 0.45, 0.5, 0.6, 0.8, 1.2, 2.0, 3.5, 6.2]
    line "Automatisation" [0, 0.5, 0.8, 1.0, 1.2, 1.35, 1.48, 1.58, 1.67, 1.75, 1.82, 1.88, 1.93, 1.98, 2.02, 2.06, 2.09, 2.12, 2.15, 2.17, 2.19, 2.21, 2.23, 2.24, 2.25, 2.26, 2.27, 2.28]
```

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

```markdown
| Exigence | Outil A | Outil B | Outil C | Priorité |
|----------|---------|---------|---------|----------|
| Compatibilité Java | ✅ | ⚠️ | ❌ | Haute |
| Tests API | ✅ | ✅ | ⚠️ | Haute |
| Intégration CI/CD | ✅ | ✅ | ✅ | Moyenne |
| Coût licence | ❌ | ✅ | ✅ | Moyenne |
| Formation requise | ⚠️ | ✅ | ❌ | Basse |
```

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
