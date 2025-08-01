---
tags:
  - Wiki/Professional/TestAnalyst/ISTQB
Type: "[[Training]]"
aliases:
  - ISTQB - Niveau Fondation - Testeur Certifié
  - CTFL
Link: https://www.istqb.org/certifications/certified-tester-foundation-level
---
> [!info] Try QA  
> Logistics software is an application that directs business operations in the shipping and delivery of goods and merchandise.  
> [http://tryqa.com/](http://tryqa.com/)  

# CFTL (Comité Français des Test Logiciel)

> Comité Français réunit depuis 2005, pour développer, définir ou faire la promotion de contenu standards pour les formations en tests de logiciels

### Introduction

> L'ISTQB est le système de certification le plus répandu au monde.

Les différents niveaux de fondation :

- Fondation Level
- Agile Tester Extension
- Model-Based Tester Extension
- Advanced Level
- Security Tester
- Expert Level

  

1. Matière de l'examen
    
    Toute la matière du syllabus du chapitre 1 à 6 est considéré comme matière à apprendre (K1). Le candidat doit donc être en mesure de se souvenir d'un mot-clé ou d'un concept mentionné dans l'un des 6 chapitres. Le niveau de connaissance attendu pour chaque objectif d'apprentissage est indiqué au début de chaque chapitre et est classifié comme ci-dessous:
    
    - K1 : Mémorisation
    - K2 : Mémorisation + Compréhension
    - K3 : Mémorisation + Compréhension + Application
    
    Plus d'informations et d'exemples vis-à-vis des objectifs d'apprentissage sont indiqué dans Appendice B.  
    Chaque définition des termes listé en début de chapitre, juste en dessous du titre du chapitre, doit être apprise (K1), même si ce n'est pas indiqué dans les objectifs d'apprentissage.  
    
    Répartition des questions
    
    |Chapitre|# questions||K1|K2|K3|
    |---|---|---|---|---|---|
    |4. Techniques de conception de tests|11|>|1|5|5|
    |5. Gestion de tests|9|>|2|5|2|
    |1. Fondamentaux|8|>|2|6|0|
    |2. Tests dans les cycles de vie logiciels|5|>|1|4|0|
    |3. Techniques statiques|5|>|1|3|1|
    |6. Outils de tests|2|>|1|1|0|
    |Total|40|>|8|24|8|
    
2. Condition de réussite
    
    Pour réussir l'examen, il faudra répondre correctement à 65% des 40 questions (=26 questions correctes).
    
3. Organisation du syllabus
    
    Le syllabus est organisé en 6 chapitre, réparti sur 16,75 heures d'instruction, dans le cas d'un cours, et est représentatif de l'importance de chaque matière pour l'examen final.
    
    1. Chapitre 1 : Les fondamentaux des tests (K2 - 175 min)
    2. Chapitre 2 : Les tests tout au long du cycle de vie logiciel (K2 - 100 min)
    3. Chapitre 3 : Les tests statiques (K2 - 135 min)
    4. Chapitre 4 : Les techniques de conception de tests (K3 - 330 min)
    5. Chapitre 5 : La gestion des tests (K3 - 225 min)
    6. Chapitre 6 : Outils de support aux tests (K2 - 40 min)

### Chapitre 1 : Les fondamentaux des tests (K2)

### Lexique

#### Lexique

|Mot|Word|Définition|
|---|---|---|
|[[Analyse de test]]|test analysis|L'activité qui identifie les conditions de test en analysant les bases de test.|
|[[Assurance qualité]]|quality assurance|Partie de la gestion de la qualité visant à fournir l’assurance que les exigences qualité seront atteintes|
|[[Base de test]]|test basis|L'ensemble des connaissances utilisées comme base pour l'analyse et la conception des tests, telle que les exigences, la documentation, etc.|
|[[Cas de test]]|test case|Un ensemble de conditions préalables, de données d'entrée, d'actions (le cas échéant), de résultats attendus et de postconditions, élaboré sur la base des  <br>conditions de test|
|[[Cause racine]]|root cause|Une source de défaut telle que si elle est retirée, l’apparition de ce type de défaut est diminuée ou  <br>supprimée. (CMMI)|
|[[Clôture des tests]]|test completion|L'activité qui rend les actifs de test disponibles pour une utilisation ultérieure, laisse les environnements de test dans un état satisfaisant et communique les résultats|
|[[Conception des tests]]|test design|Activité consistant à dériver et à spécifier des cas de test à partir des conditions de test. Voir aussi : Spécification de la conception des tests|
|[[Test Condition]]|test condition|Un aspect testable d'un composant ou d'un système identifié comme une base pour les tests. Donc un aspect des bases de test qui est pertinent pour atteindre des objectifs de test  <br>spécifiques.  <br>Synonymes : exigence de test, situation de test|
|[[Contrôle des tests]]|test control|Une tâche de gestion des tests qui traite du développement et de l’application d’un ensemble d’actions correctives pour remettre un projet de test sur les rails  <br>quand les métriques de suivi indiquent une déviation par rapport à ce qui a été  <br>prévu.  <br>Voir aussi : Gestion des tests|
|[[Couverture - couverture de test]]|Coverage|le degré, exprimé en pourcentage, selon lequel un élément de couverture spécifié a été exécuté lors d’une suite de test.|
|[[Déboguer]]|debugging|le processus de trouver, analyser et éliminer les causes de  <br>défaillance dans les logiciels.|
|[[Défaillance]]|failure|Événement dans lequel un composant ou un système n'exécute pas une fonction requise dans les limites spécifiées|
|[[Défaut]]|defect|Une imperfection ou une déficience d'un produit d’activités lorsqu’il ne répond pas à ses exigences ou à ses  <br>spécifications. (IEEE 1044)  <br>Synonymes : bug, faute|
|[[Données de test]]|test data|Données créées ou sélectionnées pour satisfaire les préconditions d'exécution et les entrées pour exécuter un ou plusieurs cas de test.|
|[[Error]]|error|action humaine produisant un résultat incorrect.  <br>Synonyme : confusion|
|[[Exécution des tests]]|test execution|Processus consistant à exécuter un test sur un composant ou système en test, en produisant le(s) résultat(s) obtenu(s)s.|
|[[Implémentation des tests]]|test implementation|L'activité qui prépare le testware nécessaire à l'exécution des tests sur la base de l'analyse et de la conception des tests.|
|[[Objectif de test]]|test objective|une raison ou but de la conception et l’exécution d’un test.|
|[[Objet de test]]|test object|Composant ou système à tester.  <br>Voir aussi : Article de test|
|[[Oracle de test]]|test oracle|Une source pour déterminer un résultat attendu à comparer avec le résultat réel du système testé.|
|[[Pilotage des tests 2]]|test monitoring|Une activité de gestion des tests qui comprend la vérification de l'état des activités de test, l'identification de tout écart par rapport à l'état planifié ou attendu, et le reporting aux parties prenantes.  <br>Voir aussi : Gestion des tests|
|[[Planification de test]]|test planning|Activité de définition ou de mise à jour d’un plan de test.|
|[[Procédure de test]]|test procedure|Une séquence de cas de test dans l'ordre d'exécution, et  <br>toutes les actions associées qui peuvent être nécessaires pour mettre en place les préconditions initiales et toutes les  <br>activités de bouclage après l'exécution.  <br>Voir aussi : Script de test|
|[[Processus de test]]|test process|Ensemble d'activités interdépendantes comprenant la planification des tests, le suivi et le contrôle des tests, l'analyse de test, la conception des tests, l’implémentation des tests, l'exécution des tests et la clôture des tests.|
|[[produit d’acctivité]]|Work product||
|[[Qualité]]|quality|degré par lequel un composant, système ou processus atteint des exigences spécifiées et/ou des besoins  <br>ou attentes des clients ou utilisateurs (ISO 24765)|
|[[Suite de tests - Suite de cas de test - Ensemble de tests]]|test suite|Ensemble de cas de test ou de procédures de test à exécuter dans un cycle de test spécifique.|
|[[Test]]|testing|Processus consistant en toutes les activités du cycle de vie, statiques et dynamiques, concernant la planification et  <br>l’évaluation de produits logiciels et produits liés pour déterminer s’ils satisfont aux exigences et démontrer qu’ils sont conformes aux objectifs et détecter des anomalies.|
|[[Testware|Testware]]|testware|Produits d’activités réalisés au cours du processus de test pour la planification, la conception, l'exécution, l'évaluation et l'établissement de rapports sur les tests.|
|[[Traçabilité]]|traceability|La mesure dans laquelle une relation peut être établie entre deux ou plusieurs produits d’activités.  <br>Voir aussi : Traçabilité horizontale, Traçabilité verticale|
|[[Validation]]|validation|Confirmation par l’examen et la fourniture de preuves objectives que les exigences, pour un usage ou  <br>une application voulue, ont été satisfaites. [ISO 9000]|
|[[Vérification]]|verification|Confirmation par l’examen et la fourniture de preuves objectives que des exigences spécifiées ont été satisfaites.|

  
  

1. Que sont les tests ?
    - Def : méthodologie permettant d’évaluer la qualité d’un logiciel et de réduire le risque de défaillance.
    - Besoin : a emergé avec la diffusion de l’informatique dans tous les secteurs, (mobilité, banquaire, militaire, etc) et l’émergeance de nouveaux risques, allant de la perte d’argent et de temps, jusqu’à la mort, en passant par les blessures.
    - préconceptions communes
        - Le test se limite à exécuter le test et vérifier.  
              
            _Faux! Le test logiciel est un processus couvrant de nombreuse activité, telle que la planification, l’analyse, la conception, la mise en oeuvre de test, etc._
        - Les tests impliquent d’exécuter un composant ou un système  
              
            _Faux! On parle de_ _tests dynamiques__, impliquant l’exécution d’un composant, en opposition aux_ _tests statiques__, qui n’implique aucune exécution, et se concentre sur la vérification des exigences, des users stories, du code source, etc._
        - Les tests se concentre uniquement sur la vérification des exigences, des User Stories ou d’autres spécifications  
              
            _Faux! Les tests impliquent aussi de vérifier que le système répond aux besoins des utilisateurs et des autres parties prenantes dans ses environnements opérationnels_
    - ==Objectifs récurrentes (K1)==
        - ==Évaluer les produits d’activités (ex: exigences, les User Stories, la conception et le code)==
        - ==Vérifier que toutes les exigences spécifiés sont remplies==
        - ==Valider au près des utilisateurs et autres parties prenantes si l’objet du test est complet et fonctionne comme attendu==
        - ==Etablir la confiance dans le niveau de qualité de l’objet du test==
        - ==Prévenir des défauts==
        - ==trouver les défaillances et défauts==
        - ==Informer suffisamment les parties prenantes afin qu’ils soient aptes à prendre des décisions éclairées, en particulier sur le niveau de qualité de l’objet du test==
        - ==Réduire le niveau de risque d’une qualité logicielle inadéquate (ex: défaillances en opérationnel non-préalablement détectées)==
        - ==vérification de la compatibilité et conformité du test et de son objet avec les exigences ou les normes contractuelles, légales et réglementaires.==
    - ==Dépendant du contexte (composant ou système testé, niveau de test et me model du cycle de développement logiciel), the objectives peuvent varier. ex:==
        - ==Durant le test d’un composant, l’objectif peut être d’identifier un maximum de défaillance pour connaitre les défauts sous-jacents, ou d’étendre le code couvert par le test==
        - ==Durant un test d’acceptation, l’objectif peut être de confirmer que le système fonctionne bien et remplit les attentes, ou d’informer les parties prenantes des risques lié au déploiement du système à une date donnée.==
    - Le test et le déboggage sont deux activités différentes.  
        Le test se concentre à trouver les défaillances causées par les défauts dans le logiciel, tandis que le déboggage est l’activité de développement, qui trouve, analyse et corrige de ces défauts.  
        
2. 2.   
          
        
    
      
      
    

## 1.1 - Que sont les tests ?

### 1.1.1 - Objectifs habituels des tests

### 1.1.2 - Test et débogage

## 1.2 - Nécessité des tests

1. Pourquoi ?  
    La présence de défauts dans le logiciel ou le système  
    1. Crée des défaillances
    2. Ne satisfasse pas les besoins des parties prenante
2. Comment ?  
    Grâce à l’emploie de technique de test, approprié qui vont réduire ce type de livraison problématique, si applqiuée:  
    1. avec le niveau approprié d’expertise en matière de test
    2. au niveau de test approprié
    3. au moment appropriée du cycle de vie de développement logiciel.

### 1.2.1 - Contribution des tests au succès

1. La participation des testeurs revue des exigences ou au raffinement des user stories réduit les défauts dans les exigences
2. La collaboration entre les testeurs et les concepteurs du système approfondi la compréhension de la conception et la façon de tester, réduisant les défauts et les détectant à un stade précoce.
3. La collaboration entre testeurs et développeurs lors du développement, augmente la compréhension du code et la façon de le tester, réduisant les défauts dans le code et les tests
4. La validation et vérification du logiciel par les testeurs permet de prévenir et réduire les défauts et défaillance en production, augmentant les chances de répondre aux besoins des partis prenant et des exigences.

### 1.2.2 - Assurance qualité et test

1. Gestion de la qualité  
    Toutes activités qui dirigent ou contrôle la qualité au sein d’une organisation  
    1. assurance de la qualité  
          
        _Activités axées sur le respect des processus adéquats afin d’atteindre les niveaux de qualité appropriés. Passe par la prévention des défauts, que ce soit par l’analyse des défauts pour en éliminer les causes ou les réunions rétrospectives pour améliorer les processus._
    2. contrôle de la qualité  
          
        _Ensemble des activités de développement, vérification et maintenance logicielle, dont le testing., afin d’atteindre le niveau de qualité attentu._

### 1.2.3 - Erreurs, défauts et défaillances

1. erreurs  
      
    _Action humaine produisant un résultat incorrect, et donc un défaut dans le produit d’activité. Elle peuvent survenir pour cause de contraintes de temps, de manque de compétences, mauvaise communication sur les exigences, etc._
2. défauts (faute ou bogue)  
      
    _imperfection ou déficience d'un produit d’activités ne répondant pas aux exigences ou aux spécifications. Il peuvent conduire à une défaillance d’un composant ou d’un système. Tous défauts ne crée pas une défaillance, nécessitant dans certains cas des circonstances précises, telle que des entrées (ex: entrer du texte dans un champs attendant un nombre) ou des conditions environnementales précises (ex: rayonnement électromagnétique perturbant le fonctionnement des composants et firmware). Des erreurs, dans les données, dans la rédaction ou l’exécution des test peuvent mener à :_
    1. faux positif  
        Faux défaut du produit d’activité rapporté par l’exécution du test  
        
    2. faux négatif  
        Défaut du produit d’activité non-rapporté par l’exécution du test  
        
3. défaillance  
      
    _Événement où un composant ou un système n'exécute pas une fonction requise dans les limites spécifiées._

### 1.2.4 - Défauts, causes racines et effets

Les causes racines des défauts sont les premières actions ou conditions à l’origine de des défauts. L’analyse des défauts permet d’identifier leurs causes racines afin de prévenir l’apparition de défauts similaires et améliorer les processus.

## 1.3 - 7 Principes sur les tests

- Les principes sont :
    1. Les tests montrent la présence de défauts, pas leur absence  
          
        _Il est impossible de prouver l’inexistance de quelques choses, seulement son existance_
    2. Les tests exhaustif sont impossibles  
          
        _le nombre de variables causant un défaut (humaines, matérielles, etc.) étant important, il est impossible de couvrir toutes les combinaisons possibles Il est donc recommandé d’analyser les risques, les techniques de test et des priorités pour cibler les efforts._
    3. Tester tôt économise du temps et de l’argent  
          
        _Détecter tôt le défauts limite les dépendances impactées par le défauts et les potentiels coûts de redéveloppement_
    4. Regroupement des défauts  
          
        _Regrouper et prédire les défauts_ permet _une analyse comparative avec les groupes de défauts observés en test et opérationnel, contribuant à l’analyse de risque afin de mieux cerner l’effort de test; Un petit nombre de module présentant la majorité des défauts et produisant la majorité des défaillances. (Loi de Pareto)_
    5. Paradoxe du pesticide  
          
        _La capacité d’un test à découvrir de nouveaux défauts décroit au fur et à mesure qu’on le repète, celui-ci ne testant un contexte particulier. Il est donc essentiel de faire varier les conditions du test (données, cas de test, etc.) afin de découvrir de nouveaux défauts._
    6. Les tests sont contextuels  
          
        _Dépendant du contexte, la stratégie et les cas de test varrieront. On ne teste pas une voiture, un antivirus et un site de e-commerce._
    7. L’absence d’erreur est un mirage  
          
        _Trouver et corriger les défauts peut toujours produire un produit d’activité ne répondant pas aux attentes et aux besoins des partis prenants, car peu performant, difficile à utiliser ou inférieur à un système concurrent._

## 1.4 - Processus de test

Le processus de test est les séries d’activtié de test à exécuter, définit dans la stratégie de test. Cette stratégie définit autant les activités, que l’implémentation et le déroulement (où quand et comment). S’il n’existe pas de processus universel de test, des séries commune d’activité de test permettent d’augmenter les chances d’atteindre les objectifs fixées.

### 1.4.1 - Processus de test en contexte

Les processus de test pour une organisation sont influencés par différents des facteurs contextuels internes et externes, telle que la méthodologie de projet, le modèle de cycle de vie du dévelopement logiciel, contraintes opérationnelles (temps, budget, ressources, etc.), etc.

### 1.4.2 - les activités et tâches de test

1. Les activités et tâches de test  
    Un processus de test consiste aux principaux groupes d’activités suivantes; Chaque groupe d’activité consiste en une mutlitude de tâches individuelles variant selon les projets  
    1. Planification des tests  
        Consiste en la création du plan de test qui définit les objectifs des tests et l’approche pour les atteindres dans le cadre imposé par le projet. le plan de test peut être revisité sur base des retours récoltés pendant la phase de surveillance et de contrôles des tests.  
        
    2. Pilotage et contrôle des tests  
        Consiste en la comparaison des progrès du test en cours avec le calendrier et les métriques définies dans le plan de test. Ainsi qu’à la communication aux parties prenantes des progrès du test via le rapport d’avancement de test, qui inclu toutes informations importantes pour la prise de décision (replanification/arrêt des tests), telle que les écarts par rapport au plan.  
        
    3. Analyse des tests (quoi tester ?)  
        Consiste à établir ce qui doit être tester sur base de critères mesurables en identifiant les fonctionnalités testables et définissant les conditiones de tests associées. Ce qui inclus les activités suivantes :  
        
        1. L’analyse des bases de test adapté au niveau de test considéré
        2. L’évaluation des bases et les éléments de test pour en identifier les défauts
        3. L’identification des fonctionnalités et leurs ensembles à tester
        4. La définition et la priorisation les conditions de tests pour chaque fonctionnalité basé sur les l’analyse de chaque fonctionnalité et les caractéristiques fonctionnelles, non-fonctionnelles et structurelle
        5. La capture de la traçabilité bi-directionnelle entre chaque élément de la base de test et les conditions de test associées
        
        - More details
            
            L’application de techniques de test (botie noir/blanche, basée sur l’expérience) peut aider à réduire la probabilité d’omission d’importantes conditions de test et affiner leur exactitude et précision
            
    4. Conception des tests (comment le tester ?)  
        Consiste en l’élaboration des conditions de test en cas de test et matériels de test par l’utilisation de techniques de test. Ce qui inclus les activités suivantes :  
        1. Conception et hiérarchisation des cas de test et leurs ensembles.
        2. Identification des données de test nécessaire pour soutenir les conditions de test et des cas de test
        3. Conception de l’environnement de test et identification des infrastructures et matériels nécessaires
        4. Capture de la traçabilités bi-directionnnelle entre la base, les conditions et les cas de test
    5. Implémantation des tests (Avons nous tous pour tester ?)  
        Consiste en la mise en place des matériels de test, telle que le séquençage des cas de test en procédure. Ce qui inclus ;:  
        1. Le développement et la hierachisation des procédures de test, et éventuellement, créer des scripte de test automatisé
        2. La création de suites de test à partir des procédures de test et des scripts de test automatisé
        3. La planification des suites de tests dans le calendrier d’éxecution des tests
        4. La construction et vérification de l’environnement de test (harnais de test, virtualisation des services, simulateurs, etc.)
        5. La préparation, le chargement et la vériifcation des données dans l’environnement de test
        6. La vérification et mise à jour de la traçabilité bidirectionnelle entre la base, les conditions, les cas, les procédures et les suites de test.
    6. Exécution des tests  
        Consiste en l’exécution des suites de test en fonction du calendrier d’éxecution des tests. Cette étape inclus :  
        1. L’enregistrement des identifiants/ de la version des éléments ou objets, des outils et matériels de test.
        2. L’exécution des tests manuelle ou via des outils
        3. La comparaison des résultats actuels et attuels
        4. L’analyse des anomalies pour en déduire les causes probables (code erroné, faux positif, etc.)
        5. La répétition des activités à des fins de réplicabilité ou au suite d’un correctif (exécution d’un test corrigé, test de confirmation, etc.)
        6. La vérification et mise à jours de la traçabilité bi-directionnelle des bases, conditions, cas, procédures et résultats de test.
    7. Clôture des tests  
        Consiste en la collecte des données pour consolider les procédures de test, ils ont lieu à des étapes clés du projet. Ce qui inclus :  
        1. La vérification de la clôture des rapports de défauts, l’entrée d’élément de produit de backlog ou de demande de changement, pour tous défauts non-résolu à la fin de l’éxécution.
        2. La création d’un rapport synthétique de fin de test pour les parties prenantes
        3. La finalisation et l’archivage de l’environnement, des données, de l’infrastructure et du matériel de test pour une utilisation ultérieur
        4. Le transfère du matériel de test aux différentes équipes, dont l’équipe de maintenance, et autres parties prenantes pouvant en bénéficier.
        5. L’analyse des leçons apprises de la clôture des activités de test pour en déterminer les changements pour les prochaines itérations, versions et projets.
        6. L’utilisation des informations collectées pour améliorer la maturité des processus de test.

### 1.4.3 - les produits d’activité de test

_Les produits d’activités sont le résultat des processus de test, qui tous deux varient significativement en fonction des organisations. Dans le cas des produits d’activités, ils varient significativement dans leur type, leur organisation et gestion, et leur appellation. Beaucoup des produits d’activités ci-dessous peuvent être saisis et gérés à l’aide d’outils de gestion des tests et/ou des défauts._

1. Produits d’activités de la planification des tests  
      
    _Inclus, un ou plusieurs plans de test, qui comprennent des informations sur la base de tests. Cette base lie les autres produits d’activités via les informations de traçabilités et les critères de sorties; Critères qui sont utilisé pendant les tests de pilotage et contrôle._
2. Produits d’activités de pilotage et contrôle des tests  
      
    _inclus divers types de rapport de tests, telle que le rapport d’avancement de test (produit en continu ou régulièrement); et le rapport de synthèse des tests (produit à l’achèvement de divers étapes). Ils doivent fournir des informations pertinences au public cible sur l’avancement des tests, à la date du rapport, telle que le résumé des résultats de l’exécution des tests. Mais aussi, adresser les inquiétudes des gestionnaires du projet, telle que l’achèvement des tâches, l’affectation et l’utilisation des ressources, et l’effort._
3. Produits d’activités de l’analyse de test  
      
    _Inclus la définition et la priorisation des conditions de test, idéalement bi-directionnellement traçable jusqu’à l’élément spécific couvert dans la base de test. L’analuse de test peut aussi impliquer la création de charte de test dans le cas des tests d’exploration, mais aussi la découverte et documentation de défauts dans la base de test._
4. Produits d’activités de la conception des tests  
      
    _Résulte en la conception de cas de test et de leurs ensembles, afin d’exercer les conditions définies dans l’analyse de test, mais aussi la conception et/ou l’identification des données de tests, la conception de l’environnement de test et l’identification de l’infrastructure et des outils.  
    Il est conseillé de concevoir des cas de test de haut niveau sans valeur d’entrée, ni valeur attendue en sortie, afin de documenter le scope du test et de disposer de cas de test ré-utilisable bi-directionnellement traçable jusqu’aux conditions qu’il couvre, quelque soit le cycle de test et le set de données.  
    _
5. Produits d’activités de l’implémentation des tests  
      
    _Phase consistant à reprendre les cas de test conçus lors de la phase de conception pour établir une procédure de test, ce qui veut dire définir la séquence de test, donc l’ordre dans lequel les cas de test seront joués. Ces procédures sont ensuite réparties dans différentes suites de test, dont l’ordre d’exécution est définit par le calendrier d’exécution des cas de test.  
      
    Ex: Pour 1 composant, 2 ensembles de données et 13 cas de test, vous créerez une suite de test spécifique à ce composant, incluant 2 procédures de test spécifique à chaque ensemble de données, dans lesquels se répartissent les cas de test. Ensuite vous définirez le calendrier d’exécution dépendant les suites de test qui doivent être tester en premier lieu.  
      
    Cas de test peut tester un composant, les liens avec ce composant , vérifier si il n’y a pas de régression, etc.  
      
    _  
      
    _Inclus les procédures de test et leurs procédures, les suites de test, un calendrier d’exécution. Permet de démontrer la réalisation des critères de couverture établis dans le plan de test par la traçabilité bidirectionnelle entre les procédures de tests et des éléments spécifique de la base de test, via les cas et conditions de test, une fois les tests d’implémentation complétés. peut inclure la création de produits d’activité par des services de virtualisation et d’automation de scripts de test. peut aussi résulter en la création et vérification de données et de l’environnement de test, qui peuvent servir à attribuer des valeurs concrètes aux entrées et aux résultats attendus des cas de test de haut niveau pour les transformer en cas de test de bas niveau. Les résultat attendus associés aux données de test sont identifié en utilisant un oracle de test._
6. Produits d’activités de l’exécution des tests  
      
    _Phase d’éxécution des cas de test consistant à produire les produits et éléments d’activité, telle que des logs contenant les status des cas de tests (passé/bloqué/échoué), la documentation des processus de test (logiciel utilisé, etc.), les rapports de défauts (environement, outils utilisé, etc)_
7. Produits d’activités de la clôture des tests  
    Phase consistant à produire un rapport de synthèse des tests, un compte rendu d’activité avec des recommandations d’amélioration pour les projets, cycles et itérations suivantes, ainsi que la liste du matériel de test (matériel produit par le plan, la suite et les cas de test, les tests de régressions, les script d’automatisation, etc + emplacement de ce matériel)  
    

### 1.4.4 - Traçabilité entre la base et les produits d’activité des tests

## 1.5 - La psychologie des test

La psychologie humaine influe sur le test logiciel, l’être humain étant impliqué autant dans le développement logiciel, que dans sa sous partie, le test logiciel.

### 1.5.1 - Psychologie humain et le test

l’humain souffrant de biais cognitif, des frictions voir de l’hostilité envers les tests, leurs résultats et les testeurs peuvent apparaitre. Un exemple est le biais de confirmation, qui est cette tendance chez l’humain à chercher les informations confirmant une croyance tenue et à rejeter toute chose la contredisant. Or dans le cas de développeurs s’attendant à que leur code soit correct, les résultats des tests créeront du rejet et de l’hostilité envers le testeur.

Il est donc essentiel de communiquer de manière positive, non-violente et constructive sur les défauts et défaillances, en insistant sur la collaboration et les bénéfices apporté par le test (amélioration du projet, détection anticipé des défauts, etc.), afin de construire des relations positives avec les autres collègues. Il est donc essentiel de faire preuve d’empathie et d’écoute, en tant que testeur.

### 1.5.2 - État d’esprit des testeurs et développeurs

Le but premier du développeur et du testeur différent, il en découle autant une différence d’approche, que de méthodologie et de solution mise en oeuvre; Le développeur cherchant à concevoir et construire un produit, tandis que le testeur cherche à vérifier et valider le produit, à en trouver les défauts, etc.

  

### Chapitre 2 :

### Lexique

#### Lexique

|Mot|Word|Définition|
|---|---|---|
|[[Tests Alpha]]|alpha testing|test opérationnel réel ou simulé conduit dans l’environnement de test du développement par des rôles en dehors de ceux de l’organisation en charge du développement.|
|[[Tests Beta]]|beta testing|Tests opérationnels simulés ou réels effectués sur un site externe, par des rôles à l'extérieur de l'organisation de développement.|
|[[Wiki/Glossary/Sans titre|Sans titre]]|change-related testing||
|[[Logiciel commercial sur étagère]]|commercial  <br>off-the-shelf software (COTS)|Produit logiciel qui est développé pour le marché de façon générale, c'est-à-dire pour un grand nombre de clients, et qui est livré à de nombreux clients dans un format identique.|
|[[Test de composant]]|component  <br>testing|le test de composants logiciels individuels.|
|[[test d’intégration de composants]]|component integration testing|test effectué pour découvrir des défauts dans les interfaces et les interactions entre des composants intégrés.|
|[[Test de confirmation]]|confirmation testing|tests dynamiques effectués après la correction de défauts dans le but de confirmer que les défaillances causées par ces défauts ne se produisent plus.|
|[[Tests d'acceptation contractuelle]]|contractual  <br>acceptance testing|tests d'acceptation effectués pour vérifier si un système satisfait à ses exigences contractuelles.|
|[[Test fonctionnel]]|functional testing|Test réalisé pour évaluer la conformité d'un composant ou d'un système aux exigences. Voir aussi : test boîte-noire  <br>fonctionnelles. (ISO 24765)|
|[[Analyse d'impact]]|impact  <br>analysis|L'identification de tous les produits d’activités touchés par un changement, y incluant une estimation des ressources nécessaires pour accomplir le changement.|
|[[Tests d’intégration]]|integration testing|tests effectués pour montrer des défauts dans les interfaces et interactions de composants ou systèmes intégrés.|
|[[Test de maintenance]]|maintenance  <br>testing|Processus de modification d'un composant ou d'un système après la livraison pour corriger les défauts, améliorer les attributs de qualité ou s'adapter à un environnement modifié.|
|[[Test non-fonctionnel]]|non-functional testing|Test effectué pour évaluer la conformité d'un composant ou d'un système avec les exigences non fonctionnelles.|
|[[Tests d’acceptation opérationnelle]]|operational  <br>acceptance testing|test opérationnel en phase de test d'acceptation, généralement effectué dans un environnement opérationnel (simulé) par l' exploitation et/ou le personnel de l'administration des systèmes en se concentrant sur les aspects opérationnels, par exemple la reprise (après incident), le comportement des ressources, la facilité d’installation et la conformité technique.|
|[[Test de régression]]|regression testing|tests d’un programme préalablement testé, après une modification, pour s’assurer que des défauts n’ont pas été introduits ou découverts dans des parties non modifiées du logiciel, comme suites des modifications effectuées.|
|[[Test d'acceptation réglementaire]]|regulatory  <br>acceptance testing|Tests d'acceptation effectués pour vérifier si un système est conforme aux lois, politiques et règlements applicables.|
|[[Modèle de développement séquentiel]]|sequential development model|Un type de modèle de cycle de vie de développement selon lequel un système achevé est développé de manière linéaire en plusieurs phases distinctes et successives, sans chevauchement entre elles.|
|[[Tests d’intégration système]]|system  <br>integration testing|Tester la combinaison et l'interaction des systèmes.|
|[[Tests système]]|system testing|Tester un système intégré pour vérifier qu'il répond aux exigences spécifiées.|
|[[Environnement de test]]|test  <br>environment|Environnement contenant le matériel, les instruments, les simulateurs, les outils logiciels et les autres éléments de support nécessaires à l’exécution d’un test.|
|[[Niveau de test]]|test level|Une instanciation spécifique d'un processus de test.|
|[[Type de test]]|test type|Groupe d'activités de test basées sur des objectifs de test spécifiques visant des caractéristiques spécifiques d'un composant ou d'un système.|
|[[Tests d'acceptation utilisateur]]|user acceptance testing|Tests d'acceptation effectués dans un environnement opérationnel réel ou simulé par les utilisateurs prévus en mettant l'accent sur leurs besoins, leurs exigences et leurs processus métier.|
|[[Test boîte-blanche]]|white-box  <br>testing|Test basé sur une analyse de la structure interne du composant ou système.  <br>Synonymes : Test de boîtes transparentes, Test basé sur le code, Test de boîtes de verre, Test de couverture logique, Test dirigé par la couverture logique, Test structurel, Test basé sur la structure.|
|[[Test d’acceptation]]|acceptance testing|Test formel conduit par le business déterminant si le système satisfait où non au critères d’acceptance, basé sur les besoins utilisateurs et les attentes.|
|[[Test Statique]]|Static Test|Test qui n'implique pas l'exécution d'un élément de test, telle que du code, l’exécution d’un programme, etc. Il consiste donc à vérifier le code, les documents d’exigences et de conceptions, pour en prévenir les défauts.|
|[[développement piloté par les tests]]|TDD (Test driven development)|Une technique de développement de logiciels selon laquelle les cas de test sont développés, et souvent automatisés, puis le logiciel est développé de manière incrémentale pour passer ces cas de test.|
|[[Objet de test]]|test object|Composant ou système à tester.  <br>Voir aussi : Article de test|
|[[Objectif de test]]|test objective|une raison ou but de la conception et l’exécution d’un test.|

  
  

  

  

### Chapitre 3 :

### Lexique

#### Lexique

|Mot|Word|Définition|
|---|---|---|
|[[Tests Alpha]]|alpha testing|test opérationnel réel ou simulé conduit dans l’environnement de test du développement par des rôles en dehors de ceux de l’organisation en charge du développement.|
|[[Tests Beta]]|beta testing|Tests opérationnels simulés ou réels effectués sur un site externe, par des rôles à l'extérieur de l'organisation de développement.|
|[[Wiki/Glossary/Sans titre|Sans titre]]|change-related testing||
|[[Logiciel commercial sur étagère]]|commercial  <br>off-the-shelf software (COTS)|Produit logiciel qui est développé pour le marché de façon générale, c'est-à-dire pour un grand nombre de clients, et qui est livré à de nombreux clients dans un format identique.|
|[[Test de composant]]|component  <br>testing|le test de composants logiciels individuels.|
|[[test d’intégration de composants]]|component integration testing|test effectué pour découvrir des défauts dans les interfaces et les interactions entre des composants intégrés.|
|[[Test de confirmation]]|confirmation testing|tests dynamiques effectués après la correction de défauts dans le but de confirmer que les défaillances causées par ces défauts ne se produisent plus.|
|[[Tests d'acceptation contractuelle]]|contractual  <br>acceptance testing|tests d'acceptation effectués pour vérifier si un système satisfait à ses exigences contractuelles.|
|[[Test fonctionnel]]|functional testing|Test réalisé pour évaluer la conformité d'un composant ou d'un système aux exigences. Voir aussi : test boîte-noire  <br>fonctionnelles. (ISO 24765)|
|[[Analyse d'impact]]|impact  <br>analysis|L'identification de tous les produits d’activités touchés par un changement, y incluant une estimation des ressources nécessaires pour accomplir le changement.|
|[[Tests d’intégration]]|integration testing|tests effectués pour montrer des défauts dans les interfaces et interactions de composants ou systèmes intégrés.|
|[[Test de maintenance]]|maintenance  <br>testing|Processus de modification d'un composant ou d'un système après la livraison pour corriger les défauts, améliorer les attributs de qualité ou s'adapter à un environnement modifié.|
|[[Test non-fonctionnel]]|non-functional testing|Test effectué pour évaluer la conformité d'un composant ou d'un système avec les exigences non fonctionnelles.|
|[[Tests d’acceptation opérationnelle]]|operational  <br>acceptance testing|test opérationnel en phase de test d'acceptation, généralement effectué dans un environnement opérationnel (simulé) par l' exploitation et/ou le personnel de l'administration des systèmes en se concentrant sur les aspects opérationnels, par exemple la reprise (après incident), le comportement des ressources, la facilité d’installation et la conformité technique.|
|[[Test de régression]]|regression testing|tests d’un programme préalablement testé, après une modification, pour s’assurer que des défauts n’ont pas été introduits ou découverts dans des parties non modifiées du logiciel, comme suites des modifications effectuées.|
|[[Test d'acceptation réglementaire]]|regulatory  <br>acceptance testing|Tests d'acceptation effectués pour vérifier si un système est conforme aux lois, politiques et règlements applicables.|
|[[Modèle de développement séquentiel]]|sequential development model|Un type de modèle de cycle de vie de développement selon lequel un système achevé est développé de manière linéaire en plusieurs phases distinctes et successives, sans chevauchement entre elles.|
|[[Tests d’intégration système]]|system  <br>integration testing|Tester la combinaison et l'interaction des systèmes.|
|[[Tests système]]|system testing|Tester un système intégré pour vérifier qu'il répond aux exigences spécifiées.|
|[[Environnement de test]]|test  <br>environment|Environnement contenant le matériel, les instruments, les simulateurs, les outils logiciels et les autres éléments de support nécessaires à l’exécution d’un test.|
|[[Niveau de test]]|test level|Une instanciation spécifique d'un processus de test.|
|[[Type de test]]|test type|Groupe d'activités de test basées sur des objectifs de test spécifiques visant des caractéristiques spécifiques d'un composant ou d'un système.|
|[[Tests d'acceptation utilisateur]]|user acceptance testing|Tests d'acceptation effectués dans un environnement opérationnel réel ou simulé par les utilisateurs prévus en mettant l'accent sur leurs besoins, leurs exigences et leurs processus métier.|
|[[Test boîte-blanche]]|white-box  <br>testing|Test basé sur une analyse de la structure interne du composant ou système.  <br>Synonymes : Test de boîtes transparentes, Test basé sur le code, Test de boîtes de verre, Test de couverture logique, Test dirigé par la couverture logique, Test structurel, Test basé sur la structure.|
|[[Test d’acceptation]]|acceptance testing|Test formel conduit par le business déterminant si le système satisfait où non au critères d’acceptance, basé sur les besoins utilisateurs et les attentes.|
|[[Test Statique]]|Static Test|Test qui n'implique pas l'exécution d'un élément de test, telle que du code, l’exécution d’un programme, etc. Il consiste donc à vérifier le code, les documents d’exigences et de conceptions, pour en prévenir les défauts.|
|[[développement piloté par les tests]]|TDD (Test driven development)|Une technique de développement de logiciels selon laquelle les cas de test sont développés, et souvent automatisés, puis le logiciel est développé de manière incrémentale pour passer ces cas de test.|
|[[Objet de test]]|test object|Composant ou système à tester.  <br>Voir aussi : Article de test|
|[[Objectif de test]]|test objective|une raison ou but de la conception et l’exécution d’un test.|

  
  

### Chapitre 4 :

### Lexique

#### Lexique

|Mot|Word|Définition|
|---|---|---|
|[[Technique de test boîte-noire]]|black-box test technique|procédure documentée pour élaborer et sélectionner des cas de tests basés sur une analyse des spécifications, soit fonctionnelles soit non-fonctionnelles, d’un composant ou système, sans faire référence à ses structures internes.  <br>Synonymes : Technique boîte noire, technique basée sur les spécifications, technique de test basée sur les spécifications|
|[[Valeur limite]]|boundary value|Une valeur minimale ou maximale d'une partition d'équivalence ordonnée.|
|[[Analyse des valeurs limites]]|boundary value analysis|une technique de conception de tests boîte noire dans laquelle les cas de tests sont conçus sur la base des valeurs limites.  <br>Voir aussi : Valeur limite|
|[[Test basé sur une checklist]]|checklist-based testing|Une technique de conception de tests basée sur l'expérience selon laquelle le testeur expérimenté utilise une liste de haut niveau d'éléments à noter, à vérifier, ou à se rappeler, ou un ensemble de règles ou de critères en fonction desquels un produit doit être vérifié.|
|[[Couverture - couverture de test]]|Coverage|le degré, exprimé en pourcentage, selon lequel un élément de couverture spécifié a été exécuté lors d’une suite de test.|
|[[Couverture des décisions]]|decision coverage|La couverture des résultats des décisions|
|[[Table de décision]]|decision table|Un tableau utilisé pour montrer des ensembles de conditions et les actions qui en résultent.|
|[[Test par tables de décisions]]|decision table testing|une technique de conception des tests boîte noire dans laquelle les cas de tests sont conçus pour exécuter les combinaisons d’entrées et/ou de stimuli (causes) présentes dans une table de décision.  <br>Voir aussi : Table de décision|
|[[Partition d’équivalence]]|equivalence partitioning|une portion d’un domaine d’entrée ou de sortie pour laquelle le comportement d’un composant ou système est supposé être le même, basé sur ces spécifications.  <br>Synonyme : classe d'équivalence|
|[[Estimation d’erreur]]|error guessing|Technique de test qui consiste à dériver les tests sur la base de la connaissance des défaillances passées ou de la connaissance générale des modes de défaillance|
|[[Technique de test basée sur l'expérience]]|experience-based test technique|Procédure pour obtenir et/ou sélectionner des cas de test basée sur l'expérience du testeur, sa connaissance et son intuition.  <br>Synonyme : technique basée sur l'expérience|
|[[Tests exploratoires]]|exploratory testing|Une approche des tests par laquelle les testeurs conçoivent et exécutent dynamiquement des tests en fonction de leurs connaissances, de l'exploration de l'élément testé et des résultats des tests précédents|
|[[Transition d’état]]|state transition|Une transition entre deux états d’un composant ou système|
|[[Test des transitions d’état]]|state transition testing|Une technique de test de boîte-noire utilisant un diagramme états-transitions ou une table d'état pour dériver des cas de test afin d'évaluer si l'élément de test exécute avec succès des transitions valides et bloque les transitions invalides.  <br>Voir aussi : Test N-switch  <br>Synonyme : Test de machines à états finis|
|[[Couverture des instructions]]|statement coverage|le pourcentage des instructions exécutables qui ont été exécutées par une suite de tests.|
|[[Technique de test]]|test technique|Procédure utilisée pour dériver et/ou sélectionner les cas de test.  <br>Synonymes : technique de conception de cas de test, technique de spécification de test, technique de conception de test|
|[[Test de cas d’utilisation]]|use case testing|Technique de test boîte noire selon laquelle les cas de tests sont conçus pour exécuter des scénarios de cas d’utilisation.  <br>Synonymes : tests de scénarios, tests de scénarios utilisateurs|
|[[Technique de test boîte-blanche]]|white-box test technique|Procédure permettant de dériver et/ou de sélectionner des cas de test sur la base d'une analyse de la structure interne d'un composant ou d'un système.  <br>Synonymes : technique de test structurel, technique de test basé sur la structure, technique basée sur la structure, technique boîte-blanche|

  
  

## 4.1 Catégories de techniques de test

Les techniques de test ont pour but/fonction d’aider à identifier les conditions, les cas et les données de test.

**4.1.1 (K2) Expliquer les caractéristiques, les points communs et différences entre les techniques de test boite-noire, boite-blanches et basées sur l’expérience.**

- Les facteurs impliqués dans le choix de la technique de test sont:
    - Type et complexité du composant ou des systèmes
    - Normes réglementaires
    - Exigences client ou contractuelles
    - Niveaux et types de risques
    - Objectifs du test
    - Documentation disponible
    - Connaissances et compétences des testeurs
    - Outils disponibles
    - Temps et budget
    - Modèle de cycle de vie du développement logiciel
    - Utilisation prévue du logiciel
    - Expérience antérieure de l’utilisation des techniques de test sur le composant ou le système à tester
    - Types de défauts attendus dans le composant ou le système

|Techniques|Boite-noire|Boite-blanche|Basées sur l’expérience|
|---|---|---|---|
|synonymes|Test techniques comportementales  <br>Test techniques basées sur le comportement|Test techniques structurelles  <br>Test techniques basées sur la structure|N/A|
|Focus|se concentre sur l’entrée et la sortie de l’objet de test, ignorant son contenu  <br>  <br>==**Entrées**== → Test → ==**Sorties**==|Se concentre sur la structure et le traitement à l’interne de l’objet de test  <br>Entrées →  <br>==**Test**== → Sorties||
|Se base|sur la base de test (ex. documents d’exigences formelles, spécifications, cas d’utilisation, user stories ou processus métier|sur l’analyse de l’architecture, de la conception détaillée, de la structure interne ou du code|sur l’expérience des développeurs, des testeurs et des utilisateurs|

Les caractéristiques des techniques de test

- Boite-noire incluent ;
    - Les conditions, les cas et les données de test d’une base de test pouvant inclure des exigences logicielles, des spécifications, des cas d’utilisation, et des user story
    - Les cas de test peuvent être utiliser pour détecter les écarts entre les exigences et l’implémentation des exigences, ainsi que les défauts au niveau des exigences
    - La couverture est mesurée en fonction des éléments de base de test évalués et de la technique appliquée à cette base de test
- Boite-blanche incluent :
    - Les conditions, les cas et les données de test sont dérivés d’une base de test qui peut inclure le code, l’architecture logicielle, la conception détaillée ou toute autre source d’information concernant la structure du logiciel
    - La couverture est mesurée en fonction des éléments testés au sein d’une structure donnée (ex. code ou interface)
    - les spécifications sont souvent utilisées comme source d’information supplémentaire pour déterminer le résultat attendu des cas de test
- Basée sur l’expérience incluent :
    - Les conditions, les cas et les données de test sont dérivées d’une vase de test qui peut inclure les connaissances et l’expérience des testeurs, développeurs, utilisateurs et autres parties prenantes. (expérience et connaissance qui inclut l’utilisation, l’environnement, les défauts probables et la répartition de ces défauts)

## **4.2 Technique de test boite-noire**

**4.2.1 (K3) Appliquer la technique des partitions d’équivalence pour produire des cas de test à partir d’exigences des données**

Divisions des données en partitions (=classes d’équivalence), tous les éléments d’une partition doivent être traité de la même manière (données de même type), les données valides et invalides sont partitionnées séparément.

- Les valeurs valides sont les valeurs acceptées par le composant ou le système. La partition contenant les valeurs valides est appelée “partition d’équivalence valide”.
- Les valeurs invalides sont les valeurs rejetées par le composant ou le système. La partition contenant les valeurs invalides est appelée “partition d’équivalence invalide”
- Les partitions peuvent être identifiées pour tout élément de données lié à l’objet de test, y compris les entrées, les sorties, les valeurs internes, les valeurs liées au temps (par exemple, avant ou après un événement) et pour les paramètres d’interface (par exemple, les composant intégrés testés pendant les test d’intégration).
- Toutes partitions est sous-partissionable si nécessaire
- Une valeur est exclusive à une seul et unique partition d’équivalence
- Une défaillance pouvant masquer une autre défaillance dans le cas d’un test, il est essentiel d’utiliser individuellement les partissions d’équivalence invalides.

Une couverture de 100% est obtenue avec cette technique, si toutes valeurs des partitions d’équivalence, qui ont été identifiées, sont utilisées

$C \% = \frac v P \\$

**4.2.2 (K3) Appliquer l’analyse des valeurs limites pour produire des cas de test à partir de l’exigences des données**

L’analyse des valeurs limites est une extension des partitions équivalentes utilisables uniquement pour les partition ordonnée, composée de données numériques/séquentielles. Les valeurs minimal (/première) et maximale (/dernière) sont les valeurs limites  
  
Ex. pour un champs acceptant des valeurs entières de 1 à 5  

- partition d’équivalence invalide (trop bas)
    - Valeur limite : 0
- partition d’équivalent valide (1 - 5)
    - Valeur minimal : 1
    - Valeur maximal : 5
- partition d’équivalence invalide (trop élevée)
    - Valeur minimal : 6
    - Valeur maximal : 9

L’analyse et les tests des valeurs limites permettent de détecter les défauts sur l’implémentation incorrecte de ces limites. Il est possible que ces limites soient décalées vers une positions inférieure/supérieure non-prévue, être oubliée ou implémentée avec des limites additionnelles non-demandées. La probabilité de rencontrer des défauts en périphérie des partitions d’équivalence est donc plus élevé, que au sein même de la partition d’équivalence.

L’analyse des valeurs limites est généralement utilisée pour tester les exigences nécessitant une série de valeurs numériques (Age, Date, Heure, etc) et peut être appliquée à tous les niveaux de test.

$C \% = \frac l L \\$

**4.2.3 (K3) Appliquer le test de tables de décision pour produire des cas de test à partir d’exigences données**

Le test de tables de décisions fait parti des techniques de test combinatoire, qui servent à tester la mise en oeuvre des exigences du système en spécifiant comment différentes combinaisons de conditions donnent des résultats différents. elle permet d’identifier toutes les combinaisons importantes et d’identifier les lacunes dans les exigences. Elle s’applique à toutes les situations dont le comportement du logiciel dépend d’un combinaison de conditions, qu’importe le niveau de test.

Les tables de décisions sont un moyen de répertorier les règles métier complexe qu’un système doit mettre en oeuvre, en identifiant les conditions (ex. entrées) et les actions résultantes (ex. sorties) du système. Les lignes du tableau sont ces conditions et actions résultantes, avec les conditions en premier, tandis que les colonnes sont les différentes combinaisons (/cas) possibles entre ces conditions et actions. Les valeurs de ces conditions et actions sont indiqués sous forme de valeurs boléennes (V/F, 0/1) ou discrètes (vert, rouge, bleu).

La couverture minimal pour les test de table de décision est minimum un cas type par conditions

$C \% = \frac c L \\$

- Exemple
    
    |   |   |   |   |   |
    |---|---|---|---|---|
    |Conditions|Rule 1|Rule 2|Rule 3|Rule 4|
    |Username (T/F)|F|T|F|T|
    |Password (T/F)|F|F|T|T|
    |Output (E/H)|E|E|E|H|
    
    Legend:
    
    - T – Correct username/password
    - F – Wrong username/password
    - E – Error message is displayed
    - H – Home screen is displayed
    
    Interpretation:
    
    - Case 1 – Username and password both were wrong. The user is shown an error message.
    - Case 2 – Username was correct, but the password was wrong. The user is shown an error message.
    - Case 3 – Username was wrong, but the password was correct. The user is shown an error message.
    - Case 4 – Username and password both were correct, and the user navigated to homepage
- Exemple 2
    
      
    
    ![[Untitled 31.png|Untitled 31.png]]
    
    La table de décision pour le champs ci-dessus sera le suivant :
    
    |   |   |   |   |   |   |   |   |   |
    |---|---|---|---|---|---|---|---|---|
    |Conditions|Case 1|Case 2|Case 3|Case 4|Case 5|Case 6|Case 7|Case 8|
    |Format|.jpg|.jpg|.jpg|.jpg|Not .jpg|Not .jpg|Not .jpg|Not .jpg|
    |Size|Less than 32kb|Less than 32kb|>= 32kb|>= 32kb|Less than 32kb|Less than 32kb|>= 32kb|>= 32kb|
    |resolution|137*177|Not 137*177|137*177|Not 137*177|137*177|Not 137*177|137*177|Not 137*177|
    |Output|Photo uploaded|Error message resolution mismatch|Error message size mismatch|Error message size and resolution mismatch|Error message for format mismatch|Error message format and resolution mismatch|Error message for format and size mismatch|Error message for format, size, and resolution mismatch|
    

**4.2.4 (K3) Appliquer le test des transitions d’état pour produire des cas de test à partir d’exigences**

Identifier les différents états, transitions et construisez un diagramme de transition d’état.

- Un diagramme de transition d’état montre les états possible du logiciel, ainsi que les entrées (=événements), les sorties (=actions) et les transitions entre les états.
    - Un état est une étape par laquelle le composant/système passe  
        (ex: 1ier/2ème/3ème essaie )  
        
    - Un événement est une entrée et résulte en un transition  
        (ex: cliquer sur valider, mot de passe oublié)  
        
    - Un transition est initié par un événement
    - Une actions est une sortie et est déclenchée par changement d’état  
        (ex: verrouillage de l’application, affiche d’une message d’erreur)  
        
- Un table de transition d’état montre toutes les transitions valides et potentiellement invalides entre les états, ainsi que les événements et les actions résultat d’une transition valide.
- La couverture est exprimé en pourcent et est calculée en divisant les états et transitions testées par le total d’état et de transitions dans l’objet du test.

- Exemple

  

**4.2.5 (K2) Expliquer comment produire des cas de test à partir d’un cas d’utilisation**

  

Acteur (utilisateur humain, matériel externe ou autres composants ou systèmes)

sujets (le composant ou système auquel le cas d’utilisation est appliqué)

Diagrame de cas d’utilisation

  

- exemple
    
    ![[Untitled 1 1.png|Untitled 1 1.png]]
    
    ![[Untitled 2 1.png|Untitled 2 1.png]]
    
      
    
      
    

  

## 4.3 Technique de test boite-blanche

Les techniques de test “boite-blanche” se base sur la structure interne de l’objet du test et peuvent être utilisé à tous les niveaux de test. Dans cette section, nous parlerons seulement de deux tests principalement utilisé dans le test de composants.

**4.3.1 (K2) Expliquer la couverture des instructions**

Le test d’instruction exerce les instructions exécutable du code.  
La couverture est exprimée en pourcentage et se calcule en divisant le nombre d’instruction exécutée par le total d’instruction exécutable dans l’objet du test.  

**4.3.2 (K2) Expliquer la couverture des décisions**

Le test de décisions exerce les décisions, donc les conditions dans le code et test le code exécuté en fonction conditions activées (cf. if, else, case, etc.). Un cas est donc à prévoir pour chaque condition, que ce soit un if-elif-else, case, etc.

La couverture est exprimée en pourcentage et se calcule en divisant le nombre de résultat de décision exécutés par le total de résultat de décision de l’objet du test.

**4.3.3 (K2) Expliquer l’intérêt de la couverture des instructions et des décisions**

test des instructions

- Couverture du code moindre que le test des décisions quand à 100% de couverture
- Permet de trouver les défauts, dans le cas d’instruction FALSE non-explicité

test des décisions

- Garanti la couverture de 100% des instruction, mais pas l’inverse

## 4.4 Technique de test basées sur l’expérience

Les techniques de test basées sur l’expériences se basent sur les compétences, l’intuition et l’expérience du testeurs avec des application et des technologies similaires. Elles permettent d’identifier les tests difficilement identifiable avec des techniques plus systématiques. Le degrés d’efficacité et de couverture est variable dépendant l’approche et l’expérience du testeur. Tandis que la couverture peut être difficile à évaluer, voir ne pas être mesurable avec ces techniques.

Les techniques les plus communes sont :

- L’estimation d’erreur
- Le test exploratoire
- Le test basé sur la checklists

**4.4.1 (K2) Expliquer l’estimation d’erreur**

L’estimation d’erreur est une technique anticipant les erreurs, les défauts et les défaillances sur base des connaissances du testeur (ex. fonctionnement antérieur de l’application, types d’erreurs récurrentes commises par les développeurs, les défaillances précédentes dans les autres applications, etc.)

Une approche de cette technique consiste à créer une liste d’erreurs, de défauts et de défaillances possibles, puis de concevoir des tests les exposant. La rédaction de la liste peut se reposer sur l’expérience, les données des défauts et des défaillances, et les connaissances générales sur les causes des défaillances logicielles.

**4.4.2 (K2) Expliquer le test exploratoire**

Test informel (non-prédéfinis) conçu, exécuté, enregistré et évalué dynamiquement pendant l’exécution des tests. Il permet d’en apprendre plus sur le composant ou le système, et pour créer des tests supplémentaire pour les parties ayant besoin de plus de test.

Il peuvent être réalisé durant des sessions dans un temps imparti afin de structurer l’activité, sur base de charte comprenant les objectifs du test. Des fiches de sessions peuvent être utilisées pour documenter les étapes et constatations réalisées.

Les tests exploratoires sont utiles pour compenser l’absence ou la faible qualité des spécifications, de fortes contraintes de temps, et permettent de compléter les autres techniques de test.

**4.4.3 (K2) Expliquer le test basé sur des checklists**

Les tests basé sur des checklists sont des tests fonctionnels ou non-fonctionnels couvrant les conditions de tests exprimées sous forme de listes à cocher. Ces conditions peuvent être élaborée sur le besoin utilisateur, la compréhension des défaillances logicielles, etc. En l’absence de cas de tests détaillés, les listes peut être de haut niveau donnant des lignes directrices et un certain degré de cohérence, afin de structurer.

### Chapitre 5 : Gestion des tests

### Lexique

#### Lexique

|Mot|Word|Définition|
|---|---|---|
|[[Gestion de configuration]]|configuration management|une discipline appliquant une direction et surveillance technique et administrative pour identifier et documenter les caractéristiques fonctionnelles et physiques d’un élément de configuration, contrôler les modifications de ces caractéristiques, enregistrer et informer des modifications et états d’implémentation, et vérifier la conformité avec des exigences spécifiées.|
|[[Gestion des défauts]]|defect management|Processus qui consiste à identifier et à enregistrer les défauts, à les classer, à les examiner, à prendre des mesures pour les résoudre et à les clôturer lorsqu'ils sont résolus.  <br>Voir aussi : Gestion des incidents|
|[[Rapport de défaut]]|defect report|Documentation de la survenance, de la nature et de l'état d'un défaut.  <br>Voir aussi : Rapport d'incident  <br>Synonymes : rapport de bogue|
|[[Critère d’entrée]]|entry criteria|L'ensemble des conditions pour le démarrage formel d'une tâche définie.  <br>Synonyme : définition du prêt|
|[[Critère de sortie]]|exit criteria|L'ensemble des conditions pour la complétion formelle d'une tâche définie.  <br>Synonymes : critères d'achèvement, critères d'achèvement des tests, définition du terminé|
|[[Risque produit]]|product risk|Un risque directement lié à l’objet de test. Voir aussi : Risque|
|[[Risque projet]]|project risk|Un risque qui a une incidence sur la réussite du projet.  <br>Voir aussi : Risque|
|[[Test basé sur les risques]]|RBT (risk-based testing)|Tests pour lesquels la gestion, la sélection, la priorisation et l'utilisation des activités et des ressources de test sont basées sur les types de risque et les niveaux de risque correspondants.|
|[[Risque]]|risk|Un facteur qui pourrait avoir des conséquences négatives à l'avenir. généralement exprimé comme un impact et une probabilité.|
|[[Niveau de risque]]|risk level|Mesure qualitative ou quantitative d'un risque défini par l'impact et la probabilité.  <br>Synonyme : Exposition au risque|
|[[Approche du test]]|test approach|l’implémentation de la stratégie de test pour un projet spécifique|
|[[Contrôle des tests]]|test control|Une tâche de gestion des tests qui traite du développement et de l’application d’un ensemble d’actions correctives pour remettre un projet de test sur les rails  <br>quand les métriques de suivi indiquent une déviation par rapport à ce qui a été  <br>prévu.  <br>Voir aussi : Gestion des tests|
|[[Estimation des tests]]|test estimation|Approximation calculée d’un résultat lié à divers aspects du test (ex. : effort accompli, date d’achèvement, coûts induits, nombre de cas de test, etc.) qui est utilisable malgré des données d’entrée incomplètes, incertaines ou altérées.|
|[[test manager]]|test manager|Personne responsable de la gestion de projet des activités et des ressources de test et de l'évaluation d'un objet de test. La personne qui dirige, contrôle, gère l’organisation et règle l’évaluation d’un objet de test.|
|[[Pilotage des tests]]|test monitoring|Une activité de gestion des tests qui comprend la vérification de l'état des activités de test, l'identification de tout écart par rapport à l'état planifié ou attendu, et le reporting aux parties prenantes.|
|[[Plan de test]]|test plan|Documentation décrivant les objectifs de test à atteindre et les moyens et le calendrier pour les atteindre, organisée pour coordonner les activités de test.|
|[[Planification de test]]|test planning|Activité de définition ou de mise à jour d’un plan de test.|
|[[Rapport d’avancement de test]]|test progress report|Un rapport de test produit à intervalles réguliers sur l'état d'avancement des activités de test par rapport à une base de référence, aux risques et aux solutions alternatives nécessitant une décision.  <br>Synonyme : Rapport sur le statut des tests|
|[[Stratégie de test]]|test strategy|Documentation qui exprime les exigences génériques pour tester dans le cadre d'un ou de plusieurs projets exécutés au sein d'une organisation, fournissant des détails sur la façon dont les tests doivent être effectués, et qui est alignée sur la politique de test.  <br>Synonyme : Stratégie de test organisationnel|
|[[Rapport de synthèse de test]]|test summary report|Un rapport de test qui fournit une évaluation des éléments de test en comparaison avec les critères de sortie.  <br>Synonyme : rapport de test|
|[[tester]]|tester|Un professionnel qualifié qui participe aux tests d'un composant ou d'un système|

  
  

### 5.1 Organisation des tests

**5.1.1 (K2) Expliquer les bénéfices et inconvénients du test indépendant**

Les tests peuvent être réalisé par une personne dédié à ce rôle (testeur), ou une autre personne (client, business, etc.). L’indépendance du testeur le rend plus efficace à détecter les défauts, n’étant pas soumis au biais de l’auteur, malgré son expertise dans son domaine.

Différents degrés d’indépendances:

- Les développeurs testent leur propre code (pas de testeur)
- Les développeurs testent les produits de leur collègues (peer review, testeur indépendants au sein de l’équipe de dev/projet)
- Des testeurs interne à l’organisation, testent les produits et rapport à la direction du projet/général
- Des testeurs issus du business ou de la communauté d’utilisateur, ou des testeurs spécialisé (utilisabilité, sécurité, performance, conformité réglementaire ou portabilité)
- Des testeurs externe à l’organisation travaillant sur site (insourcing) ou hors-site (outsourcing)

Les avantages :

- La différence (connaissances, approches techniques et biais) entre les testeurs et les développeurs, leur permet de détecter des types de défaillances différentes
- Un testeur indépendant peut vérifier, contester ou réfuter les hypothèses formulées par les parties prenantes au cours de la spécification et de l’implémentation du système.

Les inconvénients:

- L’isolement des testeurs de l’équipe de développement, entrainant un manque de collaboration, des retards dans les retours et/ou une relation conflictuelle
- Perte du sens de la qualité de la part des développeurs
- Les testeurs indépendant sont perçu comme un goulot d’étranglement et tenu responsable des retards
- Les informations importantes ne sont pas transmises aux testeurs indépendants

**5.1.2 (K1) Identifier les tâches d’un Test Manager et d’un testeur**

Le test manager est responsable du processus de test et de la bonne conduite des activités de test.  
La gestion des tests peut être assumé par un test manager professionnel, un chef de projet ou un responsable du développement/ de l’assurance qualité.  

Dans le cas de projet impliquant plusieurs équipes sur un projet, le test manager dispose de test leader, qui chacun dirigent une équipe.

|   |   |   |
|---|---|---|
||Test manager|Tester|
|Tâches|• Développer et revoir une politique et une stratégie de test pour l’organisation  <br>• Planifier les activités de test en tenant compte du contexte (objectifs, risques, etc.)  <br>Ce qui inclut la sélection des approches, l’estimation du temps, de l’effort et du coût des tests, de l’acquisition des ressources, de la définition des niveau et des cycles de tests et la planification de la gestion des défauts.  <br>• Rédiger et mettre à jour les plans de tests  <br>• Coordonner le plan de test avec les chefs de projet, les product owners et autres parties prenantes  <br>• Partager différents aspects des tests avec d’autres activités du projet, comme la planification de l’intégration  <br>• Lancer l'analyse, la conception, l'implémentation et l'exécution des tests, suivre l'avancement et les résultats des tests, et vérifier le statut des critères de sortie (ou de la définition du terminé)  <br>• Préparer et fournir des rapports d'avancement des tests et des rapports de synthèse des tests basés sur les informations recueillies  <br>• Adapter la planification en fonction des résultats et de l’avancement des tests (parfois documentés dans les rapports d'avancement des tests et/ou dans les rapports de synthèse des tests pour d’autres tests déjà réalisés sur le projet) et prendre toutes les mesures nécessaires au contrôle des tests  <br>• Aider la mise en place du système de gestion des défauts et à la gestion adéquate de la configuration des testware  <br>• Introduire les métriques appropriées pour mesurer l’avancement des tests et évaluer la qualité des tests et du produit  <br>• Accompagner la sélection et la mise en oeuvre des outils pour soutenir le processus de test, y compris recommander le budget pour la sélection des outils (et éventuellement l'achat et/ou le support), allouer du temps et des ressources pour des projets pilotes et apporter un accompagnement continu à l'utilisation du ou des outils  <br>• Décider de l'implémentation du ou des environnements de test  <br>• Promouvoir et soutenir les testeurs, l'équipe de test et le métier du test au sein de l'organisation  <br>• Développer les compétences et les carrières des testeurs (par exemple, par le biais de plans de formation, d'évaluations de performance, de coaching, etc.).||

  

### 5.2 Planification et estimation des tests

  

**5.2.1 (K2) Résumer l’objectif et le contenu d’un plan de test**

  

**5.2.2 (K2) Expliquer les différences entre plusieurs stratégies de test**

  

**5.2.3 (K2) Donner des exemples de critères d’entrée et de critères de sortie possibles**

  

**5.2.4 (K3) Appliquer les informations de priorité et de dépendances techniques et logiques pour ordonnancer l’exécution d’un ensemble donnée de cas de test**

  

**5.2.5 (K1) Identifier des facteurs qui influencent l’effort au test**

  

**5.2.6 (K2) Expliquer les différences entre deux techniques d’estimation : la technique basée sur des métriques et la technique basée sur l’expertise**

  

### 5.3 Pilotage et contrôle des tests

  

**5.3.1 (K1) Se souvenir des métriques utilisées pour les tests**

  

**5.3.2 (K2) Résumer les objectifs, contenus et destinataires des rapports de test**

  

### 5.4 Gestion de configuration

  

**5.4.1 (K2) Résumer comment la gestion de configuration vient en appui des tests**

  

### 5.5 Risques et tests

  

**5.5.1 (K1) Définir le niveau de risque à partir de la probabilité d’occurrence et de l’impact**

  

**5.5.2 (K2) Décrire la différence entre les risques projet et les risques produit**

  

**5.5.3 (K2) Décrire en utilises des exemples, comment l’analyse des risques produit peut influencer la complétude et le périmètre des tests**

  

### 5.6 Gestion des défauts

  

**5.6.1 (K3) Écrire un rapport de défaut couvrant les défauts trouvés pendant les tests**

  

  

### Chapitre 6 :

### Lexique

#### Lexique

|Mot|Word|Définition|
|---|---|---|
|[[Tests Alpha]]|alpha testing|test opérationnel réel ou simulé conduit dans l’environnement de test du développement par des rôles en dehors de ceux de l’organisation en charge du développement.|
|[[Tests Beta]]|beta testing|Tests opérationnels simulés ou réels effectués sur un site externe, par des rôles à l'extérieur de l'organisation de développement.|
|[[Wiki/Glossary/Sans titre|Sans titre]]|change-related testing||
|[[Logiciel commercial sur étagère]]|commercial  <br>off-the-shelf software (COTS)|Produit logiciel qui est développé pour le marché de façon générale, c'est-à-dire pour un grand nombre de clients, et qui est livré à de nombreux clients dans un format identique.|
|[[Test de composant]]|component  <br>testing|le test de composants logiciels individuels.|
|[[test d’intégration de composants]]|component integration testing|test effectué pour découvrir des défauts dans les interfaces et les interactions entre des composants intégrés.|
|[[Test de confirmation]]|confirmation testing|tests dynamiques effectués après la correction de défauts dans le but de confirmer que les défaillances causées par ces défauts ne se produisent plus.|
|[[Tests d'acceptation contractuelle]]|contractual  <br>acceptance testing|tests d'acceptation effectués pour vérifier si un système satisfait à ses exigences contractuelles.|
|[[Test fonctionnel]]|functional testing|Test réalisé pour évaluer la conformité d'un composant ou d'un système aux exigences. Voir aussi : test boîte-noire  <br>fonctionnelles. (ISO 24765)|
|[[Analyse d'impact]]|impact  <br>analysis|L'identification de tous les produits d’activités touchés par un changement, y incluant une estimation des ressources nécessaires pour accomplir le changement.|
|[[Tests d’intégration]]|integration testing|tests effectués pour montrer des défauts dans les interfaces et interactions de composants ou systèmes intégrés.|
|[[Test de maintenance]]|maintenance  <br>testing|Processus de modification d'un composant ou d'un système après la livraison pour corriger les défauts, améliorer les attributs de qualité ou s'adapter à un environnement modifié.|
|[[Test non-fonctionnel]]|non-functional testing|Test effectué pour évaluer la conformité d'un composant ou d'un système avec les exigences non fonctionnelles.|
|[[Tests d’acceptation opérationnelle]]|operational  <br>acceptance testing|test opérationnel en phase de test d'acceptation, généralement effectué dans un environnement opérationnel (simulé) par l' exploitation et/ou le personnel de l'administration des systèmes en se concentrant sur les aspects opérationnels, par exemple la reprise (après incident), le comportement des ressources, la facilité d’installation et la conformité technique.|
|[[Test de régression]]|regression testing|tests d’un programme préalablement testé, après une modification, pour s’assurer que des défauts n’ont pas été introduits ou découverts dans des parties non modifiées du logiciel, comme suites des modifications effectuées.|
|[[Test d'acceptation réglementaire]]|regulatory  <br>acceptance testing|Tests d'acceptation effectués pour vérifier si un système est conforme aux lois, politiques et règlements applicables.|
|[[Modèle de développement séquentiel]]|sequential development model|Un type de modèle de cycle de vie de développement selon lequel un système achevé est développé de manière linéaire en plusieurs phases distinctes et successives, sans chevauchement entre elles.|
|[[Tests d’intégration système]]|system  <br>integration testing|Tester la combinaison et l'interaction des systèmes.|
|[[Tests système]]|system testing|Tester un système intégré pour vérifier qu'il répond aux exigences spécifiées.|
|[[Environnement de test]]|test  <br>environment|Environnement contenant le matériel, les instruments, les simulateurs, les outils logiciels et les autres éléments de support nécessaires à l’exécution d’un test.|
|[[Niveau de test]]|test level|Une instanciation spécifique d'un processus de test.|
|[[Type de test]]|test type|Groupe d'activités de test basées sur des objectifs de test spécifiques visant des caractéristiques spécifiques d'un composant ou d'un système.|
|[[Tests d'acceptation utilisateur]]|user acceptance testing|Tests d'acceptation effectués dans un environnement opérationnel réel ou simulé par les utilisateurs prévus en mettant l'accent sur leurs besoins, leurs exigences et leurs processus métier.|
|[[Test boîte-blanche]]|white-box  <br>testing|Test basé sur une analyse de la structure interne du composant ou système.  <br>Synonymes : Test de boîtes transparentes, Test basé sur le code, Test de boîtes de verre, Test de couverture logique, Test dirigé par la couverture logique, Test structurel, Test basé sur la structure.|
|[[Test d’acceptation]]|acceptance testing|Test formel conduit par le business déterminant si le système satisfait où non au critères d’acceptance, basé sur les besoins utilisateurs et les attentes.|
|[[Test Statique]]|Static Test|Test qui n'implique pas l'exécution d'un élément de test, telle que du code, l’exécution d’un programme, etc. Il consiste donc à vérifier le code, les documents d’exigences et de conceptions, pour en prévenir les défauts.|
|[[développement piloté par les tests]]|TDD (Test driven development)|Une technique de développement de logiciels selon laquelle les cas de test sont développés, et souvent automatisés, puis le logiciel est développé de manière incrémentale pour passer ces cas de test.|
|[[Objet de test]]|test object|Composant ou système à tester.  <br>Voir aussi : Article de test|
|[[Objectif de test]]|test objective|une raison ou but de la conception et l’exécution d’un test.|

  
  

  

  

### BNTQB (Belgium and Netherlands Testing Qualifications Board)

> [!info] Software Testing: wij zijn er voor de testers | BNTQB  
> Software testen is ons vak én onze passie.  
> [http://www.bntqb.org/](http://www.bntqb.org/)  

## ISTQB (International Software Testing Qualification Board)

  

examen blanc : [https://www.gasq.org/fr/certification/exemples-dexamens.html](https://www.gasq.org/fr/certification/exemples-dexamens.html)

### Synthèse

Testing

debugging

Condition de test

objectif de test

Type de test

- component testing
    - basé sur
    - adapté à telle situation
- system testing
    - basé sur
- checklist based testing
- Black box
- white box

importance de faire varier les conditions de test pour trouver de nouveaux défauts

comment le testing s’intégre à l’assurance qualité

En quoi se compose l’analyse des tests

white box , black box testing les différences

modèle de développement incrémental

maintenance testing

forma review

roles in formal review

activities carries out within formal review

types and charactérisitic of reviews

static testing

decision coverage

exploratory testing

boundary value analysis

transition diagrame

  

  

---

- Old
    
    Le test logiciel est une méthode permettant d’évaluer la qualité d’un logiciel et de réduire le risque de défaillance. La nécessité de réduire la défaillance logicielle a émergé avec leur adoption de plus en plus vaste dans nos vies, de l’application business (ex: banque) jusqu’aux produits de consommation (ex: voiture); Et dont les conséquences peuvent aller de la perte de temps ou d’argent , à la blessure ou la mort.
    
    Une préconception commune des tests est qu'ils consistent uniquement à exécuter des tests, et à vérifier les résultats obtenus. Or le test de logiciels est un processus comprenant de nombreuses activités différentes, telles que la planification des tests, l'analyse, la conception, la mise en œuvre des tests, etc.
    
    De plus, un test n’implique pas nécessairement l’exécution d’un composant ou d’un système. On parle de test dynamique, lorsqu’un composant ou un système est exécuté, en opposition aux tests statiques, qui consiste à vérifier les exigences, les user stories et le code source.
    
    Ensuite une autre préconception commune des tests est qu’ils se concentrent uniquements sur les spécifications, telle que les exigences, les userstories, etc. Alors qu’ils incluent aussi une phase de validation, impliquant de vérifier si le système répondra aux besoins des utilisateurs et autres parties prenantes dans l’environnement opérationnel.
    
    Enfin, les tests sont organisés et menés différemment dépendant du cycle de développement, afin de s’adapter au contexte.
    
    1. Identifier les objectifs typiques des tests (K1)
        
        Pour tous project, les objectifs de test peuvent être les suivantes:
        
        - prévenir les défauts en évaluant les produits de travail, telle que les exigences, les récits uitilisateur, la conception et le code
        - Vérifier que toutes les exigences sont atteintes
        - Assurer quel l’objet du test atteint et remplit les attentes des utilisateurs et des autres partis prenantes
        - Augmenter la confience dans le niveau de qualité de l’objet du test
        - Trouver les défauts et défaillances pour réduire le niveau de risque d’une qualité logicielle inadéquate.
        - Fournir suffisamment d’information aux partis prenantes pour leur permettre de prendre des décisions informées; Spécialement en regard du niveau de qualité de l’objet du test
        - Se conformer et/ou vérifier la conformité aux exigences et nomes contractuelles, légales ou réglementaires.
        
    2. Différencier le test du débogage (K2)
    3. Pourquoi tester est nécessaire
        1. Donner des exemples sur la nécessiter de tester (K2)
        2. Décrire le relation entre le test et l'assurance qualité, et donner des exemples de contribution à une meilleur qualité (K2)
        3. Distinguer l'erreur, du défaut et de la défaillance (K2)
        4. Distinger la cause profonde d'un défaut de ses effets (K2)
    4. Les sept principes de tests
        1. Expliquer les 7 principes de tests (K2)
    5. Les processus de test
        1. Expliquer l'impact du contexte sur le processus de test (K2)
        2. Décrire les activités de tests et les tâches respectives dans le processus de test (K2)
        3. Différencier les résultats de travail qui support le processus de test (K2)
        4. Expliquer l'importance de maintenir la traçabilité les bases du test et le test des résultats de travail.
    6. La psychologie des tests
        1. Identifier les facteurs psychologiques influençant le succès des tests
        2. Expliquer la différence entre l'état d'esprit requis pour les activités de test et l'état d'esprit requis pour les activités de développement
- Old2
    
    Plan de formations
    
    Objectif de connaissance/ niveaux de connaissance
    
    ![[Untitled 3 1.png|Untitled 3 1.png]]
    
    - Fondamentaux des tests (K2)
        1. Pourquoi les tests sont-ils nécessaires?
            1. Contexte des systèmes logiciels (K1)
                
                > Les technologies étant de plus en plus présentes dans nos vies, les logiciels qui permettent de les utiliser le sont aussi. Or le logiciel évolue dans le temps, nécessitant un suivi qualitatif afin d'éviter l'apparition de bug et de panne informatique.  
                >   
                > Il est donc essentiel de tester un logiciel avant chaque déploiement, afin de s'assurer que le logiciel réponde au besoin et attente de l'utilisateur (ex: éviter que l'utilisateur désinstalle directement l'application après l'avoir télécharger, car elle ne marche pas)  
                
                Types de conséquences graves des bugs:
                
                - physique: blessures ou mort (ex: bug sur le réseau de train provoquant un accident)
                - Financières : Coût de correction, impact sur les utilisateurs ou clients
                
                Les acteurs concernés:
                
                - L'entreprise
                - Les utilisateurs finaux
                
                Un coût complexe difficile à calculer:
                
                - Temps de correction
                - Pénalités de retard de livraison
                - Impact commercial en terme de confiance et image de société
            2. Origine des défauts (K2)
                
                - Erreur/ error (mistake) : Action humaine produisant un résultat incorrect
                - Défaut (Bug, Faute)/ Defect (Bug, Fault): Une imperfection dans un composant ou un système ce qui conduit à une mauvaise exécution.
                    
                    > Un défaut, si rencontré lors de l'exécution, peut causer la défaillance d'un composant ou d'un système.
                    
                - Défaillance/ faillure : Écart constaté du composant ou système par rappart au livrable, au service ou au résultat attendu
                    
                    > Une défaillance peut être produite quand un défaut est rencontré
                    
                - Incident
                    - Tout événement arrivant pendant les tests qui requiert une vérification
                    - divergence entre le résultat obtenu et le résultat attendu lors de l'exécution d'un test.
                
                Chaine d'événement (De l'erreur à la défaillance):
                
                1. Erreur (humaine)  
                      
                    **Qui mène à...**
                2. Défaut (Bug) dans le code, le résultat de l'erreur  
                      
                    **Qui mène à...**
                3. Défaillance (Résultat de l'exécution d'un défaut dans le code : Le système fait ou ne fait pas ou fait différemment
                
                Cout de correction des défauts augmente selon la phase de détection:
                
                ![[Untitled 4 1.png|Untitled 4 1.png]]
                
                  
                
            3. Test et qualité (K2)
                
                Qualité: "_Degré par lequel un composant système ou un processus atteint des exigences spécifiées ou les attentes des utilisateurs/clients._"
                
                > Avec l'aide des tests, il est possible de mesurer la qualité des logiciels en termes de défaults trouvés, pour des caractéristiques et exigences tant fonctionnelles que non-fonctionnelles
                
                Types de tests
                
                - Fonctionnalité -
                - Fiabilité - sécurité des données de l'utilisateur
                - Utilisabilité - accessibilité du projet, est-il utilisable par les différents groupes d'utilisateurs
                - Rendement - Les rentrées d'argent par rapport aux coûts de développement, de maintenance, etc.
                - Maintenabilité - Capacité à maintenir le développement du projet et à fixer les bugs quelque soit la situation
                - Portabilité - Capacité à porter le projet sur différents systèmes d'exploitation, sur différents supports
                
                Execution des tests > découverte des défauts > Résolution des défauts
                
                Quand arrêter les tests?
                
                - Quand tous les tests ont été réalisé avec succès
                - Quand tous les défauts auront été corrigés
                - Quand il n'y aura plus de défauts
                - Quand tout aura été testé
                - Quand le budget aura été dépensé
                - Quand le logiciel fonctionne
            4. Combien de test est suffisant? (K2)
                
                Plusieurs variables peuvent influencer la décision d'arrêt de test:
                
                - Taille du changement (amélioration d'une fonction existante =/= développement d'une nouvelle fonctionnalité)
                - Importance du changement (fonctionnalité centrale =/= fonctionnalité annexe)
                - Budget
                - Temps
        2. Que sont les tests?
            
            - Revues des documents (y compris le code source) > test unitaire, test lisibilité, commentaire compréhensible de n'importe quelle développeur
            - Planification et contrôle > à chaque étape on planifie les différents types de tests (unitaire, d'intégration, fonctionnel ou d'acceptance) à réaliser, et contrôler que tout les bugs ont été fixé
            - Sélection des conditions de test > Test manuel? automatique? dynamique? Statique?
            - Conception et axe des cas de tests > Rédaction des cas de test, s'assurer que l'on a tester les cas de tests qui pourraient bloquer le fonctionnement du projet (sur base des spécifications du client sur base de ses besoins initiaux)
            - évaluation des critères de sortie > Quelles sont les résultats obtenus? Quelles sont les résultats attendus
            - Reporting > quelles sont les bugs rencontrés? Quelle est leur gravité (mineur? Majeur?)
            - Exécution des activités de clôture des tests à la fin d'une phase > Vérification que chaque étape du cycle de test a bien été réalisé
            
            Les objectifs d'un test peuvent varier dependant de la situation:
            
            1. Trouver des défauts
                - Lors des revues des documents (cahier de charge validé avec le client)
                - Lors du test des composants (lecture du code, tests unitaires)
            2. Acquérir de la confiance
                - Lors de l'acquisition du composant (pv de recette)
                - Lors de test de vérification du bon fonctionnement
                - Lors de tests d'acceptation utilisateurs
            3. Fournir de l'information utile aux prises de décisions
                - Lors des tests d'acceptation d'une livraison
                - A tous les niveaux de test
            4. Prévenir des défauts
                - Lors des tests faits tôt dans le projet, comme des revues de spécifications.
            
              
            
            Test (analyse l'application et fait remonter les défaillances) =/= développeur (développe l'application et fixe les problèmes)
            
            Déboguer = Le processsus de trouver, analyser et éliminer les causes de défaillance
            
            Cas de test = Un ensemble de valeur d'entré, des préconditions d'exécution, des résultats attendus, et des posst conditions d'exécution pour un logiciel ou un composant
            
            Test = Un ensemble d'un ou plusieurs cas de test
            
        3. Les 7 principes généreaux des tests
            1. Principe 1 : Les tests montrent la présence de défaut
                
                > _Les tests peuvent prouver la présence de défauts, mais ne peuvent pas en pouver l'absence. Les tests réduisent la probabilité que des défauts restent cachés dans le logiciel mais, même si aucun défaut n'est découvert, ce n'est pas uen preuve d'exactitude._
                
            2. Principe 2 : les tests exhaustifs sont impossibles
                
                > Il est impossible de réaliser un test qui soit exhaustif et qui comprenne toutes les combinaisons de valeurs d'entrée et de préconditions. Il est nécessaire de définir ce qui doit être tester en définissant les moyens et des objectifs mesurables, afin de restreindre le champ du test.
                
            3. Principe 3: Tester tôt
                
                > De nombreux défauts sont introduits très tôt, dès la phase de SPEC.  
                > Découvrir tôt va empêcher leur propagation et leur multiplication dans les phases ultérieures.  
                > Le cout de correction d'un défaut augment avec le temps.  
                
            4. Principe 4 : Regroupement des défauts
                
                > Cibler l'effort de test au démarrage d'un projet:  
                > - Sur la base de bilans de projets similaires ou de versions précédentes  
                > - Sur la base de l'expérience des architecte, développeurs ou testeurs  
                > Cibler l'effort de test pendant la phase d'exécution  
                > - Afin d'exécuter en priorité les tests portant sur les modules les plus touchés (bogués)  
                
            5. Principe 5 : Paradoxe du pesticide
                
                > - Le pesticide, comme un ensemble de tests, ne tue pas tous les défauts.  
                > - Après plusieurs applications, le pesticide ne tue plus les insectes qui sont dévenus résistants  
                
            6. Principe 6 : Les tests dépendent du contexte
                
                > Contexte d'utilisation:  
                > - Dans quel domaine le logiciel va-t-il être utilisé?  
                > - Quelle est sa criticité  
                > Contexte d'exécution  
                > - Dans quel environnement doit-il fonctionner ?  
                > - Sur quelle plateforme matérielle et logicielle ?  
                > Contexte du projet  
                > - Quelles sont les contraintes de temps / de budget ?  
                > - Quel est le mode de travail utilisé ?  
                
            7. Principe 7 : L'illusion de l'absence de l'erreur
                
                > - Les défauts ne sont pas touts découverts de la même façon.  
                > - Si les besoihns de l'utilisateurs ne sont pas tous couverts par le système celui-ci sera considéré comme bogué même si les test n'ont pas trouvé d'erreur.  
                > - Si les utilisateurs ont mal formulé leurs besoins le logiciel ne sera pas accepté malgré l'absence d'erreur  
                
        4. Processus de tests fondamental
            
            Lexique:
            
            - Politique de test : _Un document de haut niveau décrivant les principes, approches et objectifs majeures de l'organisation ayant trait aux test_
            - Stratégie de test : _un document de haut niveau, définissant pour un programme, les niveaux de tests à exécuter._
            - Niveau de test : _Un groupe d'activité de test qui sont organisées ensemble. Ex: "Test d'intégration", "système d'acceptation", etc._
            - Plan de test : _Un document décrivant l'étendu, les ressources et le planing des activités de test prévues._
            - Procédure de test : Un document spécifiant la séquence d'actions pour l'exécution d'un test connu sous le terme "script de test"
            - Suite de test : Un ensemble de plusieurs cas de test
            - Test de confirmation (= retest) : Test qui exécute des cas de tests qui ont été en échec la dernière fois.
            - Test de non-régression : Test d'un système préalablement testé, après une modification pour assurer qu'il y a pas de défauts ont été nouvellement introduit.
            - critère de sortie: l'ensemble des conditions génériques et spécifiques, convenues avec les responsables pour terminer officiellement un processus
            - Rapport de synthèse de test : un document synthétisant les activités et le résultats de test
            - Testware : Tous les utilitaires et logiciels d'application utilisés conjointement pour planifier, concevoir et exécuter les tests : la documentation, les scripts, les entrées, les résultats attendus, les bases de données...
            
            Tester ne se réduit pas à exécuter des tests
            
            1. Controle
                1. Planification et controle des tests
                    
                    - Implémenter la politique de test et/ou la stratégie de test
                    - Identifier les objectifs des tests, sur la base d'une analyse de risque, ou de priorisation des exigences
                    - déterminer les ressources (personnel, environnement, etc.)
                    - Planifier la tâche de conception de test
                    - Définition de la gestion des défauts
                    - Définir la diapositive pour suivre l'avancement de test
                    
                    Fournir → Plan de test → Mise à jour
                    
                2. Analyse et conception
                    
                    - Déterminer l'objectif du test
                    - Détenrminer l'objet du test
                    - Identifier les données et les conditions de test
                    - Concevoir l'initialisation de l'environnement de test
                    - Conception des cas de test + étapes de test
                    
                    1. Test d'intégration
                3. Implémentation et exécution
                    1. Test système
                    2. Test d'acceptation
                4. Evaluation et reporting
                5. Cloture
                    
                    Cette étape a pour but:
                    
                    - vérifier les livrables
                    - clôturer les rapports ou créer des demandes d'évolution
                    - Fournir les testwares à l'organisation qui se charge de la maintenance
        5. La psychologie des tests
            
              
            
    
    1. Tester pendant le cycle de vie logiciel (K2)
    2. Technique statiques (K2)
    3. Techniques de conception de tests (K3)
    4. Gestion des tests (K3)
    5. Outils de support aux tests (K2)
    6. Avant examen