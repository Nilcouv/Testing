# Chapitre 8

## Syllabus - 8 Amélioration continue – 210 minutes (K4)

### Mots clés

validation de schéma, histogramme de test

### Objectifs d'apprentissage pour le chapitre 8

- **8.1** Possibilités d'amélioration continue de l'Automatisation des tests
  - **TAE-8.1.1** (K3) Découvrir les opportunités d'amélioration des cas de test par la collecte et l'analyse de données.
  - **TAE-8.1.2** (K4) Analyser les aspects techniques d'une solution d'Automatisation des tests déployée et fournir des recommandations d'amélioration.
  - **TAE-8.1.3** (K3) Restructurer le testware automatisé pour l'aligner sur les mises à jour du SUT.
  - **TAE-8.1.4** (K2) Résumer les opportunités d'utilisation des outils d'Automatisation des tests.

## 8.1 Possibilités d'amélioration continue de l'Automatisation des tests

### 8.1.1 Découvrir les possibilités d'amélioration des cas de test grâce à la collecte et à l'analyse des données

La collecte et l'analyse des données peuvent être améliorées en prenant en compte différents types de données grâce aux approches décrites ci-dessous.

#### Histogramme de test

Un rapport visuel des données de test représenté sous la forme d'un histogramme de test fournit des domaines d'amélioration potentiels concernant les tendances des données des cas de test. Les TAE peuvent décider des domaines d'amélioration possibles car de nombreux outils de CI/CD et de reporting des tests ont la capacité de montrer différents résultats de test et leurs données de test respectives (par exemple, les logs d'exception, les messages d'erreur et les captures d'écran). L'histogramme des tests permet également aux TAE d'identifier et de sélectionner les cas de test qui sont fragiles et de les refactoriser avec des améliorations supplémentaires ou en repensant l'implémentation réelle.

#### Intelligence artificielle

Une autre opportunité récente est l'utilisation de l'intelligence artificielle (IA) pour soutenir les tests et l'Automatisation des tests. Par exemple, dans les cas de test de l'interface utilisateur, les données comprennent également des valeurs de localisateur d'interface utilisateur qui peuvent être traitées comme des entrées. Des outils de pointe récents permettent de détecter si un localisateur donné est modifié par rapport à celui qui est utilisé. Sur la base du ML et de la reconnaissance d'images, ils peuvent identifier les nouveaux sélecteurs et utiliser un algorithme d'auto-réparation pour corriger le cas de test et inclure les localisateurs modifiés dans le rapport de test. Cela peut accélérer les étapes de suivi telles que les changements de contrôle de version et la maintenance du code.

#### Validation de schéma

La validation de schéma peut être appliquée à l'analyse des données de l'API (par exemple, les propriétés dérivées des points de terminaison cibles) et à l'analyse des bases de données (par exemple, les règles de validation des champs logiciels, telles que les types de données et les plages de valeurs autorisés).

Avec la validation de schéma, la TAS est capable de vérifier si une réponse correspond à la spécification métier réelle. Ce type de contrôle peut être utilisé pour déterminer si les éléments de réponse obligatoires sont présents dans la réponse du service et si leur type d'objet correspond à celui défini dans le schéma. En cas de rupture du schéma, la solution renvoie la validation réelle qui aide les TAE à identifier la cause racine du problème.

Exemple : une API a six éléments de réponse obligatoires qui doivent être des chaînes de caractères dans la réponse. Avec les outils de validation de schéma, il n'est pas nécessaire d'écrire des assertions individuelles pour vérifier si ces types sont des chaînes et si leurs valeurs ne sont pas nulles. La validation de schéma se charge de ces vérifications, ce qui raccourcit considérablement le code d'Automatisation des tests implémenté et accroît l'efficience de la détection des défauts dans le service backend.

### 8.1.2 Analyser les aspects techniques d'une solution d'Automatisation des tests déployée et formuler des recommandations d'amélioration

Outre les tâches de maintenance permanente nécessaires pour maintenir la synchronisation de la TAS avec le SUT, il existe de nombreuses possibilités d'améliorer la TAS. Ces améliorations peuvent être apportées pour apporter toute une série de bénéfices, notamment une plus grande efficience (par exemple, en réduisant encore l'intervention manuelle), une plus grande facilité d'utilisation, des capacités supplémentaires et un meilleur soutien pour les tests. La décision d'améliorer la TAS est influencée par les caractéristiques qui ajoutent le plus de valeur à un projet.

Les domaines spécifiques d'une TAS dont l'amélioration peut être envisagée comprennent le script, l'exécution du test, la vérification, la TAA, le TAF, l'installation et le démontage, la documentation, les caractéristiques de la TAS, ainsi que les mises à jour et les mises à niveau de la TAS. Ces domaines sont décrits plus en détail ci-dessous.

#### L'écriture de scripts

Les techniques de script varient de l'écriture linéaire à l'approche des tests guidés par les données, puis à l'approche plus sophistiquée des tests guidés par les mots-clés, comme décrit à la section 3.1.4. Il peut être judicieux de mettre à niveau la technique de script TAS actuelle pour tous les nouveaux tests automatisés. La technique peut être adaptée à tous les tests automatisés existants, ou du moins à ceux qui nécessitent le plus d'efforts de maintenance.

Un autre domaine d'amélioration de la TAS pour les scripts de test peut se concentrer sur leur mise en œuvre. Par exemple :

- Évaluer le chevauchement des scripts de test/cas de test/étapes de test pour consolider les tests automatisés. Les cas de test contenant des séquences d'actions similaires ne devraient pas mettre en œuvre ces étapes de test plusieurs fois. Ces étapes de test doivent être transformées en une fonction et ajoutées à une bibliothèque, afin qu'elles puissent être réutilisées. Ces fonctions de bibliothèque peuvent ensuite être utilisées par différents cas de test. La maintenabilité du logiciel de test s'en trouve améliorée. Lorsque les étapes de test ne sont pas identiques mais similaires, la paramétrisation peut être nécessaire. Remarque : il s'agit d'une approche typique dans les tests pilotés par mots-clés
- Établir un processus de reprise en cas de défaillance pour le TAS et le SUT. Lorsqu'une défaillance se produit pendant l'exécution d'une suite de tests, la TAS doit être en mesure de récupérer et de continuer avec le prochain test possible. Lorsqu'une défaillance se produit dans le SUT, la TAS doit effectuer les actions de récupération nécessaires sur le SUT (par exemple, un redémarrage du SUT) lorsque cela est faisable et pratique
- Évaluer les mécanismes d'attente pour s'assurer que le meilleur type est utilisé. Il existe trois mécanismes d'attente courants :
  - Les attentes codées en dur (c'est-à-dire attendre un certain nombre de millisecondes) qui peuvent être à l'origine de nombreux défauts dans l'automatisation des tests, étant donné l'imprévisibilité des temps de réponse des logiciels
  - L'attente dynamique par interrogation (par exemple, vérifier qu'un certain changement d'état ou qu'une certaine action a eu lieu) est beaucoup plus souple et efficace :
    - La TAS n'attend que le temps nécessaire, et aucun temps de test n'est perdu
    - Lorsque le processus prend plus de temps que prévu, l'interrogation attendra jusqu'à ce que la condition soit vraie. Il est recommandé d'inclure un mécanisme de temporisation afin d'éviter que le test attende indéfiniment lorsqu'un défaut est présent
  - Un moyen encore plus efficace est de s'abonner au mécanisme d'événement du SUT. Cette méthode est beaucoup plus fiable que les deux autres options, mais le langage de script de test doit prendre en charge l'abonnement aux événements et le SUT doit proposer ces événements à la TAS. Un mécanisme de temporisation est également nécessaire, sinon le test peut attendre indéfiniment s'il y a un défaut

#### Exécution des tests

Lorsqu'une suite de tests de régression automatisés n'est pas terminée parce que l'exécution des tests prend trop de temps, il peut être nécessaire de tester simultanément sur différents environnements de test quand cela est possible. Lorsque des systèmes coûteux sont utilisés pour les tests, il peut être contraignant d'effectuer tous les tests sur un seul système cible. Il peut être nécessaire de diviser la suite de tests de régression en plusieurs parties, chacune s'exécutant sur une période de temps définie (par exemple, en une seule nuit). Une analyse plus poussée de la couverture de l'automatisation des tests peut révéler des doublons. La suppression des doublons peut réduire le temps d'exécution des tests et permettre d'autres gains d'efficacité. Dans le cas de CI/CD, une bonne pratique consiste à exécuter des travaux par lots en parallèle afin d'optimiser le temps d'exécution des tests. De même, il est bon de programmer des tâches automatisées par lots pour exécuter les différents pipelines à un moment donné, par exemple tous les matins, afin de réduire les interactions manuelles et d'accélérer le processus de développement.

#### Vérification

Avant de créer de nouvelles fonctions de vérification, adoptez un ensemble de méthodes de vérification standard à utiliser par tous les tests automatisés. Cela évitera la ré-implémentation des actions de vérification dans plusieurs tests. Lorsque les méthodes de vérification ne sont pas identiques mais similaires, l'utilisation de la paramétrisation permet d'utiliser une fonction pour plusieurs types d'objets.

#### TAA

Il peut être nécessaire de modifier la TAA pour améliorer la testabilité du SUT. Ces modifications peuvent être apportées à l'architecture du SUT et/ou à la TAA de la TAS. Cela peut permettre d'améliorer considérablement l'automatisation des tests, mais peut nécessiter des changements et des investissements importants dans les SUT/TAS. Par exemple, si le SUT doit être modifié pour fournir des API pour les tests, la TAS doit également être remaniée en conséquence. L'ajout de ce type de fonctionnalités, plus tard dans le SDLC, peut s'avérer très coûteux ; il est préférable d'y penser dès le début de l'automatisation des tests et dans les premières phases du SDLC du SUT.

#### TAF

Il y a souvent de nouvelles versions des bibliothèques de base utilisées dans un TAF. Il s'agit parfois de mises à jour majeures, et la dernière version ne peut pas être immédiatement référencée dans la liste des dépendances du TAF, car cela casserait les tests pour de nombreuses équipes qui les utilisent. Il est donc préférable d'effectuer d'abord un pilote et une analyse d'impact. Ensuite, un plan d'adoption peut être créé. Soit toutes les équipes adoptent la nouvelle version des bibliothèques de base en même temps en mettant à jour la dépendance dans le fichier de compilation de la couche des bibliothèques de base, soit chaque équipe décide individuellement du moment de la mise à jour dans sa couche logique métier. Finalement, une fois que toutes les équipes sont prêtes à accepter la nouvelle version des bibliothèques de base, les dépendances peuvent être mises à jour dans la couche des bibliothèques de base (voir section 3.1.3).

#### Initialisation et démontage (« Setup » et « Teardown »)

Les actions et les configurations qui sont répétées avant ou après chaque script ou suite de tests doivent être déplacées dans les méthodes d'initialisation ou de démontage. De cette manière, toute modification ayant un impact sur le code peut être mise à jour en un seul endroit, ce qui réduit les efforts de maintenance. Par exemple, les appels aux services web peuvent être utilisés pour remplir les conditions préalables ou postérieures des tests d'interface utilisateur (par exemple, l'enregistrement de l'utilisateur, le « nettoyage » de l'utilisateur et la configuration du profil).

#### Documentation

Elle couvre toutes les formes de documentation, de la documentation sur l'Automatisation des tests (par exemple, ce que fait le code d'Automatisation des tests et comment il doit être utilisé) à la documentation utilisateur pour la TAS, en passant par les rapports de test et les journaux de test produits par la TAS.

#### Fonctionnalités de la TAS

Ajouter des caractéristiques et des fonctions à la TAS, telles que des rapports de test détaillés, des journaux de test et l'intégration à d'autres systèmes. Seules les fonctionnalités qui seront utilisées doivent être ajoutées. L'ajout de fonctionnalités inutilisées ne fait qu'accroître la complexité et diminuer la fiabilité et la maintenabilité.

#### Mises à jour et mises à niveau du TAF

La mise à jour ou la mise à niveau vers de nouvelles versions du TAF peut permettre de disposer de nouvelles fonctions pouvant être utilisées par les cas de test ou de corriger des défaillances. Le risque est que la mise à jour du TAF, par la mise à niveau des outils de test existants ou l'introduction de nouveaux outils, ait un impact négatif sur les cas de test existants. Il est recommandé de tester la dernière version de l'outil de test en exécutant des exemples de tests avant de déployer la nouvelle version de l'outil de test. Les exemples de tests doivent être représentatifs des tests automatisés de différents SUT, de différents types de tests et, le cas échéant, de différents environnements de test.

### 8.1.3 Restructurer le logiciel de test automatisé pour l'aligner sur les mises à jour du système sous test

L'application d'un ensemble donné de modifications à un SUT existant nécessitera des mises à jour de la TAS, y compris du TAF et des bibliothèques de composants. Tout changement, aussi insignifiant soit-il, peut avoir un impact négatif important sur la fiabilité et la performance de la TAS.

#### Identifier les changements dans les composants de l'environnement de test

Évaluer les changements et les améliorations à apporter. Faut-il modifier le logiciel de test, les bibliothèques de fonctions personnalisées ou le système d'exploitation ? Chacun de ces éléments a un impact sur les performances de la TAS. L'objectif global est de s'assurer que les tests automatisés continuent à fonctionner de manière efficace. Les changements doivent être apportés de manière progressive, dans l'optique d'un produit minimum viable, de sorte que l'impact sur la TAS puisse être mesuré au moyen d'une série limitée de scripts de test. Une fois que l'on a constaté qu'il n'y a pas d'effet secondaire, les changements peuvent être entièrement mis en œuvre. L'exécution d'une régression complète est la dernière étape permettant de vérifier que le changement n'a pas eu d'effet négatif sur les scripts de test automatisés. Au cours de l'exécution de ces scripts de test de régression, des défaillances peuvent être constatées. L'identification de la cause racine de ces défaillances (par exemple, à travers les rapports de test, les logs de test et l'analyse des données de test) fournira un moyen de s'assurer qu'ils ne résultent pas de l'activité d'amélioration de l'Automatisation des tests.

#### Accroître l'efficacité et l'efficience des bibliothèques de fonctions de base de la TAS

Au fur et à mesure qu'une TAS évolue, on découvre de nouvelles façons d'exécuter les tâches plus efficacement. Ces nouvelles techniques (par exemple, l'optimisation du code dans les fonctions et l'utilisation de nouvelles bibliothèques de système d'exploitation) doivent être intégrées dans les bibliothèques de fonctions de base utilisées par le projet actuel et les projets futurs.

#### Cibler plusieurs fonctions qui agissent sur le même type de contrôle pour la consolidation

Une grande partie de l'exécution d'un test automatisé consiste à interroger les contrôles dans l'interface graphique. Cette interrogation sert à fournir des informations sur un contrôle (par exemple, visible/non visible, activé/non activé, taille et dimensions, données). Grâce à ces informations, un test automatisé peut sélectionner un élément dans une liste déroulante, saisir des données dans un champ et lire une valeur dans un champ. Plusieurs fonctions peuvent agir sur les contrôles pour obtenir ces informations. Certaines fonctions sont extrêmement spécialisées, tandis que d'autres sont de nature plus générale. Par exemple, il peut exister une fonction spécifique qui ne fonctionne qu'avec les listes déroulantes. Il peut aussi y avoir une fonction qui fonctionne avec plusieurs fonctions en spécifiant une fonction comme l'un de ses paramètres. Par conséquent, un TAE peut utiliser plusieurs fonctions qui peuvent être regroupées en un nombre réduit de fonctions, ce qui permet d'obtenir les mêmes résultats et de minimiser la maintenance.

#### Refonte de la TAA pour tenir compte des changements dans le SUT

Tout au long du cycle de vie d'une TAS, des modifications devront être apportées pour tenir compte des changements dans le SUT. Au fur et à mesure que le SUT évolue et mûrit, la TAA sous-jacente devra également évoluer pour s'assurer que la capacité est là pour soutenir le SUT. Lors de l'extension des fonctionnalités, il convient de veiller à ce qu'elles ne soient pas mises en œuvre de manière ponctuelle, mais qu'elles soient analysées et modifiées dans le cadre de la TAA. Ainsi, lorsque de nouvelles fonctionnalités du SUT nécessiteront des scripts de test supplémentaires, des composants compatibles seront en place pour prendre en charge ces nouveaux tests automatisés.

#### Conventions de nommage et normalisation

Au fur et à mesure que des changements sont introduits, les conventions de nommage pour le nouveau code d'automatisation des tests et les bibliothèques de fonctions doivent être cohérentes avec les normes définies précédemment (voir section 4.3.1).

#### Évaluation des scripts de test existants pour la révision/élimination

Le processus de changement et d'amélioration comprend également un audit des scripts de test existants, de leur utilisation et de leur valeur continue. Par exemple, si certains tests sont complexes et longs à exécuter, il peut être plus viable et plus efficient de les décomposer en tests plus petits. En ciblant l'élimination des tests qui ne sont pas ou peu exécutés, on réduit la complexité de la TAS et on clarifie ce qui doit être maintenu.

### 8.1.4 Résumer les possibilités d'utilisation des outils d'Automatisation des tests

Outre les tests proprement dits, l'automatisation des tests peut contribuer à des activités de test non spécifiques telles que :

#### Configuration et contrôle de l'environnement

Certains scripts de test (par exemple, la création de données de test) peuvent être exploités dans une méthode de configuration pour créer différentes données de test dans un nouvel environnement de test. Dans une situation où des utilisateurs avec plusieurs profils doivent être créés sur la base de différentes entrées de données, une équipe peut utiliser un script de test automatisé pour appeler un point de terminaison de service web qui enregistre ces utilisateurs. Les scripts de test peuvent avoir un contrôle sur la mise en place de l'infrastructure de test et peuvent être exploités dans le cadre d'un nettoyage après le processus de test. Cela permet de gagner du temps et de s'assurer que les bons utilisateurs sont présents dans chaque nouvel environnement de test. Par exemple, les différents logs de test et autres testware peuvent être retirés automatiquement d'un environnement de test, ce qui rend l'entretien et l'utilisation de l'environnement de test plus efficaces.

#### Vieillissement des données

L'Automatisation des tests peut être utilisée pour manipuler les données de test dans l'environnement de test. Par exemple, dans les bases de données, les champs de date peuvent être vérifiés et contrôlés pour les maintenir à jour d'une année à l'autre.

#### Génération de captures d'écran et de vidéos

La plupart des outils modernes d'Automatisation des tests de l'interface utilisateur ont une capacité intégrée à créer des captures d'écran ou des vidéos, sous certaines conditions, et à les stocker. Grâce à ces outils de test, les équipes peuvent soutenir le métier en créant des captures d'écran et des vidéos d'utilisation réelle pour documenter la version testée du logiciel ou à des fins de marketing.
