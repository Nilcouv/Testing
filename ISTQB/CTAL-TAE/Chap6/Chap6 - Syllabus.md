# Chapitre 6

## Syllabus - 6 Reporting et métriques sur l'Automatisation des tests – 150 minutes (K4)

### Mots clés

mesure, métrique, logging des tests, rapport d'avancement des tests, fin de test

### Objectifs d'apprentissage pour le chapitre 6

- **6.1** Collecte, analyse et reporting des données d'Automatisation des tests
  - **TAE-6.1.1** (K3) Appliquer des méthodes de collecte de données à partir de la solution d'Automatisation des tests et du système sous test.
  - **TAE-6.1.2** (K4) Analyser les données de la solution d'Automatisation des tests et du système sous test pour mieux comprendre les résultats.
  - **TAE-6.1.3** (K2) Expliquer comment un rapport d'avancement des tests est construit et publié.

## 6.1 Collecte, analyse et reporting des données de l'Automatisation des tests

### 6.1.1 Appliquer les méthodes de collecte des données de la solution d'Automatisation des tests et du système sous test

Les données peuvent être collectées à partir des sources suivantes :

- Logs du SUT :
  - Interface utilisateur Web/mobile
  - APIs
  - Applications
  - Serveurs web
  - Serveurs de base de données
- Les logs de la TAF pour fournir une piste d'audit
- Les logs de build
- Les logs de déploiement
- Les logs de production pour surveiller les données en production (voir le syllabus CT-PT de l'ISTQB, section 2.3) :
  - Suivi des performances en production pour effectuer une analyse des tendances
  - Les logs des tests d'efficience des performances dans un environnement de test de performance (par exemple, tests de charge, de stress et de pic)
- Captures et enregistrements d'écrans (natifs de l'outil d'automatisation ou d'une tierce partie)

Étant donné qu'un TAS dispose nativement d'un testware automatisé, ce dernier peut être amélioré pour enregistrer des informations sur son utilisation. Les améliorations apportées au testware sous-jacent peuvent être utilisées par tous les scripts de test automatisés de niveau supérieur. Par exemple, l'amélioration du testware sous-jacent pour enregistrer l'heure de début et de fin de l'exécution du test peut s'appliquer à tous les tests.

#### Caractéristiques de l'Automatisation des tests qui soutiennent la mesure et la génération de rapports de test

Les langages de script de nombreux outils de test soutiennent la mesure et le reporting grâce à des fonctions qui peuvent être utilisées pour enregistrer et logger des informations avant, pendant et après l'exécution des tests individuels et des suites de tests entières.

Le reporting de test sur chacune des séries de tests doit comporter une caractéristique d'analyse permettant de prendre en compte les résultats des runs de tests précédents afin de mettre en évidence des tendances, telles que des changements dans le taux de réussite des tests.

L'Automatisation des tests nécessite généralement d'automatiser à la fois l'exécution du test et la vérification du test, cette dernière étant réalisée en comparant des éléments spécifiques des résultats réels avec les résultats attendus. Cette comparaison est réalisée au mieux par un outil de test utilisant des assertions. Le niveau d'information qui est rapporté à la suite de cette comparaison doit être pris en compte.

Il est important que le statut du test soit déterminé correctement (c'est-à-dire passé ou en échec). En cas d'échec, de plus amples informations sur la cause de la défaillance seront exigées (par exemple, des captures d'écran).

Les différences entre les résultats réels et les résultats attendus d'un test ne sont pas toujours évidentes, et le soutien de l'outil peut être d'une grande aide en permettant de tester des comparaisons qui ignorent les différences attendues, telles que les dates et les heures, tout en mettant en évidence les différences inattendues.

#### Logging des tests

Les logs des tests sont une source fréquemment utilisée pour analyser les défauts potentiels au sein de la TAS et du SUT. La section suivante présente des exemples de log de test, classés par TAS et SUT.

##### Logging de la TAS

Le contexte détermine si le TAF ou l'exécution du test est responsable du logging des informations qui doivent inclure les éléments suivants :

- Le cas de test en cours d'exécution, y compris l'heure de début et de fin
- Le statut de l'exécution du test car, si les défaillances peuvent facilement être identifiées dans les logs des tests, le TAF devrait également disposer de ces informations et en rendre compte via un tableau de bord. Le statut de l'exécution du test peut être soit passé, soit en échec, soit une défaillance du TAF. Les statuts peuvent parfois ne pas être concluants et il est important pour une organisation de les définir de manière claire et cohérente. Une défaillance de la TAS s'applique aux situations où le défaut ne se trouve pas dans la SUT
- Les détails de bas niveau du log du test (par exemple, logging des étapes significatives du test), y compris les informations de calendrier
- Les informations dynamiques sur le SUT (par exemple, les fuites de mémoire) que le cas de test a pu identifier à l'aide d'outils tiers. Les résultats réels et les défaillances doivent être loggés avec la suite de tests qui a été exécutée lorsque la défaillance a été détectée
- Dans le cas des tests de fiabilité ou des tests de stress au cours desquels de nombreux cycles de test sont effectués, un compteur doit être loggé afin de déterminer facilement combien de fois les cas de test ont été exécutés
- Lorsque les cas de test comportent des éléments aléatoires (par exemple, des paramètres aléatoires ou des étapes de test aléatoires dans les tests de transition d'état), le numéro/les choix aléatoires doivent être loggés
- Toutes les actions effectuées par un scénario de test doivent être loggées de manière à ce que les logs de test, ou des parties de ceux-ci, puissent être lus afin de réexécuter le test avec les mêmes étapes de test et le même calendrier. Ceci est utile pour reproduire une défaillance identifiée et pour capturer des informations supplémentaires. Les informations relatives à l'action du cas de test peuvent également être loggées par le SUT afin d'être utilisées lors de la reproduction de défaillances identifiées par le client. Si un client exécute une suite de tests, les informations du log de test sont capturées et peuvent ensuite être rejouées par l'équipe de développement lorsqu'elle teste un défaut
- Des captures d'écran peuvent être enregistrées pendant l'exécution du test pour une utilisation ultérieure lors de l'analyse des causes racines
- Chaque fois qu'une suite de tests déclenche une défaillance, la TAS doit s'assurer que toutes les informations nécessaires à l'analyse du défaut sont disponibles/stockées, ainsi que toute information concernant la suite de test, le cas échéant. La TAS doit sauvegarder tous les vidages de mémoire d'erreur et traces de pile associés. En outre, tous les logs des tests qui peuvent être écrasés (par exemple, les tampons cycliques sont souvent utilisés pour les logs de test sur le SUT) doivent être stockés à un endroit où ils seront disponibles pour une analyse ultérieure
- L'utilisation de couleurs peut aider à distinguer les différents types d'informations du log de test (par exemple, les défauts en rouge et les informations sur la progression en vert)

##### Logging du SUT

La corrélation des résultats de l'Automatisation des tests avec les logs du SUT pour aider à identifier la cause racine des défauts dans le SUT et la TAS.

- Lorsqu'un défaut est identifié dans le SUT, toutes les informations nécessaires à l'analyse du défaut doivent être loggées, y compris les horodatages, l'emplacement de la source du défaut et les messages d'erreur
- Au démarrage d'un système, les informations relatives à la configuration doivent être loggées dans un fichier, comprenant, par exemple, les différentes versions du logiciel/micrologiciel, la configuration du SUT et la configuration du système d'exploitation
- Grâce à l'Automatisation des tests, les logs des tests peuvent être facilement consultables. Une défaillance identifiée dans le log de test par la TAS devrait être facilement identifiée dans le log de test du SUT, et vice versa, avec ou sans outils supplémentaires. La synchronisation de divers logs de test avec un horodatage facilite la corrélation de ce qui s'est passé lorsqu'une défaillance est rapportée

#### Intégration avec d'autres outils tiers

Par exemple, feuilles de calcul, XML, documents, bases de données et outils de reporting.

Lorsque les informations issues de l'exécution des cas de test automatisés sont utilisées dans d'autres outils pour le suivi et le reporting (par exemple, la mise à jour des informations de traçabilité), il est possible de fournir les informations dans un format adapté aux outils tiers. Cela est souvent possible grâce aux fonctionnalités existantes des outils de test (par exemple, les formats d'exportation pour les rapports de test) ou en créant des rapports personnalisés qui sont produits dans un format compatible avec d'autres logiciels.

#### Visualisation des résultats du test

Les résultats des tests peuvent être rendus visibles à l'aide de graphiques. Envisagez d'utiliser des icônes de couleur, comme des feux tricolores, pour indiquer l'état général de l'exécution du test/de l'Automatisation des tests, afin que des décisions puissent être prises sur la base des rapports des tests. Le management est particulièrement intéressé par les résumés visuels des résultats des tests, ce qui facilite la prise de décision. S'ils ont besoin de plus d'informations, ils peuvent toujours aller plus loin dans les détails.

### 6.1.2 Analyser les données de la solution d'Automatisation des tests et du système sous test pour mieux comprendre les résultats de test

Après l'exécution du test, il est important d'analyser les résultats du test, d'identifier les défaillances possibles à la fois dans le SUT et dans la TAS. Pour une telle analyse, les données collectées auprès de la TAS sont primaires et les données collectées auprès du SUT sont secondaires.

- Analyser les données de l'environnement de test pour soutenir le dimensionnement approprié de l'Automatisation des tests (par exemple, dans le cloud) :
  - Les regroupements et les ressources
  - Exécution des tests sur un seul navigateur ou plusieurs (c'est-à-dire multi-navigateurs)
- Comparer les résultats du test des exécutions précédentes
- Déterminer comment utiliser les logs web pour surveiller l'utilisation du logiciel

Les défaillances de l'exécution du test doivent être analysées, car il existe des problèmes potentiels :

1. Vérifier si la même défaillance s'est produite lors des exécutions du test précédentes. Il peut s'agir d'un défaut connu dans le SUT ou la TAS. Le système d'évaluation des tests peut être construit de manière à logger l'historique des résultats des cas de test, ce qui facilite l'analyse
2. Si le défaut n'est pas connu, identifier le cas de test et ce qu'il teste. Le test peut être explicite, ou le cas de test peut être identifié dans le système de gestion des tests, sur la base de son ID loggé avec l'exécution du test
3. Trouver à quelle étape du cas de test la défaillance s'est produite. La TAS le logge
4. Analyser les informations du log de test sur l'état du SUT et vérifier s'il correspond aux résultats attendus en utilisant les captures d'écran, les logs API et réseau, ou tout autre log qui montre l'état du SUT
5. Si l'état du SUT ne correspond pas à ce qui était attendu, logger un défaut dans le système de gestion des défauts. Veillez à inclure toutes les informations nécessaires sur le défaut et les logs qui justifient qu'il s'agit bien d'un défaut

En cas de défaillance, il est possible que le résultat réel et le résultat attendu du SUT ne correspondent pas. Dans ce cas, il est très probable que le SUT contienne un défaut qui doit être corrigé, ou qu'il y ait une non-concordance invisible.

Une autre situation peut se produire si l'environnement de test n'est pas disponible pendant le run de test, ou s'il n'est que partiellement disponible. Dans ce cas, tous les cas de test peuvent échouer, soit avec le même défaut, soit si des parties du système sont en panne, avec des défaillances apparemment réelles. Pour identifier la cause racine de ces défauts, les logs du SUT peuvent être analysés, ce qui montrera s'il y avait des pannes de l'environnement de test au moment du run de test.

Si le SUT implémente des logs d'audit pour les interactions des utilisateurs (c'est-à-dire les sessions UI ou les appels API), cela aide à analyser les résultats des tests. Il y a généralement un ID unique ajouté à l'interaction avec le même ID pour chaque appel et intégration ultérieurs dans le système. De cette manière, en connaissant l'ID unique d'une requête/interaction, le comportement du système peut être observé et retracé.

Cet identifiant unique est généralement appelé identifiant de corrélation ou identifiant de trace. Il peut être loggé par la TAS pour faciliter l'analyse des résultats du test.

### 6.1.3 Expliquer comment un rapport d'avancement des tests est élaboré et publié

Les logs des tests fournissent des informations détaillées sur les étapes du test, les actions à entreprendre et les réponses attendues d'un cas de test et/ou d'une suite de tests. Cependant, les logs de test ne peuvent à eux seuls fournir une bonne vue d'ensemble des résultats du test. Pour cela, il est nécessaire de disposer d'une fonctionnalité de reporting des tests. Après l'exécution d'une suite de tests, un rapport d'avancement des tests concis doit être créé et publié. Un générateur de rapports peut être utilisé à cet effet.

#### Contenu d'un rapport d'avancement des tests

Le rapport d'avancement des tests doit contenir les résultats des tests, des informations sur le SUT et une documentation sur l'environnement de test dans lequel les tests ont été exécutés, dans un format approprié pour chacune des parties prenantes.

Il est nécessaire de savoir quels sont les tests qui ont échoué et les raisons de ces défaillances. Pour faciliter les corrections, il est important de connaître l'historique de l'exécution du test et de savoir qui a rapporté la défaillance (c'est-à-dire, en général, la personne qui l'a créé ou qui l'a mis à jour pour la dernière fois). La personne responsable doit rechercher la cause de la défaillance, rapporter le défaut qui y est lié, assurer le suivi de la correction du défaut et tester que la correction a été correctement implémentée.

Le reporting des tests est également utilisé pour diagnostiquer les éventuelles défaillances des composants du TAF.

#### La publication des rapports de tests

Le rapport de test doit être publié à l'intention de toutes les parties prenantes concernées. Il peut être téléchargé sur un site web, dans le cloud ou sur les lieux, envoyé à une liste de diffusion ou téléchargé vers un autre outil tel qu'un outil de gestion des tests. Cela permet de s'assurer que les rapports seront revus et analysés si des personnes sont censées les recevoir par courriel ou par le biais de messages de discussion postés par un chatbot.

Une option consiste à identifier les parties problématiques du SUT, et à conserver un historique des rapports de test, de sorte que des statistiques sur les cas de test ou les suites de tests présentant des régressions fréquentes puissent être rassemblées pour l'analyse des tendances.

Les parties prenantes auxquelles il faut rendre compte comprennent :

- Les parties prenantes du management :
  - Rôles typiques : architecte de solutions ou d'entreprise, chef de projet/de livraison, gestionnaire de programme, Test Manager ou directeur de test
- Parties prenantes opérationnelles :
  - Rôles typiques : Product Owner/manager, représentant du métier ou Analyste Métier
- Parties prenantes techniques :
  - Rôles typiques : chef d'équipe, scrum master, administrateur web, développeur/administrateur de base de données, leader de test, TAE, testeur, ou développeur

Les rapports de tests peuvent varier en contenu ou en détail en fonction des destinataires. Alors que les parties prenantes techniques peuvent être plus intéressées par les détails de bas niveau, le management se concentrera sur les tendances, telles que le nombre de scénarios de test ajoutés depuis le dernier test run, l'évolution du ratio réussite-échec et la fiabilité de la TAS et du SUT. Les parties prenantes de l'exploitation mettent généralement l'accent sur les métriques liées à l'utilisation du produit.

#### Création de tableaux de bord

Les outils de reporting modernes offrent plusieurs options de reporting par le biais de tableaux de bord, de graphiques colorés, de collectes de logs détaillés et d'analyses automatisées des logs des tests. Il existe un vaste choix d'outils disponibles sur le marché.

Ces outils soutiennent l'agrégation de données à partir de sources telles que les logs de test d'exécution du pipeline, les outils de gestion de projet et les référentiels de code. La visualisation des données fournie par ces outils aide les parties prenantes à voir les tendances et à prendre des décisions en conséquence. Ces tendances peuvent inclure des regroupements de défauts, l'augmentation/la diminution de la propagation des défauts vers certains environnements de test, la dégradation des performances des SUT et la fiabilité des builds.

#### Analyse des logs de test par l'intelligence artificielle/le machine learning

Ces dernières années, certains outils d'Automatisation des tests incluent ou sont basés sur des algorithmes de machine learning (ML). L'analyse automatisée de grandes quantités de données dans les logs de test aide le TAE à réduire le temps passé à localiser les défaillances, à analyser la raison des défaillances de test (est-ce un défaut dans le SUT ou dans la TAS ?) et à regrouper les défauts communs pour le reporting des tests (voir le Syllabus CT-AI de l'ISTQB).
