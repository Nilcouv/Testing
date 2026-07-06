# Chapitre 1

## Syllabus - 1 Introduction et objectifs de l'Automatisation des tests – 45 minutes (K-2)

### Mots clés

système sous test, Automatisation des tests, ingénieur en Automatisation des tests

### Objectifs d'apprentissage pour le chapitre 1

- **1.1** Objectif de l'Automatisation des tests
  - **TAE-1.1.1** (K2) Expliquer les avantages et les inconvénients de l'Automatisation des tests.
- **1.2** L'Automatisation des tests dans le cycle de vie du développement logiciel
  - **TAE-1.2.1** (K2) Expliquer comment l'Automatisation des tests est appliquée dans les différents modèles de cycle de vie du développement logiciel.
  - **TAE-1.2.2** (K2) Sélectionner les outils d'Automatisation des tests appropriés pour un système sous test donné.

## 1.1 Objectif de l'Automatisation des tests

### 1.1.1 Expliquer les avantages et les inconvénients de l'Automatisation des tests

L'Automatisation des tests, qui comprend l'exécution automatisée des tests et l'établissement de rapports sur les tests, correspond à une ou plusieurs des activités suivantes :

- Utilisation d'outils logiciels conçus à cet effet pour contrôler et mettre en place des suites de tests pour l'exécution des tests.
- Exécution de tests de manière automatisée.
- Comparaison des résultats réels aux résultats attendus.

L'Automatisation des tests offre des caractéristiques et des capacités significatives qui peuvent interagir avec un système sous test (SUT). L'Automatisation des tests peut couvrir un large domaine des logiciels. Les solutions couvrent de nombreux types de logiciels (par exemple, SUT avec une interface utilisateur (UI), SUT sans UI, applications mobiles, protocoles réseau et connexions).

L'Automatisation des tests présente de nombreux avantages. Elle :

- Permet d'exécuter plus de tests par version (build) par rapport aux tests manuels.
- Offre la possibilité de créer et d'exécuter des tests qui ne peuvent pas être exécutés manuellement (par exemple, réactivité en temps réel, tests à distance et tests en parallèle).
- Permet de réaliser des tests plus complexes que les tests manuels.
- S'exécute plus rapidement que les tests manuels.
- Est moins sujette à l'erreur humaine.
- Est plus efficace et efficiente dans l'utilisation des ressources de test.
- Fournit un retour d'information plus rapide concernant la qualité du SUT.
- Contribue à améliorer la fiabilité du système (par exemple, la disponibilité et la récupération).
- Améliore la cohérence de l'exécution des tests sur l'ensemble des cycles de test.

Cependant, l'Automatisation des tests présente des inconvénients potentiels, notamment :

- Des coûts supplémentaires seront impliqués pour le projet car il peut être nécessaire d'engager un ingénieur en Automatisation des tests (TAE), d'acheter du nouveau matériel et de mettre en place une formation.
- La nécessité d'un investissement initial pour mettre en place une solution d'Automatisation des tests.
- Le temps nécessaire pour développer et maintenir une solution d'Automatisation des tests.
- Le besoin d'objectifs clairs en matière d'Automatisation des tests pour garantir le succès.
- La rigidité des tests, et moins d'adaptabilité aux changements dans le SUT.
- L'introduction de défauts supplémentaires dus à l'Automatisation des tests.

L'Automatisation des tests présente des limites qu'il faut garder à l'esprit :

- Tous les tests manuels ne peuvent pas être automatisés.
- Ne vérifie que ce que les tests automatisés sont programmés pour faire.
- L'Automatisation des tests ne peut vérifier que les résultats des tests interprétables par une machine, ce qui signifie que certaines caractéristiques de qualité peuvent ne pas être testables avec l'automatisation.
- L'Automatisation des tests ne peut vérifier que les résultats du test qui peuvent être vérifiés par un oracle de test automatisé.

## 1.2 L'automatisation dans le cycle de vie de développement logiciel

### 1.2.1 Expliquer comment l'Automatisation des tests est appliquée dans les différents modèles de cycles de vie de développement logiciel

#### Modèle en Cascade

Le modèle en cascade est un modèle SDLC à la fois linéaire et séquentiel. Ce modèle comporte des phases distinctes (exigences, conception, implémentation, vérification et maintenance) et chaque phase se termine généralement par une documentation qui doit être approuvée. L'implémentation de l'Automatisation des tests se fait généralement en parallèle ou après la phase d'implémentation. Les exécutions de test ont généralement lieu pendant la phase de vérification, car les composants logiciels ne sont pas prêts à être testés avant ce moment-là.

#### Modèle en V

Le modèle en V est un modèle de cycle de vie de développement logiciel dans lequel un processus est exécuté de manière séquentielle. Comme un projet est défini depuis les exigences de haut niveau jusqu'aux exigences de bas niveau, les activités de test et d'intégration correspondantes sont définies pour valider ces exigences. C'est de là que découlent les niveaux de test traditionnels : composant, intégration des composants, système, intégration des systèmes et acceptation, comme décrit dans la section 2.2 du syllabus de niveau Fondation. Il est possible et recommandé de fournir un framework d'Automatisation des tests (TAF) pour chaque niveau de test.

#### Développement de logiciel en mode Agile

Dans le développement logiciel en mode Agile, les possibilités d'Automatisation des tests sont innombrables. Contrairement à la cascade ou au modèle V, dans la méthode de développement logiciel en mode Agile, les TAE et les représentants du métier peuvent décider de la feuille de route, du calendrier et de la planification des tests. Dans ces méthodes, il existe de meilleures pratiques telles que les revues de code, la programmation en binôme et l'exécution fréquente de tests automatisés. L'élimination des silos (c'est-à-dire en s'assurant que les développeurs, les testeurs et les autres parties prenantes travaillent ensemble) permet aux équipes de couvrir tous les niveaux de test avec la quantité et la profondeur appropriées d'automatisation, atteignant ainsi un objectif appelé automatisation in-sprint. De plus amples renseignements figurent à la section 3.2. du syllabus CT-TAS (Stratégie d'Automatisation des tests) de l'ISTQB®.

### 1.2.2 Choisir des outils d'Automatisation des tests adaptés à un système sous test donné

Pour identifier les outils de test les plus adaptés à un projet donné, le SUT doit d'abord être analysé. Les TAE doivent identifier les exigences du projet qui peuvent être utilisées comme base pour la sélection des outils.

Étant donné que différentes caractéristiques des outils d'Automatisation des tests sont utilisées pour les logiciels d'interface utilisateur et, par exemple, les services web, il est important de comprendre ce que le projet veut atteindre au fil du temps. Il n'y a pas de limite au nombre d'outils d'Automatisation des tests et de caractéristiques qui peuvent être utilisés ou sélectionnés, mais les coûts doivent toujours être pris en compte. L'utilisation d'un outil commercial sur étagère ou l'implémentation d'une solution personnalisée basée sur une technologie open-source peut être un processus complexe.

Le sujet suivant à évaluer est la composition et l'expérience de l'équipe en matière d'Automatisation des tests. Dans le cas où les testeurs ont peu ou pas d'expérience en programmation, l'utilisation d'une solution « low-code » ou « no-code » peut être un choix viable.

Pour les testeurs techniques ayant des connaissances en programmation, il peut être utile de choisir des outils dont le langage correspond à celui du SUT. Cela présente des avantages, notamment la possibilité de travailler avec les développeurs sur le débogage des défauts d'Automatisation des tests de manière plus efficiente et la formation conjointe des membres de différentes équipes.
