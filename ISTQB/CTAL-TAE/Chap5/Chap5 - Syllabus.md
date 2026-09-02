# Chapitre 5

## Syllabus - 5 Stratégies d'implémentation et de déploiement de l'Automatisation des tests – 90 minutes (K3)

### Mots clés

test de contrat

### Objectifs d'apprentissage pour le chapitre 5

- **5.1** Intégration aux pipelines CI/CD
  - **TAE-5.1.1** (K3) Appliquer l'Automatisation des tests à différents niveaux de test dans les pipelines.
  - **TAE-5.1.2** (K2) Expliquer la gestion de configuration pour les testware.
  - **TAE-5.1.3** (K2) Expliquer les dépendances de l'Automatisation des tests pour une infrastructure API.

## 5.1 Intégration aux pipelines CI/CD

### 5.1.1 Appliquer l'Automatisation des tests à différents niveaux de test dans les pipelines

L'un des principaux avantages de l'Automatisation des tests est que les tests implémentés peuvent s'exécuter sans surveillance, ce qui en fait des candidats idéaux pour être exécutés au sein de pipelines. Cela peut se faire par le biais de pipelines CI/CD, ou du pipeline utilisé pour exécuter les tests régulièrement.

Les niveaux de test sont généralement intégrés comme suit :

- Les tests de configuration pour TAF/TAS, pendant le build, peuvent être considérés comme une sous-espèce de tests de composants. Ces tests sont exécutés pendant le build d'un projet d'Automatisation des tests (TAF/TAS) et vérifient que tous les chemins d'accès aux fichiers utilisés dans les scripts de test sont corrects, que les fichiers existent réellement et qu'ils se trouvent dans les chemins d'accès spécifiés.
- Les tests de composants font partie de l'étape de build du pipeline, car ils sont exécutés sur les composants individuels (par exemple, les classes de bibliothèque et les composants web). Ils agissent comme des points de contrôle de qualité pour le pipeline, et constituent donc une partie cruciale d'un pipeline d'intégration continue.
- Les tests d'intégration des composants peuvent faire partie du pipeline d'intégration continue s'il s'agit de tests de composants de bas niveau ou du SUT. Dans ce cas, ces tests et les tests de composants sont exécutés ensemble.
- Les tests système peuvent souvent être intégrés dans un pipeline de déploiement continu, où ils font office de dernier point de contrôle qualité du SUT livré.
- Les tests d'intégration entre les différents composants du système font souvent partie d'un pipeline de livraison continue en tant que points de qualité. Ces tests d'intégration du système garantissent que les composants du système développés séparément fonctionnent ensemble.

De nombreux systèmes modernes d'intégration continue font la distinction entre les phases de build et de déploiement des pipelines de livraison continue. Dans ce cas, les tests de composants et les tests d'intégration de composants font partie de la première phase de build. Lorsque cette première phase est réussie (c'est-à-dire que le build et les tests se déroulent ensemble), les composants/SUT sont déployés.

Dans le cas des tests d'intégration des systèmes, des tests système et des tests d'acceptation, il existe deux approches principales pour les intégrer dans ces pipelines :

1. Les cas de test sont exécutés dans le cadre de la phase de déploiement après le déploiement du composant. Cela peut être bénéfique, car sur la base des résultats des tests, le déploiement peut échouer et également être annulé. Toutefois, dans ce cas, si les tests doivent être réexécutés, il faut procéder à un redéploiement.
2. Les cas de test sont exécutés en tant que pipeline distinct, déclenché par la réussite du déploiement. Cela peut être bénéfique si l'on s'attend à ce que différentes suites de tests et divers codes d'automatisation des tests soient exécutés à chaque déploiement. Dans ce cas, les tests n'agissent pas comme un point de contrôle qualité. Il faut donc d'autres actions, généralement manuelles, pour revenir sur un déploiement qui n'a pas abouti.

Dans ce cas, quelques scripts de tests automatisés simples peuvent être utilisés, en tant que contrôles de déploiement, pour s'assurer que le SUT est déployé, mais ces scripts de tests automatisés ne vérifient pas l'aptitude fonctionnelle d'une manière générale.

Les pipelines peuvent également être utilisés à d'autres fins d'Automatisation des tests, telles que :

- Exécuter périodiquement différentes suites de tests : une suite de tests de régression peut être exécutée chaque nuit (c'est-à-dire la régression nocturne), en particulier pour les suites de tests de longue durée, de sorte que l'équipe aura une image claire de la qualité du SUT le matin.
- Exécuter des tests non fonctionnels : soit dans le cadre d'un pipeline de déploiement continu, soit séparément, pour surveiller périodiquement certaines caractéristiques de qualité non fonctionnelles du système, telles que l'efficience des performances.

### 5.1.2 Expliquer la gestion de la configuration pour les testware

La gestion de la configuration fait partie intégrante de l'Automatisation des tests, car l'automatisation sera souvent exécutée sur plusieurs environnements de test et versions du SUT.

La gestion de la configuration dans l'Automatisation des tests comprend :

- La configuration de l'environnement de test.
- Les données de test.
- Les suites de tests/cas de tests.

#### Configuration de l'environnement de test

Chaque environnement de test utilisé dans le pipeline de développement peut avoir des configurations différentes, telles que diverses URL ou informations d'identification. La configuration de l'environnement de test est généralement stockée avec le testware. Toutefois, dans le cas d'une Automatisation des tests utilisée sur plusieurs projets ou de plusieurs TAFs pour le même projet, la configuration de l'environnement de test peut faire partie de la bibliothèque principale commune ou d'un référentiel partagé.

#### Données de test

Les données de test peuvent également être spécifiques à l'environnement de test ou à la version et au jeu de caractéristiques du SUT. Comme pour la configuration de l'environnement de test, les données de test sont généralement stockées dans des TAFs plus petits, mais des systèmes de gestion des données de test peuvent également être utilisés.

#### Suites de tests/cas de tests

Une pratique courante consiste à mettre en place différentes suites de tests pour les cas de test, en fonction de leur objectif, comme les « smoke tests » ou les tests de régression. Ces suites de tests sont souvent exécutées à des niveaux de tests distincts, en tirant parti de différents pipelines et environnements de tests.

Chaque version du SUT détermine un ensemble de caractéristiques qui comprend des cas de tests et des suites de tests qui permettent d'évaluer la qualité de la version en question. Il existe différentes options dans le testware pour gérer cela :

- Une configuration de basculement des caractéristiques peut être définie pour chaque version ou environnement de test. Il existe des cas de test et des suites de tests pour tester chaque caractéristique. La bascule de caractéristiques peut être utilisée dans le testware pour identifier les suites de tests à exécuter sur une version/un environnement de tests donné(e).
- Le testware peut également être versionné avec le SUT en utilisant la même version. De cette manière, il y a une correspondance exacte entre la version du SUT et le testware qui peut le tester. Une telle version est généralement implémentée à l'aide d'un système de gestion des livraisons utilisant des balises ou des branches.

### 5.1.3 Expliquer les dépendances de l'Automatisation des tests pour une infrastructure API

Lors de l'Automatisation des tests d'API, il est crucial de disposer des informations suivantes sur les dépendances pour construire une stratégie adéquate :

- **Connexions API** : faciliter la compréhension de la logique métier qui peut être testée automatiquement et de la relation entre les APIs.
- **Documentation API** : servir de ligne de base pour l'Automatisation des tests avec toutes les informations pertinentes (par exemple, les paramètres, les en-têtes et les types distincts de demande/réponse des objets).

Les tests automatisés intégrés de l'API peuvent être réalisés soit par les développeurs, soit par les TAE. Toutefois, avec le shift-left, il est recommandé de soutenir et de répartir les tests entre différents niveaux.

Le syllabus CTFL de l'ISTQB mentionne les tests d'intégration des composants et les tests d'intégration des systèmes, qui peuvent être étendus à l'aide d'une meilleure pratique appelée « test de contrat ».

#### Test de contrat

Le test de contrat est un type de test d'intégration vérifiant que les services peuvent communiquer entre eux et que les données partagées entre les services sont conformes à un ensemble de règles spécifiées.

L'utilisation des tests de contrat permet d'assurer la compatibilité entre deux systèmes distincts (par exemple, deux micro-services) pour qu'ils communiquent l'un avec l'autre. Il va au-delà de la validation des schémas, exigeant que les deux parties parviennent à un consensus sur l'ensemble des interactions autorisées tout en prévoyant une évolution dans le temps. Il capture les interactions qui sont échangées entre chaque service et les stocke dans un contrat, qui peut ensuite être utilisé pour vérifier que les deux parties y adhèrent. L'un des principaux avantages de ce type de test est que les défauts provenant des services sous-jacents peuvent être trouvés plus tôt dans le cycle de développement durable et que la source de ces défauts peut être plus facilement identifiée.

Dans l'approche de test de contrat pilotée par le consommateur, le consommateur définit ses attentes en déterminant comment le fournisseur doit répondre à ses demandes. Dans l'approche de test de contrat pilotée par le fournisseur, ce dernier crée le contrat, qui indique comment ses services fonctionnent.
