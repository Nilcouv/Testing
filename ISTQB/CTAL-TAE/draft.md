&# Chapter 5: Implementation and Deployment Strategies for Test
Automation – 90 minutes (K3)

## Glossaire

### Termes du chapitre (à connaître pour l'examen)

| **Terme** | **Définition** |
|-----------|----------------|
| **contract testing** | Type de test d'intégration vérifiant que des services peuvent communiquer entre eux et que les données partagées sont cohérentes avec un ensemble de règles spécifiées. Fournit la compatibilité entre deux systèmes séparés (ex: microservices). Va au-delà de la validation de schéma en exigeant un consensus sur les interactions autorisées tout en permettant l'évolution. |

### Termes complémentaires (pour la compréhension)

| **Terme** | **Définition** |
|-----------|----------------|
| **pipeline CI/CD** | Chaîne automatisée d'étapes (construction, tests, déploiement) que le code traverse du développement à la production. |
| **testware** | Ensemble des artefacts produits lors des tests (scripts de test, données de test, configurations d'environnement, suites de tests). |
| **quality gate** | Point de contrôle dans le pipeline où les tests déterminent si le déploiement peut continuer ou doit être bloqué. |
| **feature toggle** | Configuration permettant d'activer/désactiver des fonctionnalités pour gérer quelles suites de tests exécuter sur un environnement ou une release donnée. |
| **continuous integration (CI)** | Pratique de développement où les membres d'une équipe intègrent leur travail fréquemment, généralement plusieurs fois par jour, avec vérification automatique. |
| **continuous deployment (CD)** | Pratique où chaque changement de code qui passe les étapes de validation automatisées est automatiquement déployé en production. |
| **rollback** | Processus de retour à une version précédente d'une application en cas de problème avec la version déployée. |
| **consumer-driven contract** | Approche de contract testing où le consommateur d'un service définit les attentes sous forme de contrat que le fournisseur doit respecter. |
| **provider-driven contract** | Approche de contract testing où le fournisseur d'un service définit le contrat que les consommateurs doivent suivre. |

## Objectifs d'apprentissage

**5.1 Integration to CI/CD Pipelines**

- **TAE-5.1.1 (K3)** Apply test automation at different test levels within pipelines
- **TAE-5.1.2 (K2)** Explain configuration management for testware
- **TAE-5.1.3 (K2)** Explain test automation dependencies for an API infrastructure

## Introduction : L'automatisation au service de la livraison continue

### Le défi de l'automatisation continue

Automatiser des tests est une première étape. Mais les intégrer dans un processus de **livraison continue** en est une autre : les tests doivent s'exécuter automatiquement, sans surveillance humaine, à chaque changement de code, sur différents environnements, et fournir un feedback rapide et fiable.

**Trois défis stratégiques émergent :**

1. **Où placer les tests ?** → Un test de composant au bon moment accélère le feedback ; au mauvais moment, il ralentit le pipeline.
2. **Comment garantir la portabilité ?** → Les mêmes tests doivent fonctionner sur dev, test, staging et production sans modification manuelle.
3. **Comment gérer les dépendances ?** → Dans une architecture moderne (microservices, APIs), un service dépend d'autres services : comment tester sans bloquer les équipes ?

### Pipeline CI/CD : rappel du concept

Un **pipeline CI/CD** est une chaîne automatisée qui transforme le code source en application déployée :

```
Code → Build → Tests → Déploiement → Production
```

**Analogie terrain :** Imaginez une chaîne de montage automobile. Chaque étape vérifie un aspect (moteur, freins, carrosserie). Si un contrôle échoue, la voiture ne passe pas à l'étape suivante. Le pipeline CI/CD fonctionne pareil : chaque niveau de test est un **quality gate** (point de contrôle bloquant).

### Pourquoi ce chapitre maintenant ?

Les chapitres précédents ont construit les fondations (architecture TAF, patterns, pilote). Ce chapitre traite le **déploiement opérationnel** :

- **5.1.1** → **Placement stratégique** : À quelle étape du pipeline exécuter chaque niveau de test ?
- **5.1.2** → **Configuration adaptable** : Comment faire tourner les mêmes tests sur tous les environnements ?
- **5.1.3** → **Dépendances maîtrisées** : Comment tester des APIs interdépendantes sans bloquer le développement ?

**Fil conducteur :** Transformer une collection de scripts automatisés en un système de **qualité continue**, intégré au flux de développement, traçable et fiable.

---

## 5.1 Integration to CI/CD Pipelines
5.1.1 Apply Test Automation at Different Test Levels within Pipelines
One of the main benefits of test automation is that the implemented tests can run unattended, making
them ideal candidates to run within pipelines. This can be accomplished through CI/CD pipelines, or the
pipeline used to run the tests regularly.
Test levels are usually integrated as follows:
● Configuration tests for TAF/TAS, during build can be considered as a subspecies of component
tests. These tests are run during the build of a test automation project (TAF/TAS) and check that
all paths to the files used in the test scripts are correct, that the files really exist and are located in
the specified paths.
● Component tests are part of the build step of the pipeline, as they are executed on the individual
components, (e.g., library classes, and web components). They act as quality gates for the
pipeline, thus a crucial part of a continuous integration pipeline.
● Component integration tests can be part of the continuous integration pipeline if they are tests of
low-level components or the SUT. In such cases, these tests and the component tests are
executed together.
● System tests can often be integrated into a continuous deployment pipeline, where they act as
the last quality gate of the delivered SUT.
● System integration tests between different system components are often part of a continuous
delivery pipeline as quality gates. These system integration tests ensure that the separately
developed system components are working together.
Many modern continuous integration systems differentiate between build and deployment phases of the
continuous delivery pipelines. In these cases, component tests and component integration tests are part
of the first build phase. When this first phase is successful (i.e., build and test together), the
components/SUT are deployed.
In case of system integration testing, system testing and acceptance testing, there are two main
approaches to integrate them into such pipelines:
1. Test cases are executed as part of the deployment phase after the component deployment. This
can be beneficial, as based on the test results, the deployment can fail and also be rolled back.
However, in this case, if tests need to be rerun, a redeployment needs to be done.
2. Test cases are executed as a separate pipeline, triggered by the successful deployment. This can
be beneficial if it is expected that different test suites and various test automation code will run on
each deployment. In this case, tests do not act as a quality gate. Thus, it requires other, usually
manual, actions to roll back an unsuccessful deployment.
In this case, a few simple automated test scripts, as deployment checks, can be used to ensure
the SUT is deployed, but these automated test scripts do not verify functional suitability in a broad
manner.
Pipelines can also be used for other test automation purposes, such as:
● Running different test suites periodically: A regression test suite can be run every night (i.e., the
nightly regression), especially for longer running test suites, so the team will have a clear picture
of the quality of the SUT in the morning.
● Running non-functional tests: Either part of a continuous deployment pipeline, or separately, to
periodically monitor certain non-functional quality characteristics of the system such as
performance efficiency
5.1.2 Explain Configuration Management for Testware
Configuration management is an integral part of test automation, as automation will often be executed on
multiple test environments and versions of the SUT.
Configuration management in test automation includes:
● Test environment configuration
● Test data
● Test suites/test cases
Test environment configuration
Each test environment used in the development pipeline can have different configurations, such as
various URLs or credentials. The test environment configuration is usually stored with the testware.
However, in the case of test automation used on multiple projects or multiple TAFs for the same project,
the test environment configuration can be part of the common core library or in a shared repository.
Test data
Test data can also be specific for the test environment or for the release and the feature set of the SUT.
As with the test environment configuration, test data is usually stored with smaller TAFs, but test data
management systems can also be used.
Test suites/test cases
A common practice is to set up different test suites of the test cases, based on their purpose, such as
smoke testing or regression testing. These test suites are often executed in separate test levels,
leveraging different pipelines and test environments.
Each release of the SUT determines a feature set which includes test cases and test suites that assess
the quality of the given release. There are different options in the testware to handle this:
● A feature toggle configuration can be defined per each release or test environment. There are
test cases and test suites to test each feature. The feature toggle can be used in the testware to
identify which test suites to execute on a given release/test environment.
● The testware can also be released with the SUT using the same release version. In this way,
there is an exact match between the SUT version and the testware that can test it. Such a
release is usually implemented using a configuration management system using tags or
branches.
5.1.3 Explain Test Automation Dependencies for an API Infrastructure
When performing API test automation, it is crucial to have the following information about dependencies
to build a proper strategy:
● API connections: Understand the business logic that can be tested automatically and the
relationship between APIs
● API documentation: Serves as a baseline for test automation with all relevant information (e.g.,
parameters, headers, and distinct types of request-response of objects)
Integrated automated API testing can be done by either the developers or the TAEs. However, with shift
left it is recommended to support and divide the testing among different levels. In the ISTQB CTFL
Syllabus, component integration testing and system integration testing are mentioned which can be
extended with a best practice called contract testing.
Contract testing
Contract testing is a type of integration testing verifying that services can communicate with each other,
and that the data shared between the services is consistent with a specified set of rules. Using contract
testing provides compatibility across two separate systems (e.g., two microservices) to communicate with
one another. It goes beyond schema validation, requiring both parties to come to a consensus on the
allowed set of interactions while providing for evolution over time. It captures the interactions that are
exchanged between each service, storing them in a contract, which can then be used to verify that both
parties adhere to it. One of the main advantages of this test type is that defects occurring from underlying
services can be found earlier in the SDLC and the source of these defects can be more easily identified.
In the consumer-driven approach to contract testing, the consumer sets its expectation determining how
the provider shall respond to requests coming from this consumer. In the provider-driven approach to
contract testing, the provider creates the contract, which shows how its services are operating.