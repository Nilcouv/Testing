---
tags:
  - Wiki/Professional/TestAnalyst/ISTQB
---
## Introduction au cours

dates : 06-08/07/22

Heures: 09:00-12:15; 13:30-17:00

  
ISTQB - Organisme Anglophone  

CFTL - branche Française d’ISTQB  
TMMI -  

  

K1 - Mémorisation

K2 - Compréhension

K3 - Application

## CH 1 - Fondamentaux des tests (175 min)

### 1.1 Que sont les tests ?

**1.1.1 (K1) Identifier les objectifs habituels des tests**

Les objectifs sont:

1. Évaluer les produits d’activités (ex. exigences, les user stories, la conception et le code
2. Vérifier que les exigences business/client sont atteintes
3. Valider si l’objet de test est complet et fonctionne comme attendu par les utilisateurs et autres parties prenantes
4. Construire la confiance dans le niveau de qualité de l’objet de test  
      
    _informe sur la qualité du produit_
5. Prévenir des défauts  
      
    _détecter les défauts de conceptions lors de la phase d’analyse, évitant de développer une fonctionnalité buguée_
6. Trouver des défaillances et défauts
7. Fournir suffisamment d’informations aux parties prenantes pour leur permettre de prendre des décisions éclairées, en particulier en ce qui concentre le niveau de qualité de l’objet de test
8. Réduire le niveau de risque d’une qualité logicielle inadéquate (ex. des défaillances non détectées auparavant se produisant en opération)
9. Se conformer aux exigences ou aux normes contractuelles, légales ou réglementaires

Test des livrables, un livrable/ produit d’activité pouvant autant les produits du développement (fonctionnalités, composant, système) que la documentation (user stories, spécifications, etc.)

Les objectifs varient en fonction du contexte

- Criticité du composant ou système testé - élevée (médicale, automobile, avionique, etc.) → basse (jeux gratuits, certains sites web, etc.)
- Niveau de test considéré - Composant (code), intégration (installation et interface), acceptation (besoin utilisateur)
- Modèle de cycle de vie

  

  

**1.1.2 (K2) Faire la différence entre tester et déboguer**

Tester : action d’exécuter des tests pouvant provoquer des défaillances dues à des défauts

Déboguer : Action de trouver, analyser et corriger des défauts

  

|   |   |
|---|---|
|Tester||
|||
|||

### 1.2 Pourquoi les tests sont-ils nécessaires ?

**1.2.1 (K2) Donner des exemples montrant la nécessité des tests**

  

**1.2.2 (K2) Expliquer la relation entre les tests et l’assurance qualité et donner des exemples montrant comment les tests contribuent à une amélioration de la qualité**

  

**1.2.3 (K2) Faire la différence entre erreur, défaut et défaillance**

Erreur : Action humaine produisant une imperfection dans le code ou les spécification

défaut: faute dans la documentation ou bug dans le code

Défaillance : comportement inattendu du logiciel suite à l’exécution d’un défaut dans le code

**1.2.4 (K2) Faire la différence entre la cause racine d’un défaut et ses effets**

  

### 1.3 Les 7 Principes généraux des tests

**1.3.1 (K2) Expliquer les 7 principes généraux des tests**

Les 7 Principes sont:

1. Les tests montrent la présence de défauts, pas leur absence
2. Les tests exhaustifs sont impossibles
3. Tester Tôt économise du temps et de l’argent  
      
    _cf. maitrise de phase : L’idéal est de réussir à détecter le défaut dans la phase dans laquelle il a été introduit_
4. Regroupement des défauts
5. Paradoxe du pesticide
6. Les tests dépendent du contexte  
      
    _Ex. norme métier dans l’aviation qui vont conditionne les tests_
7. L’absence d’erreurs est une illusion

  

- Exercice - slide 62
    1. F
    2. C
    3. A
    4. B
    5. E
    6. D
    7. G

### 1.4 Processus de test

**1.4.1 (K2) Expliquer l’impact du contexte du le processus de test**

Base de test = ensemble des connaissances utilisées comme base pour lanalyse et la conception des tests

Condition de test = Un apsect des bases de tests qui est pertinent pour atteindre des objectifs de test spécifiques (exigences fonctionnelles et non-fonctionelles)

Testware = ensemble des produits d’activité réalisé au cours du processus de test pour la planification, la conception, l’exécution, et l’évaluation et l’établissement de rapport des les tests

Vérification = confirmation par rapport au spécification

Validation = confirmation par rapport au client

Oracle = source utilisé pour déterminer les résultats attendus à comparer avec les résultats obtenus de l’application en cours de test

**1.4.2 (K2) Décrire les activités de test et les tâches associées, au sein du processus de test**

1. Planification des tests - Documenter la façon d’organiser les tests sur le projet
2. Pilotage et contrôles des tests - Suivre la mise en oeuvre de ce qui est prévu et rectifier si nécessaire
3. Analyse de test - Identifier quoi tester
4. Conception de test - Concevoir les tests, données et environnements
5. Implémentation des tests - Se mettre en situation d’exécuter les tests
6. Exécution des tests - Exécuter, enregistrer les résultats et signaler les défauts
7. Clôture des tests - Faire un bilan sur les tests et sur les améliorations possibles  
      
    

Les livrables = produits d’activités de tests

Les bases de test = les entrées de test (spécification de haut niveau, user stories, normes, etc.)

outils de gestion de tests = conditions de test, cas de test de haut/bas niveau, procédure de tests

Les conditions de tests =

Testware = tous livrables/documents produits lors des activités de test (produits d’activités des tests

Outils de gestion des défauts = rapport

Traçabilité bi directionnelle cf slide 82

**1.4.3 (K2) Faire la différence entre les produits d’activités qui contribuent au processus de test**

2 types de plan de test

- plan de test maitre
- plan de test par niveau

**1.4.4 (K2) Expliquer les bénéfices apportés par le maintient de la traçabilité entre les bases de test et les produits d’activités du test**

  

### 1.5 La psychologie des tests

**1.5.1 (K1) Identifier les facteurs psychologiques ayant une influence sur le succès des tests**

biais cognitif (biais de confirmation)

**1.5.2 (K2) Expliquer la différence entre l’état d’esprit requis pour les activités de test et l’état d’esprit requis pour les activités de développement**

Comment puis je le faire

Comment puis je le casser

## CH 2 - Tester pendant le cycle de vie du développement logiciel (100 minutes)

### 2.1 Les modèles de développement logiciel

**2.1.1 (K2) Expliquer les relations entre les activités de développement logiciel et les activvités de test dans le cycle de vie du développement logiciel**

Séquentiel

- en cascade
- En V

Un flux linéaire et séquentiel d’activité pour forunir des logiciels qui contiennent l’ensemble des fonctionnalités

Itératif et incrémental

- RUP (Rational unifed process)
- Scrum
- KAnban
- Spiral par prototypage

Définition des exigences, la conception, le développement et le test d’un système par morceaux, pour fournir plusieurs versions avec des fonctionnalités qui augmentent de façon incrémentale

**2.1.2 (K1) Identifier les raison qui font que les modèles de développement logiciel doivent être adaptés au contexte du projet et aux caractéristiques du produit**

  

### 2.2 Niveaux de tests

**2.2.1 (K2) Comparer les différents niveaux de test en termes d’objectifs, de base de test, d’objects de test, de défauts et de défaillances typiques, d’approches et de repsonsabilités**

|   |   |   |   |   |
|---|---|---|---|---|
|Type|Test de composants|Test d’intégration|Test Système|Test d’acceptation|
|Objectifs|- Réduire le risque de défauts dans le code  <br>- Vérifier les caractéristiques fonctionnelles et non fonctionnelles|- Vérifier le comportement fonctionnel et non-fonctionnel des interfaces  <br>- Trouver des défauts dans les interfaces|- Vérifier les comportements fonctionnels et non-fonctionnels  <br>- Vérifier que le système est complet  <br>- Trouver des défauts|- établir la confiance dans la qualité du système  <br>- Valider que le système fonctionnera comme attendu|
|Bases de test|- Conception détaillée  <br>- Code  <br>-Spécifications de composants|- Conception du logiciel  <br>- Spécifications d’interfaces  <br>-Architecture  <br>- Cas d’utilisation|- Spécification des exigences, manuels d’utilisation  <br>- Cas d’utilisation  <br>- Epics et User Stories|- Processus métier et cas d’utilisation  <br>- Règlementation  <br>- Procédures d’installation, sauvegarde, restauration|
|Objet de test|- Code, Classe  <br>- Module de base de données|- Sous-systèmes  <br>- infrastructure et base de données  <br>- interfaces et API|- Applications  <br>- Systèmes Matériel/Logiciel  <br>- Configuration du système|- Système sous test  <br>- Processus métier  <br>- Données de production|
|Défauts et défaillances|- Défauts dans le code  <br>- Problème de flux de données|- Défaillances dans la communication entre composants ou systèmes  <br>- Données ou encodage incorrect des données  <br>- Décalages au niveau des interfaces|- Comportement fonctionnel ou non fonctionnel incorrect  <br>- Flux de contrôle et/ou de données incorrects au sein du systèm  <br>- Défaillance dans la réalisation de tâches de bout en bout|- Règles métier mal implémentées  <br>- Exigences contractuelles ou règlementaires non respectées  <br>- Défaillances non fonctionnelles (utilisabilité, performances…)|
|Approches et responsabilités|- Nécessitent des compétences en développement  <br>- Approche “Développement dirigé par les tests” (TDD)|- Nécessitent des compétences en développement, test et architecture  <br>- Approche “big bang”, de bas en haut, de haut en bas|- Utilisation de techniques de conceptions de test  <br>- Implication de testeurs tôt dans le projet avec des revues|- Souvent sous la responsabilité des clients, utilisateurs, métier, product owners et exploitants|

Bouchon = Une implémentation spéciale ou squelettique d’un composant logiciel, utilisé pour développer ou tester un composant qui l’appelle ou en est dépendant. Cela remplace un composant appelé

Pilote (driver) =Ujn composant logiciel ou outil de tests qui remplace un composant qui contrôle et/ou appelle un composant ou système

Composant = code

intégration = l’intégration du composant avec les composants avec les autres composants avec lesquels il communique

système = l’ensemble du système

**2.2.2**

### 2.3 Types de tests

  

4 types de test:

- Test fonctionnel (boite noir)  
      
    _s’intéresse aux entrées et sorties de l’objet de test_
- Test non-fonctionnel (boite noir)  
      
    _Performance, sécurité, portabilité, utilisabilité, etc._
- Test structurel (boite blanche)  
      
    _s’intéresse au fonctionnement interne à l’objet du test. architecture_
- Test liés au changement (= Test de maintenance)  
    Test de régression, test de confirmation (re-test)  
    

  

Test non-fonctionnel

|   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|
|Efficience des performances|compatibilité|utilisabilité|fiabilité|sécurité|maintenabilité|Portabilité|
||||||||

**2.3.1 (K2) Comparer les tests fonctionnels, non-fonctionnels et boite-blanche**

  

**2.3.2 (K1) Reconnaitre que les tests fonctionnels, non-fonctionnels et boite-blanche peuvent se produire à n’importe quelle niveau de test**

  

**2.3.3 (K2) Comparer les objectifs des tests de confirmation et des tests de régression**

  

### 2.4 Tests de maintenance

**2.4.1 (K2) Résumer les événements déclencheurs des tests de maintenance**

Lié à différents types de changement

**2.4.2 (K2) Décrire le rôle de l’analyse d’impact dans les tests de maintenance**

  

## CH 3 - Tests Statiques (135 min)

### 3.1 Bases des tests statiques

**3.1.1 (K1) Identifier les types de produits d’activité logiciels qui peuvent être examinés par les différentes techniques de test statique**

Test dynamique = provoquer des défaillances

- Test qui nécessite l’exécution du logiciel d’un composant ou système

Test Statiques = Trouver des défauts

- Test d’un composant ou système au niveau spécification ou implémentation sans exécution de ce logiciel (ex. revues ou analyse statique du code)

**3.1.2 (K2) Utiliser des exemples pour décrire la valeur du test statique**

Bénéfices des codes :

1. Détection et correction anticipées des défauts
2. Gain de temps de développement
3. Réduction de la durée et du coût du test
4. Moins de défauts
5. Meilleure communication
6. Découverte d’omissions que le test dynamique ne trouverait pas

**3.1.3 (K2) Expliquer la différence entre les techniques statiques et dynamiques, en considérant les objectifs, les types de défauts à identifier et le rôle de ces techniques dans le cycle de vie du logiciel**

Test statique plus performant pour trouver:

- Les défauts dans les exigences
- Les défauts dans la conception
- Les défauts dans le code
- Les vulnérabilités de sécurité

### 3.2 Processus de revue

Question habituelle : cas pratique puis faut-il faire une revue technique ou une inspection?

**3.2.1 (K2) Résumer les activités du processus de revue de produits d’activité**

  

**3.2.2 (K1) Identifier les différents rôles et responsabilité d’une revue formelle**

**3.2.3 (K2) Expliquer les différences entre les différents types de revue : revue informelle, relecture technique, revue technique, et inspection**

Revue technique demandé par l’auteur du document (slide 193)

|   |   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|---|
||||||||||
||||||||||
||||||||||
||||||||||
||||||||||

**3.2.4 (K3) Appliquer une technique de revue sur un produit d’activités afin d’y trouver des défauts**

**3.2.5 (K2) Expliquer les facteurs contribuant au succès des revues**

  

## CH 4 - Techniques de test (330 min)

technique de test = Technique de conception d’identification de cas de test

3 type de technique de test:

1. boite noire  
    il y a 5 techniques:  
    1. Technique des partitions d’équivalence
    2. Technique d’analyse des valeurs limites
    3. Technique des test de table de décision
    4. Technique des tests des transitionns d’état
    5. Technique des test des cas d’utilisation
2. boite blanche
3. basée sur l’expérience

### 4.1 Catégories de techniques de test

**4.1.1 (K2) Expliquer les caractéristiques, les points communs et différences entre les techniques de test boite-noire, boite-blanche et basées sur l’expérience**

### 4.2 Techniques de test boite-noire

Les tests technique boite-noire inclus:

- La techniques des partitions d’équivalence  
    Partition discrète = partition d’une seul valeur  
    
- L’analyse des valeurs limites
- Le test de table de décisions
- Les tests de transitions d’état
- Les tests des cas d’utilisation

**4.2.1 (K3) Appliquer la techniques des partitions d’équivalence pour produire des cas de test à partir d’exigences données**

  

Exercice sl212

$\begin{aligned}$

Exercice sl213

0-10g- > 25c

11g-50g > 35c

50-75g >

75- 99g > 45c

100> 55g

**4.2.2 (K3) Appliquer l’analyse des valeurs limites pour produire des cas de test à partir d’exigences données**

**4.2.3 (K3) Appliquer le test de tables de décision pour produire des cas de test à partir d’exigences données**

  

On peut nous demander de réduire

**4.2.4 (K3) Appliquer le test des transitions d’état pour produire des cas de test à partir d’exigences données**

**4.2.5 (K2) Expliquer comment produire des cas de test à partir d’un cas d’utilisation**

### 4.3 Techniques de test boite-blanche

Les techniques de test boite blanche inclus :

- Test de couvereture des instructions

**4.3.1 (K2) Expliquer la couverture des instructions**

**4.3.2 (K2) Expliquer la couverture des décisions**

**4.3.3 (K2) Expliquer l’intérêt de la couverture des instructions et des décisions**

### 4.4 Techniques de test basées sur l’expérience

Les techniques de test basées sur l’expérience inclus:

- L’estimation d’erreur
- Le test exploratoires
- Les tests base sur des checklists

**4.4.1 (K2) Expliquer l’estimation d’erreur**

**4.4.2 (K2) Expliquer le test d’exploratoire**

**4.4.3 (K2) Expliquer le test basé sur des checklists**

## CH 5 - Gestion des tests (225 min)

Gestion de la configuration = identification et versioning des éléments du testware

### 5.1 Organisation des tests

**5.1.1 (K2) Expliquer les bénéfices et inconvénients du test indépendant**

Bénéfinces:

- Mutualisation de compétences et expertises
- économies
- impartialité
- professionnalisation des activités
- Détection de défaillances différentes

Inconvénients

- Méconnaissance du contexte métier et projet
- Goulot d’étranglement

### 5.2 Planification et estimation des tests

**5.2.2 Stratégie de test et approche de test**

Différentes stratégies existent et peuvent être combinées

|Approches|Stratégies|
|---|---|
|Analytique|- Analyse des exigences  <br>- Analyse des risques|
|Basée sur des modèles|- Tests conçus à partir d’un modèle|
|Méthodique|- Utilisation d’un ensemble prédéfini de tests ou conditions de test (ex : taxonomie de défauts)|
|Conforme à un processus ou un norme|- Basée sur des règles et normes externe (ex : DO178B)|
|Dirigée (ou consultative)|- Dictée par les parties prenantes|
|Anti-régressions|- Eviter les régressions (avec des tests automatisés)|
|Réactive|- Adaptée pendant l’exécution des tests|

### 5.3 Pilotage et contrôles des tests

  

### 5.4 Gestion de configuration

  

### 5.5 Risques et tests

  

### 5.6 Gestion des défauts

  

## CH 6 - Outils de support aux tests (40 min)

### 6.1 Introduction aux outils de test

6.1.1

(K2) Classer les outils de test selon leur objet et les activités de test prise en charge

6.1.2

(K1) Identifier les bénéfices et les risques de l’automatisation des tests

6.1.3

(K1) Se souvenir des considérations particulières pour les outils d’exécution des tests et les outils de gestion des tests

- Approche de test piloté par les données  
      
    
- Approche de test par mots-clés  
      
    _Script générique traitant des mots-clés decrivant les actions à entreprendre (=mots-clés)_

### 6.2 Utilisation efficace des outils

6.2.1

(K1) Identifier les principes généraux pour la sélection d’un outil

6.2.2

(K1) Rappeler les objectifs de l’utilisation de projets pilotes pour introduire des outils

6.2.3

(K1) Identifier les facteurs de succès pour l’évaluation, l’implémentation, le déploiement et le support continu, des outils de tests dans une organisation