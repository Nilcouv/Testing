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