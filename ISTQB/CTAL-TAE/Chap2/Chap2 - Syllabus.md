# Chapitre 2

## Syllabus - 2 Se préparer à l'Automatisation des tests – 180 minutes (K4)

### Mots clés

Tests d'API, tests de l'interface graphique, testabilité

### Objectifs d'apprentissage pour le chapitre 2

- **2.1** Comprendre la configuration d'une infrastructure permettant l'Automatisation des tests
  - **TAE-2.1.1** (K2) Décrire les besoins de configuration d'une infrastructure permettant l'implémentation de l'Automatisation des tests.
  - **TAE-2.1.2** (K2) Expliquer comment l'Automatisation des tests est exploitée dans différents environnements.
- **2.2** Processus d'évaluation pour sélectionner les bons outils et les bonnes stratégies
  - **TAE-2.2.1** (K4) Analyser un système sous test pour déterminer la solution d'Automatisation des tests appropriée.
  - **TAE-2.2.2** (K4) Illustrer les constatations techniques d'une évaluation d'outil.

## 2.1 Comprendre la configuration d'une infrastructure permettant l'Automatisation des tests

### 2.1.1 Décrire les besoins de configuration d'une infrastructure permettant l'implémentation de l'Automatisation des tests

La testabilité du SUT (c'est-à-dire la disponibilité d'interfaces logicielles qui soutiennent les tests, par exemple pour permettre le contrôle et l'observabilité du SUT) devrait être conçue et implémentée parallèlement à la conception et à l'implémentation des autres caractéristiques du SUT. Ce travail est généralement effectué par un architecte logiciel car la testabilité est une exigence non fonctionnelle du système. Il est souvent accompagné d'un TAE pour identifier les domaines spécifiques où des améliorations peuvent être apportées.

Pour une meilleure testabilité du SUT, il existe différentes solutions qui peuvent être utilisées et qui ont des besoins de configuration différents, par exemple :

- **Identifiants d'accessibilité**
  - Les différents frameworks de développement peuvent générer ces identifiants automatiquement ou les développeurs peuvent les définir manuellement.
- **Variables d'environnement du système**
  - Certains paramètres de l'application peuvent être modifiés pour permettre de tester plus facilement l'application par le biais de l'administration.
- **Variables de déploiement**
  - Similaires aux variables du système, mais qui peuvent être définies avant de commencer le déploiement.

La conception de la testabilité d'un SUT comprend les aspects suivants :

- **Observabilité** : Le SUT doit fournir des interfaces qui donnent un aperçu du SUT. Les cas de test peuvent alors utiliser ces interfaces pour déterminer si les résultats réels correspondent aux résultats attendus.
- **Contrôlabilité** : Le SUT doit fournir des interfaces qui peuvent être utilisées pour effectuer des actions sur celui-ci. Il peut s'agir d'éléments d'interface utilisateur, d'appels de fonction, d'éléments de communication (par exemple, protocole de contrôle de transmission/protocole Internet (TCP/IP) et protocoles de bus série universel (USB)) ou de signaux électroniques pour des commutateurs physiques ou logiques sur les différentes variables d'environnement.
- **Transparence de l'architecture** : La documentation d'une architecture doit fournir des composants et des interfaces clairs et compréhensibles qui donnent une observabilité et un contrôle à tous les niveaux de test et favorisent la qualité.

### 2.1.2 Expliquer comment l'Automatisation des tests est exploitée au sein de différents environnements

Différents types de tests automatisés peuvent être exécutés dans différents environnements. Ces environnements peuvent différer selon les projets et les méthodologies, et la plupart des projets disposent d'un ou plusieurs environnements utilisés pour tester. D'un point de vue technique, ces environnements peuvent être créés à partir de conteneurs, de logiciels de virtualisation et d'autres approches.

Voici une série d'environnements possibles à prendre en considération :

#### Environnement de développement local

L'environnement de développement local est l'endroit où le logiciel est initialement créé et où les composants sont testés par automatisation pour vérifier leur aptitude fonctionnelle. Plusieurs types de tests peuvent être effectués dans l'environnement de développement local, notamment des tests de composants, des tests d'interface graphique et des tests d'interface de programmation d'applications (API).

Il est également important de noter qu'en utilisant un environnement de développement intégré (IDE) sur l'ordinateur donné, des tests boîte blanche peuvent être effectués afin d'identifier le plus tôt possible les problèmes de codage et de qualité médiocre.

#### Environnement de Build

Son objectif principal est de construire le logiciel (NDT: build) et d'exécuter des tests qui vérifient l'exactitude de la construction résultante dans un écosystème DevOps. Cet environnement peut être soit un environnement de développement local, soit un agent d'intégration continue/de livraison continue (CI/CD) où les tests de bas niveau (c'est-à-dire les tests de composants et les tests d'intégration continue des composants) et l'analyse statique peuvent être effectués sans déploiement réel dans d'autres environnements.

#### Environnement d'intégration

Après les tests de bas niveau et l'analyse statique, l'étape suivante est un environnement d'intégration des systèmes. Il s'agit d'un candidat à la release du SUT qui est entièrement intégré à d'autres systèmes pouvant être testés. Dans cet environnement, une suite de tests entièrement automatisée, soit des tests d'interface utilisateur, soit des tests d'API, peut être exécutée. Dans cet environnement, il n'y a pas de tests boîte blanche, mais uniquement des tests boîte noire (c'est-à-dire des tests d'intégration des systèmes et/ou des tests d'acceptation). Il est important de noter qu'il s'agit du premier environnement où une surveillance (NDT : monitoring) devrait être présente pour voir ce qui se passe en arrière-plan pendant l'utilisation du SUT afin de permettre une investigation efficiente des défauts/défaillances.

#### Environnement de préproduction

Un environnement de préproduction est utilisé principalement pour auditer les caractéristiques de qualité non fonctionnelles (par exemple, l'efficience de la performance). Bien que les tests non fonctionnels puissent être réalisés dans n'importe quel environnement, l'accent est mis sur la préproduction parce qu'elle ressemble le plus possible à la production. Souvent, les tests d'acceptation des utilisateurs peuvent être effectués par les parties prenantes Métier pour vérifier le produit final et il est possible d'exécuter la suite automatisée de tests existante ici aussi, si nécessaire. Cet environnement est également surveillé.

#### Environnement de production/d'exploitation

Un environnement de production peut être utilisé pour évaluer les caractéristiques de qualité fonctionnelles et non fonctionnelles en temps réel pendant que les utilisateurs interagissent avec un système déployé grâce au suivi et à certaines meilleures pratiques qui permettent les tests en production (par exemple, la release canari, le déploiement bleu/vert et les tests A/B).

## 2.2 Processus d'évaluation pour sélectionner les bons outils et stratégies

### 2.2.1 Analyser un système sous test pour déterminer la solution d'Automatisation des tests appropriée

Chaque SUT peut être différent d'un autre, mais il y a plusieurs facteurs et caractéristiques qui peuvent être analysés pour avoir une solution d'Automatisation des tests (TAS) réussie. Au cours de l'étude d'un SUT, les TAE doivent rassembler les exigences en tenant compte de son périmètre et de ses capacités données. Différents types d'applications (par exemple, service Web, mobile et Web) nécessitent différents types d'Automatisation des tests d'un point de vue technique. L'enquête peut être effectuée - c'est recommandé - en collaboration avec d'autres parties prenantes (par exemple, les testeurs manuels, les parties prenantes métier et les analystes métier) pour identifier autant de risques et leurs atténuations que possible afin d'avoir une solution d'Automatisation des tests bénéfique pour l'avenir.

Les exigences d'une approche d'Automatisation des tests et d'une architecture d'Automatisation des tests doivent prendre en compte les éléments suivants :

- Quelles activités du processus de test doivent être automatisées, (par exemple, la gestion des tests, la conception des tests, la génération des tests et l'exécution des tests).
- Quels niveaux de test doivent être soutenus ?
- Quels types de tests doivent être soutenus ?
- Quels rôles et compétences en matière de tests doivent être soutenus ?
- Quels produits, lignes de produits et familles de logiciels doivent être soutenus (par exemple, pour définir l'étendue et la durée de vie du SAE implémenté ?
- Quels types de SUT doivent être compatibles avec la TAS ?
- Quelle est la disponibilité des données de test et quelle est leur qualité ?
- Quelles sont les méthodes possibles et les moyens d'émuler des cas inaccessibles (par exemple, les applications tierces concernées) ?

### 2.2.2 Illustrer les constatations techniques d'une évaluation d'outil

Après l'analyse du SUT et la collecte des exigences auprès de toutes les parties prenantes, il est probable que des outils d'Automatisation des tests répondant à ces exigences puissent être envisagés. Il se peut qu'il n'y ait pas un seul outil qui réponde à toutes les exigences identifiées, et les parties prenantes devraient reconnaître cette possibilité.

Il est utile de rassembler les constatations sur les outils possibles et de réfléchir aux diverses exigences directes et indirectes dans un tableau comparatif. L'objectif du tableau de comparaison est de permettre aux parties prenantes de voir les différences entre les outils sur la base d'exigences spécifiques. Le tableau de comparaison présente les outils dans les colonnes et les exigences dans les lignes. Les cellules contiennent des informations sur les propriétés de chaque outil par rapport à chaque exigence ainsi que sur les priorités.

En général, les outils d'Automatisation des tests doivent être évalués pour déterminer s'ils répondent à l'exigence identifiée dans la section précédente (2.2.1). Les exigences à prendre en compte lors de l'évaluation et de la comparaison des outils comprennent :

- Le langage/la technologie de l'outil et les outils IDE.
- La capacité à configurer un outil, qu'il soutienne différents environnements de test, qu'il exécute des configurations et qu'il utilise des valeurs de configuration dynamiques ou statiques.
- La capacité à gérer les données de test au sein de l'outil. La gestion des données de test pourrait être intégrée à un référentiel central pour le contrôle des versions.
- La nécessité éventuelle de devoir sélectionner différents outils d'Automatisation des tests pour différents types de tests.
- La capacité à fournir des fonctionnalités de reporting. Ceci est important pour s'aligner sur les exigences du projet en matière de reporting des tests.
- La capacité à s'intégrer à d'autres outils utilisés sur un projet ou dans l'organisation, tels que CI/CD, le suivi des tâches, la gestion des tests, le reporting ou d'autres outils.
- La capacité d'étendre l'architecture de test globale et d'évaluer l'évolutivité, la maintenabilité, la facilité de modification, la compatibilité et la fiabilité des outils.

Ce tableau de comparaison est une bonne source pour déterminer une proposition d'outil ou d'ensemble d'outils à utiliser pour l'Automatisation des tests du SUT.

Le processus peut varier quant à la manière dont la décision est prise sur le(s) outil(s) à utiliser, mais la proposition doit être présentée aux parties prenantes appropriées pour approbation.