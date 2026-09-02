# Chapitre 7

## Syllabus - 7 Vérifier la solution d'Automatisation des tests – 135 minutes (K3)

### Mots clés

analyse statique

### Objectifs d'apprentissage pour le chapitre 7

- **7.1** Vérification de l'infrastructure d'Automatisation des tests
  - **TAE-7.1.1** (K3) Planifier la vérification de l'environnement d'Automatisation des tests, y compris la configuration des outils de test.
  - **TAE-7.1.2** (K2) Expliquer le comportement correct pour un script de test automatisé donné et/ou une suite de tests.
  - **TAE-7.1.3** (K2) Identifier les cas où l'Automatisation des tests produit des résultats inattendus.
  - **TAE-7.1.4** (K2) Expliquer comment l'analyse statique peut contribuer à la qualité du code d'Automatisation des tests.

## 7.1 Vérification de l'infrastructure d'Automatisation des tests

### 7.1.1 Planifier de vérifier l'environnement d'Automatisation des tests, y compris la mise en place des outils de test

Pour savoir si l'environnement d'Automatisation des tests et tous les autres composants de la TAS fonctionnent comme prévu, il faut encore procéder à des vérifications. Ces vérifications sont effectuées, par exemple, avant de commencer l'Automatisation des tests. Des mesures peuvent être prises pour vérifier les composants de l'environnement d'Automatisation des tests. Chacune d'entre elles est expliquée plus en détail ci-dessous.

#### Installation, paramétrage, configuration et personnalisation de l'outil de test

La TAS est constituée de nombreux composants. Chacun d'entre eux doit être pris en compte pour garantir des performances fiables et reproductibles. Les composants exécutables, les bibliothèques de fonctions correspondantes et les fichiers de données et de configuration de soutien constituent le principal élément d'une TAS. Le processus de configuration d'une TAS peut aller de l'utilisation de scripts d'installation automatisés au placement manuel des fichiers dans les dossiers correspondants. Les outils de test, à l'instar des systèmes d'exploitation et d'autres logiciels, font régulièrement l'objet de mises à jour (service packs) ou peuvent comporter des compléments optionnels ou obligatoires afin de garantir leur compatibilité avec un environnement de SUT donné.

L'installation automatisée ou la copie à partir d'un référentiel présente des avantages. Elle peut garantir que les tests sur différents SUTs ont été effectués avec la même version de la TAS et la même configuration de la TAS, le cas échéant. Les mises à jour de la TAS peuvent être effectuées par l'intermédiaire du référentiel. L'utilisation du référentiel et le processus de mise à niveau vers une nouvelle version de la TAS doivent être les mêmes que pour les outils de développement normalisés.

#### Répétabilité dans la configuration/le démontage de l'environnement de test

Une TAS sera implémentée sur une variété de systèmes, de serveurs et pour soutenir les pipelines CI/CD. Pour s'assurer que la TAS fonctionne correctement dans chaque environnement de test, il est nécessaire d'avoir une approche systématique pour charger et décharger la TAS de n'importe quel environnement de test donné. Cet objectif est atteint avec succès lorsque la construction et la reconstruction de la TAS n'entraînent aucune différence perceptible dans son exploitation au sein de plusieurs environnements de test et d'un environnement à l'autre. La gestion de la configuration des composants de la TAS garantit qu'une configuration donnée peut être créée de manière fiable. Une fois cette tâche accomplie, la documentation des divers composants de la TAS permettra de savoir quels aspects de la TAS peuvent être affectés ou nécessiter des modifications lorsque l'environnement de l'utilisateur final change.

#### Connectivité avec les systèmes/interfaces internes et externes

Une fois qu'une TAS est installée dans un environnement de SUT donné, et avant d'utiliser le SUT, un ensemble de vérifications ou de préconditions doit être administré pour s'assurer que la connectivité avec les systèmes internes, les systèmes externes et les interfaces est disponible. Par exemple, une bonne pratique consiste à se logger sur les serveurs, à lancer les outils d'Automatisation des tests, à vérifier que les outils d'Automatisation des tests peuvent accéder au SUT, à inspecter manuellement les paramètres de configuration et à s'assurer que les permissions sont correctement définies pour le logging des tests et le reporting des tests entre les systèmes. Il est essentiel d'établir des préconditions pour l'Automatisation des tests afin de s'assurer que la TAS a été installée et configurée correctement.

#### Test des composants du TAF

Comme tout projet de développement logiciel, les composants du TAF doivent être testés et vérifiés individuellement. Il peut s'agir de tests fonctionnels et non fonctionnels (par exemple, efficience des performances et utilisation des ressources). Par exemple, les composants qui assurent la vérification des objets sur les systèmes graphiques doivent être testés pour un large éventail de classes d'objets afin d'établir que la vérification des objets fonctionne correctement. De même, les logs et les rapports de test doivent fournir des informations précises sur l'état de l'Automatisation des tests et le comportement du SUT. Des exemples de tests non fonctionnels peuvent inclure la compréhension de la dégradation des performances du TAF, l'utilisation des ressources du système pouvant indiquer des défauts tels que des fuites de mémoire, et un manque d'interopérabilité des composants à l'intérieur et/ou à l'extérieur du TAF.

### 7.1.2 Expliquer le comportement correct pour un script de test automatisé donné et/ou une suite de tests

Les suites de tests automatisées doivent être testées pour vérifier leur complétude, leur cohérence et leur comportement correct. Différents types de contrôles de vérification peuvent être appliqués pour s'assurer que la suite de tests automatisés est disponible à tout moment, ou pour déterminer si elle est apte à être utilisée.

Des mesures peuvent être prises pour vérifier la suite de tests automatisés. Il s'agit notamment de :

- Vérifier la composition de la suite de tests
- Vérifier les nouveaux tests qui se concentrent sur les nouvelles caractéristiques du TAF
- Prendre en compte la répétabilité des tests
- Prendre en compte le caractère intrusif des outils de tests automatisés

Chacun de ces points est expliqué plus en détail ci-dessous.

#### Vérifier la composition de la suite de tests

Vérifier la complétude (par exemple, les cas de test ont tous les résultats attendus et les données de test sont présentes) et la bonne version du TAF et du SUT.

#### Vérifier de nouveaux tests portant sur de nouvelles caractéristiques du TAF

La première fois qu'une nouvelle caractéristique du TAF est utilisée dans les cas de test, elle doit être vérifiée et pilotée de près pour s'assurer que la caractéristique fonctionne correctement.

#### Tenir compte de la répétabilité des tests

Lors de la répétition des tests, les résultats du test doivent toujours être les mêmes. Les cas de test de la suite de tests qui ne donnent pas un résultat de test fiable (par exemple, en raison d'exécutions concurrentes mal séquencées) doivent être retirés de la suite de tests automatisés active et analysés séparément pour trouver la cause racine. Dans le cas contraire, du temps sera consacré à plusieurs reprises à ces runs de test pour analyser la défaillance.

#### Tenir compte du caractère intrusif des outils de test automatisés

La TAS est souvent étroitement couplée au SUT. C'est une question de conception, afin d'assurer une meilleure compatibilité en ce qui concerne le niveau d'interaction. Toutefois, cette intégration étroite peut également avoir des conséquences négatives. Par exemple, lorsque la TAS est située dans l'environnement du SUT, les fonctionnalités du SUT peuvent différer de celles des tests effectués manuellement, ce qui peut avoir un impact sur les performances ainsi que sur la qualité des tests.

Un niveau d'intrusion élevé peut révéler des défaillances pendant les tests qui ne sont pas évidentes dans la production. Si cela entraîne des défaillances au niveau des tests automatisés, la confiance dans la TAS peut chuter de manière spectaculaire. Les développeurs peuvent exiger que les défaillances identifiées par l'Automatisation des tests soient reproduites manuellement, si possible, pour faciliter l'analyse.

### 7.1.3 Identifier où l'Automatisation des tests produit des résultats inattendus

Lorsqu'un script de test échoue ou réussit de manière inattendue, une analyse des causes racines doit être effectuée. Il faut pour cela inspecter les logs de test, les données de performance, l'installation et le démontage du script de test.

Il est également utile d'exécuter quelques tests isolés. Les défaillances intermittentes sont plus difficiles à analyser. Le défaut peut se trouver dans le cas de test, le SUT, le TAF, le matériel ou le réseau. La surveillance des ressources du système peut fournir des indices sur la cause racine. L'analyse des logs du cas de test, du SUT et du TAF peut aider à identifier la cause racine du défaut. Le débogage peut également s'avérer nécessaire. L'identification de la cause racine peut nécessiter le soutien d'un analyste de test, d'un analyste métier, d'un développeur ou d'un ingénieur système.

Vérifier si toutes les assertions sont en place. Les assertions manquantes peuvent donner lieu à des résultats de test non concluants.

### 7.1.4 Expliquer comment l'analyse statique peut contribuer à la qualité du code d'Automatisation des tests

L'analyse statique du code permet de constater les vulnérabilités et les défauts du code du programme. Il peut s'agir du SUT ou du TAF.

Les analyses automatisées peuvent inspecter le code afin d'atténuer les risques. Cela permet de revoir le SUT à la recherche de défauts et de s'assurer que les normes de codage sont respectées et appliquées. Cela peut également être considéré comme une technique de détection proactive des défauts, et cela joue un rôle important dans les implémentations DevSecOps (c'est-à-dire DevOps en mettant l'accent sur la sécurité). Ces analyses se produisent tôt dans le SDLC via des pipelines afin de fournir aux équipes de développement un retour d'information immédiat.

Les résultats concernant les défauts sont généralement classés comme étant de sévérité critique, élevée, moyenne ou faible, de sorte que les équipes de développement ont la possibilité de donner la priorité aux défauts qu'elles choisissent de corriger. Certains outils d'analyse statique sont également en mesure de suggérer des corrections de code pour remédier aux défauts constatés. Ils présentent aux équipes de développement une copie des lignes de code incriminées et proposent aux développeurs une solution possible à implémenter. En outre, ces outils aident les TAE en mesurant la qualité, en suggérant des zones où commenter le code, en améliorant la conception du code pour optimiser la gestion des ressources (par exemple, en utilisant des blocs « try/catch » et de meilleures structures de boucle) et en supprimant les mauvais appels à la bibliothèque.

Comme les outils d'Automatisation des tests utilisent des langages de programmation, il existe un risque qu'un code d'Automatisation des tests inadéquat soit introduit dans le SDLC. À titre d'exemple, une pratique courante lors de l'Automatisation des tests consiste à disposer d'un nom d'utilisateur et d'un mot de passe. Il est concevable qu'un TAE puisse inclure par erreur le mot de passe en clair dans un ou plusieurs scripts de test.

Les outils d'analyse statique peuvent être utiles au code d'Automatisation des tests. Ils peuvent être utilisés pour analyser le code d'Automatisation des tests à la recherche de violations de la sécurité telles qu'un mot de passe en clair dans le code. Les outils d'analyse statique soutiennent de nombreux langages de programmation, y compris ceux utilisés par les logiciels d'Automatisation des tests. Il est donc impératif que le TAE étende les meilleures pratiques d'analyse du code pour inclure également le code d'Automatisation des tests. Même si le code d'Automatisation des tests n'est pas nécessairement déployé avec l'ensemble du logiciel, il existe clairement des vulnérabilités potentielles si le mot de passe a été découvert dans un script de test d'automatisation qui l'accompagne (voir le Syllabus CT-SEC de l'ISTQB).
