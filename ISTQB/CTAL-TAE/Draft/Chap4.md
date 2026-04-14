# synthèse

## Syllabus

## 4 Implémentation de l'Automatisation des tests – 150 minutes (K4)

### Mots clés

risque, contexte de test

### Objectifs d'apprentissage

### 4.1 Développement de l'Automatisation des tests

- TAE-4.1.1 (K3) Appliquer des lignes directrices qui soutiennent des activités efficaces d'Automatisation des tests en matière de pilotage et de déploiement.

### 4.2 Risques associés au développement de l'Automatisation des tests

- TAE-4.2.1 (K4) Analyser les risques liés au déploiement et planifier des stratégies d'atténuation des risques pour l'Automatisation des tests.

### 4.3 Maintenabilité de la solution d'Automatisation des tests

- TAE-4.3.1 (K2) Expliquer quels sont les facteurs qui soutiennent et affectent la maintenabilité de la solution d'Automatisation des tests.

### 4.1 Développement de l’Automatisation des tests

#### 4.1.1 Appliquer des lignes directrices qui soutiennent des activités efficaces de pilotage et de déploiement de l'Automatisation des tests
Il est important de définir le périmètre de validation d'un projet pilote d'Automatisation des tests. Un projet
pilote ne prend pas beaucoup de temps à mener, mais le résultat peut avoir un impact significatif sur la
direction que prend le projet.
Sur la base des informations recueillies sur le SUT et des exigences sur le projet, il convient d'évaluer ce
qui suit afin de mettre en place des lignes directrices pour optimiser les efforts d'Automatisation des tests :
- Le(s) langage(s) de programmation qui sera(ont) utilisé(s).
- Les outils commerciaux sur étagère/open-source appropriés.
- Les niveaux de test à couvrir.
- Les cas de test sélectionnés.
- L'approche de développement des cas de test.
Sur la base des points énumérés ci-dessus, les TAE peuvent définir une approche initiale à suivre. Sur la
base des exigences, plusieurs prototypes initiaux différents peuvent être créés pour montrer les avantages
et inconvénients des différentes approches. À partir de là, les TAE peuvent décider du chemin à suivre.
La définition d'un calendrier est un élément important pour respecter les délais et garantir le succès du
projet pilote. Une recommandation courante est de vérifier périodiquement l'avancement du projet pilote
afin d'identifier les risques éventuels et de les atténuer.
Pendant le pilote, il est également recommandé d'essayer d'intégrer la solution et le code déjà implémenté
dans le CI/CD. Cela peut mettre en évidence des problèmes précoces, soit dans le SUT, soit dans la TAS,
soit dans l'intégration globale des différents outils au sein de l'organisation.
Au fur et à mesure que le nombre de cas de test augmente, les TAE peuvent penser à modifier la
configuration initiale du CI/CD pour exécuter les tests de différentes manières et à différents temps de
réflexion.
Par ailleurs, au cours du projet pilote, il est nécessaire d'évaluer d'autres aspects non-techniques,
tels que :
- Les connaissances et l'expérience des membres de l'équipe.
- La structure de l'équipe.
- Les règles de licence et d'organisation.
- Le type de plan de test et les niveaux de test ciblés à couvrir pendant l'automatisation des cas de
test.
Une fois le projet pilote terminé, l'effort doit être évalué par les TAE et les Test Managers afin d'évaluer la
réussite ou la défaillance et de prendre une décision appropriée.

### 4.2 Risques associés au développement de l'Automatisation des tests

#### 4.2.1 Analyse des risques de déploiement et planification des stratégies d'atténuation des risques pour l'Automatisation des tests
L'interface entre le TAF et le SUT doit être prise en compte dans le cadre de la conception architecturale.
Ensuite, les outils de packaging, de logging des tests et de harnais de test peuvent être sélectionnés.
Au cours de l'implémentation du projet pilote, l'expansion et la maintenance du code d'Automatisation des
tests doivent être prises en compte. Ce sont des facteurs cruciaux de la phase d'évaluation du pilote et ils
peuvent sérieusement affecter la décision finale.
Différents risques liés au déploiement peuvent être identifiés à partir du pilote :
- Ouvertures de pare-feu
- Utilisation des ressources (par exemple, CPU et RAM)
Il faut se préparer aux risques liés au déploiement, tels que les problèmes de pare-feu, l'utilisation des
ressources, la connexion au réseau et la fiabilité. Ces éléments ne sont pas strictement liés à
l'Automatisation des tests, mais les TAEs doivent s'assurer que toutes les conditions sont réunies pour
fournir des points de contrôle de qualité fiables et bénéfiques dans leur processus de développement.
L'utilisation d'appareils réels pour l'Automatisation des tests mobiles en est un exemple. Les appareils
mobiles doivent être mis sous tension, disposer d'une autonomie de batterie suffisante pour fonctionner
pendant le test, être connectés à un réseau et avoir accès au SUT.
Les risques techniques liés au déploiement peuvent inclure :
- Le packaging
- Le logging
- La structuration des tests
- La mise à jour
Le packaging
Le packaging doit être pris en compte car le contrôle de la version de l'Automatisation des tests est tout
aussi important que pour le SUT. Le testware peut avoir besoin d'être téléchargé dans un référentiel pour
être partagé au sein d'une organisation, que ce soit sur les lieux ou dans le cloud.
Logging
Le logging des tests donne la plupart des informations sur les résultats du test. Il existe plusieurs niveaux
de logging des tests et tous sont utiles dans l'Automatisation des tests pour diverses raisons :
- Fatal : ce niveau est utilisé pour logger les événements d'erreur qui peuvent conduire à l'abandon
de l'exécution du test.
- Erreur : ce niveau est utilisé lorsqu'une condition ou une interaction échoue et que, par conséquent,
le cas de test échoue également.
- Avertissement : Ce niveau est utilisé lorsqu'une condition/action inattendue se produit mais
n'interrompt pas le déroulement du cas de test.
- Info : Ce niveau est utilisé pour afficher des informations de base sur un cas de test et sur ce qui
se passe pendant l'exécution du test.

- Débogage : Ce niveau est utilisé pour stocker des détails spécifiques à l'exécution qui ne sont
généralement pas requis pour les logs de base, mais qui sont utiles lors de l'investigation d'une
défaillance du test.
- Trace : Ce niveau est similaire à Debug mais contient encore plus d'informations.
Structuration des tests
La partie la plus importante du TAS est le harnais de test et les dispositifs de test qu'il contient, les
éléments qui doivent être disponibles pour que les tests puissent être exécutés. Les dispositifs de test
permettent de contrôler librement l'environnement de test et les données de test. Des préconditions et
des postconditions peuvent être définies pour l'exécution des tests et les cas de test peuvent être
regroupés en suites de tests de plusieurs manières. Ces aspects sont également importants à évaluer au
cours d'un projet pilote. En outre, les contextes de test permettent de créer des tests automatisés qui sont
répétables et atomiques.
Mise à jour
L'un des risques techniques les plus courants concerne les mises à jour automatiques sur les harnais de
test (par exemple, les agents) et les changements de version sur les appareils. Ces risques peuvent être
atténués par des alimentations électriques adéquates, des connexions réseau appropriées et des plans
de configuration des appareils adéquats

### 4.3 Maintenabilité de la solution d'Automatisation des tests

#### 4.3.1 Expliquer quels facteurs soutiennent et affectent la maintenabilité de la solution d'Automatisation des tests
La maintenabilité est fortement influencée par les normes de programmation et les attentes des TAE les
uns envers les autres.
Une règle d'or est d'essayer de suivre les principes du "clean code" de Robert C. Martin (Robert C Martin,
"Clean Code : A Handbook of Agile Software Craftsmanship", 2008).
En bref, les principes du « clean code » (NDT : code propre) mettent l'accent sur les points suivants :
- Utiliser une convention de nommage commune pour les classes, les méthodes et les variables
avec des noms significatifs.
- Utiliser une structure de projet logique et commune.
- Éviter le codage en dur.
- Éviter un trop grand nombre de paramètres d'entrée pour les méthodes.
- Éviter les méthodes longues et complexes.
- Utiliser le logging.
- Utiliser des canevas de conception lorsqu'ils sont utiles et requis.
- Se concentrer sur la testabilité.
Les conventions de nommage sont très utiles pour identifier la cible d'une variable donnée. Le fait d'avoir
des noms de variables compréhensibles tels que "loginButton", "resetPasswordButton" aide les TAE à
comprendre quel composant utiliser.

Le codage en dur consiste à intégrer des valeurs dans le logiciel sans pouvoir les modifier directement. Il
peut être évité en utilisant des tests pilotés par les données, de sorte que les données de test proviennent
d'une source commune qui peut être maintenue plus facilement. Le codage en dur réduit le temps de
développement, mais il n'est pas recommandé de l'utiliser car les données peuvent changer fréquemment,
ce qui peut prendre du temps à maintenir. Il est également conseillé d'utiliser des constantes pour les
variables qui ne sont pas censées changer fréquemment. Ce faisant, il est possible de réduire les sources
et les endroits qui doivent être maintenus.
L'utilisation de canevas de conception est également fortement recommandée. Les canevas de conception
- tels que décrits au point 3.1.5 - permettent d'implémenter un code d'Automatisation des tests structuré et
correctement maintenable, à condition que les canevas de conception soient utilisés correctement.
Pour garantir la qualité du code d'Automatisation des tests, il est recommandé d'utiliser des analyseurs
statiques. Les formateurs de code tels que ceux couramment utilisés dans les IDE amélioreront la lisibilité
du code d'Automatisation des tests.
Outre les principes du « clean-code », il est recommandé d'utiliser une structure et une stratégie de
branches dans le contrôle de version. L'utilisation de branches différentes pour les caractéristiques, les
versions et les corrections de défauts facilite la compréhension du contenu des branches.
## notes