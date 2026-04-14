# synthèse

## Syllabus

## 8 Amélioration continue – 210 minutes (K4)
### Mots clés

validation de schéma, histogramme de test

### Objectifs d'apprentissage

### 8.1 Possibilités d'amélioration continue de l'Automatisation des tests

- TAE-8.1.1 (K3) Découvrir les opportunités d'amélioration des cas de test par la collecte et l'analyse de données.
- TAE-8.1.2 (K4) Analyser les aspects techniques d'une solution d'Automatisation des tests déployée et fournir des recommandations d'amélioration.
- TAE-8.1.3 (K3) Restructurer le testware automatisé pour l'aligner sur les mises à jour du SUT.
- TAE-8.1.4 (K2) Résumer les opportunités d'utilisation des outils d'Automatisation des tests.

### 8.1 Possibilités d'amélioration continue de l'Automatisation des tests

#### 8.1.1 Découvrir les possibilités d'amélioration des cas de test grâce à la collecte et à l'analyse des données
La collecte et l'analyse des données peuvent être améliorées en prenant en compte différents types de
données grâce aux approches décrites ci-dessous.
Histogramme de test
Un rapport visuel des données de test représenté sous la forme d'un histogramme de test fournit des
domaines d'amélioration potentiels concernant les tendances des données des cas de test. Les TAE
peuvent décider des domaines d'amélioration possibles car de nombreux outils de CI/CD et de reporting
des tests ont la capacité de montrer différents résultats de test et leurs données de test respectives (par
exemple, les logs d'exception, les messages d'erreur et les captures d'écran). L'histogramme des tests
permet également aux TAE d'identifier et de sélectionner les cas de test qui sont fragiles et de les
refactoriser avec des améliorations supplémentaires ou en repensant l'implémentation réelle.
Intelligence artificielle
Une autre opportunité récente est l'utilisation de l'intelligence artificielle (IA) pour soutenir les tests et
l'Automatisation des tests. Par exemple, dans les cas de test de l'interface utilisateur, les données
comprennent également des valeurs de localisateur d'interface utilisateur qui peuvent être traitées comme
des entrées. Des outils de pointe récents permettent de détecter si un localisateur donné est modifié par
rapport à celui qui est utilisé. Sur la base du ML et de la reconnaissance d'images, ils peuvent identifier les
nouveaux sélecteurs et utiliser un algorithme d'auto-réparation pour corriger le cas de test et inclure les
localisateurs modifiés dans le rapport de test. Cela peut accélérer les étapes de suivi telles que les
changements de contrôle de version et la maintenance du code.
Validation de schéma
La validation de schéma peut être appliquée à l'analyse des données de l'API (par exemple, les propriétés
dérivées des points de terminaison cibles) et à l'analyse des bases de données (par exemple, les règles
de validation des champs logiciels, telles que les types de données et les plages de valeurs autorisés).
Avec la validation de schéma, la TAS est capable de vérifier si une réponse correspond à la spécification
métier réelle. Ce type de contrôle peut être utilisé pour déterminer si les éléments de réponse obligatoires
sont présents dans la réponse du service et si leur type d'objet correspond à celui défini dans le schéma.
En cas de rupture du schéma, la solution renvoie la validation réelle qui aide les TAE à identifier la cause
racine du problème.
Exemple : une API a six éléments de réponse obligatoires qui doivent être des chaînes de caractères dans
la réponse. Avec les outils de validation de schéma, il n'est pas nécessaire d'écrire des assertions
individuelles pour vérifier si ces types sont des chaînes et si leurs valeurs ne sont pas nulles. La validation
de schéma se charge de ces vérifications, ce qui raccourcit considérablement le code d'Automatisation des
tests implémenté et accroît l'efficience de la détection des défauts dans le service backend.

#### 8.1.2 Analyser les aspects techniques d'une solution d'Automatisation des tests déployée et formuler des recommandations d'amélioration
Outre les tâches de maintenance permanente nécessaires pour maintenir la synchronisation de la TAS
avec le SUT, il existe de nombreuses possibilités d'améliorer la TAS. Ces améliorations peuvent être

apportées pour apporter toute une série de bénéfices, notamment une plus grande efficience (par exemple,
en réduisant encore l'intervention manuelle), une plus grande facilité d'utilisation, des capacités
supplémentaires et un meilleur soutien pour les tests. La décision d'améliorer la TAS est influencée par les
caractéristiques qui ajoutent le plus de valeur à un projet.
Les domaines spécifiques d'une TAS dont l'amélioration peut être envisagée comprennent le script,
l'exécution du test, la vérification, la TAA, le TAF, l'installation et le démontage, la documentation, les
caractéristiques de la TAS, ainsi que les mises à jour et les mises à niveau de la TAS. Ces domaines sont
décrits plus en détail ci-dessous.
L'écriture de scripts
Les techniques de script varient de l'écriture linéaire à l'approche des tests guidés par les données, puis à
l'approche plus sophistiquée des tests guidés par les mots-clés, comme décrit à la section 3.1.4. Il peut
être judicieux de mettre à niveau la technique de script TAS actuelle pour tous les nouveaux tests
automatisés. La technique peut être adaptée à tous les tests automatisés existants, ou du moins à ceux
qui nécessitent le plus d'efforts de maintenance.
Un autre domaine d'amélioration de la TAS pour les scripts de test peut se concentrer sur leur mise en
œuvre. Par exemple :
- Évaluer le chevauchement des scripts de test/cas de test/étapes de test pour consolider les tests
automatisés. Les cas de test contenant des séquences d'actions similaires ne devraient pas
mettre en œuvre ces étapes de test plusieurs fois. Ces étapes de test doivent être transformées
en une fonction et ajoutées à une bibliothèque, afin qu'elles puissent être réutilisées. Ces
fonctions de bibliothèque peuvent ensuite être utilisées par différents cas de test. La
maintenabilité du logiciel de test s'en trouve améliorée. Lorsque les étapes de test ne sont pas
identiques mais similaires, la paramétrisation peut être nécessaire. Remarque : il s'agit d'une
approche typique dans les tests pilotés par mots-clés.
- Établir un processus de reprise en cas de défaillance pour le TAS et le SUT. Lorsqu'une
défaillance se produit pendant l'exécution d'une suite de tests, la TAS doit être en mesure de
récupérer et de continuer avec le prochain test possible. Lorsqu'une défaillance se produit dans
le SUT, la TAS doit effectuer les actions de récupération nécessaires sur le SUT (par exemple,
un redémarrage du SUT) lorsque cela est faisable et pratique.
- Évaluer les mécanismes d'attente pour s'assurer que le meilleur type est utilisé. Il existe trois
mécanismes d'attente courants :
○ Les attentes codées en dur (c'est-à-dire attendre un certain nombre de millisecondes) qui
peuvent être à l'origine de nombreux défauts dans l'automatisation des tests, étant donné
l'imprévisibilité des temps de réponse des logiciels.
○ L'attente dynamique par interrogation (par exemple, vérifier qu'un certain changement
d'état ou qu'une certaine action a eu lieu) est beaucoup plus souple et efficace :
■ La TAS n'attend que le temps nécessaire, et aucun temps de test n'est perdu
■ Lorsque le processus prend plus de temps que prévu, l'interrogation attendra
jusqu'à ce que la condition soit vraie. Il est recommandé d'inclure un mécanisme
## notes
