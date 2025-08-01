---
tags:
  - Wiki/Professional/TestAnalyst/ISTQB
Type: "[[Training]]"
aliases:
  - ISTQB - Niveau Avancé - Analyste de Test
  - CTAL-TA
Link: https://www.istqb.org/certifications/test-analyst
---
# Introduction

Pourcentage de répartition de question à l’examen

minimum 52/80 points correctes (65% , sur 40 questions en 120 minutes)

|   |   |   |
|---|---|---|
|Chapitres|pourcentage/Examen|nombre de questions|
|Chap 1|17%|6|
|Chap 2|2%|1|
|Chap 3|42%|17|
|Chap 4|27%|11|
|Chap 5|7%|3|
|Chap 6|5%|2|

Niveaux de connaissance:

1. Se souvenir (K1)
2. Comprendre (K2)
3. Appliquer (K3)
4. Analyser (K4)

  

# Chapitre 1 : Les taches de l'Analyste de Test dans le processus de Test

#### Lexique

|Mot|Définition|
|---|---|
|[[Analyse de test]]|L'activité qui identifie les conditions de test en analysant les bases de test.|
|[[Article de test]]|Une partie d'un objet de test utilisé dans le processus de test|
|[[Base de référence (gelée)]]|une spécification ou un produit logiciel qui a été  <br>officiellement revu et accepté, qui ensuite sert de base pour des développements futurs, et qui ne  <br>peut être modifié que selon un processus formel de contrôle des modifications|
|[[Base de test]]|L'ensemble des connaissances utilisées comme base pour l'analyse et la conception des tests, telle que les exigences, la documentation, etc.|
|[[BDD]]|Une approche collaborative du développement selon laquelle l'équipe se concentre sur la livraison du comportement attendu d'un composant ou d'un système pour le client, ce qui constitue la base des tests.|
|[[Cas de test de bas niveau]]|Un cas de test avec des valeurs concrètes pour les préconditions, les données d'entrée, les résultats attendus, les postconditions, et une description détaillée des actions (le cas échéant).|
|[[cas de test de haut niveau]]|Un cas de test avec des valeurs abstraites pour les préconditions , les données d'entrée, les résultats attendus, les postconditions et les actions (le cas échéant).|
|[[Conception des tests]]|Activité consistant à dériver et à spécifier des cas de test à partir des conditions de test. Voir aussi : Spécification de la conception des tests|
|[[Test Condition]]|Un aspect testable d'un composant ou d'un système identifié comme une base pour les tests. Donc un aspect des bases de test qui est pertinent pour atteindre des objectifs de test  <br>spécifiques.  <br>Synonymes : exigence de test, situation de test|
|[[Couverture - couverture de test]]|le degré, exprimé en pourcentage, selon lequel un élément de couverture spécifié a été exécuté lors d’une suite de test.|
|[[Critère d’entrée]]|L'ensemble des conditions pour le démarrage formel d'une tâche définie.  <br>Synonyme : définition du prêt|
|[[Critère de sortie]]|L'ensemble des conditions pour la complétion formelle d'une tâche définie.  <br>Synonymes : critères d'achèvement, critères d'achèvement des tests, définition du terminé|
|[[développement piloté par les tests]]|Une technique de développement de logiciels selon laquelle les cas de test sont développés, et souvent automatisés, puis le logiciel est développé de manière incrémentale pour passer ces cas de test.|
|[[développement piloté par les tests d’acceptance]]|Une approche collaborative du développement selon laquelle l'équipe et les clients utilisent le langage propre au domaine du client pour comprendre ses exigences, ce qui constitue la base pour tester un composant ou un système.|
|[[Données de test]]|Données créées ou sélectionnées pour satisfaire les préconditions d'exécution et les entrées pour exécuter un ou plusieurs cas de test.|
|[[Exécution des tests]]|Processus consistant à exécuter un test sur un composant ou système en test, en produisant le(s) résultat(s) obtenu(s)s.|
|[[Exercé]]|un élément d’un programme est dit être exercé par un cas de test quand les valeurs  <br>d’entrée causent l’exécution de cet élément, tel qu’une instruction, décision ou autre élément de  <br>structure.|
|[[Implémentation des tests]]|L'activité qui prépare le testware nécessaire à l'exécution des tests sur la base de l'analyse et de la conception des tests.|
|[[Objet de test]]|Composant ou système à tester.  <br>Voir aussi : Article de test|
|[[Planification de test]]|Activité de définition ou de mise à jour d’un plan de test.|
|[[Planning d’exécution des tests]]||
|[[Procédure de test]]|Une séquence de cas de test dans l'ordre d'exécution, et  <br>toutes les actions associées qui peuvent être nécessaires pour mettre en place les préconditions initiales et toutes les  <br>activités de bouclage après l'exécution.  <br>Voir aussi : Script de test|
|[[Résultat Faux négatif]]|Un résultat de test qui ne parvient pas à identifier la présence d'un défaut qui est réellement présent dans l'objet de test.|
|[[Résultat Faux positif- Faux échec]]|Un résultat de test dans lequel un défaut est signalé alors qu'aucun défaut n'existe réellement dans l'objet de test.|
|[[Suite de tests - Suite de cas de test - Ensemble de tests]]|Ensemble de cas de test ou de procédures de test à exécuter dans un cycle de test spécifique.|
|[[Test]]|Processus consistant en toutes les activités du cycle de vie, statiques et dynamiques, concernant la planification et  <br>l’évaluation de produits logiciels et produits liés pour déterminer s’ils satisfont aux exigences et démontrer qu’ils sont conformes aux objectifs et détecter des anomalies.|
|[[Testware|Testware]]|Produits d’activités réalisés au cours du processus de test pour la planification, la conception, l'exécution, l'évaluation et l'établissement de rapports sur les tests.|
|[[Traçabilité 2]]|La mesure dans laquelle une relation peut être établie entre deux ou  <br>plusieurs produits d’activités. Voir aussi : Traçabilité horizontale, Traçabilité verticale [ISO 19506]|

  
  

**1.1 Introduction**

Le processus de test consiste en:

|   |   |   |   |
|---|---|---|---|
|N°|Étapes|Responsabilité|Produit d’activité|
|1|La planification des tests|Manager de test|plan de test (planning, etc)|
|2|Suivi et controle des tests|Manager de test|Rapport d’avancement des tests, rapport de synthèse…|
|3|==**l’analyse des tests**==|Analyste de test|Condition de test, Spécification de conception des tests (livrable), Charte de test (T. exploratoire), rapport de défaut|
|4|==**Conception de test**==|Analyste de test|Cas de test, données de test, infrastructure, outils, spécification des cas de test (livrable)|
|5|==**L’implémentation des tests**==|Analyste de test|Procédures de test (scénario), suites de test, calendrier d’exécution, spécification des procédures de test (livrable)|
|6|==**L’exécution des tests**==|Analyste de test|Statuts des tests et des scénarios, rapport de défaut, rapport d’identification des éléments utilisés pour le test (objets, outils, testware)|
|7|La clôture des tests||Rapport de synthèse, liste de points à améliorer, demandes de changements ou items de backlogs (Agile) à réintégrer, Testware finalisés|

Dont la majeure partie du travail se trouve à l’étape 3 à 6 inclus

  

Les développeurs font du test fonctionnel et non fonctionnel, principalement test boite blanche

L’Analyste de test fait principalement des tests boites noirs (fonctionnel et non fonctionnel)

Ex test boite blanche : respect du site map par une navigation des pages

## **1.2 Le test dans le cycle de vie de développement logiciel**

Traçabilité, notion importante, elle s’applique dans les outils par la possibilité d’établir un lien entre le cas de test et une exigence, cette exigence sera couverte dès que le test sera executé. Permet de réaliser le reporting auprès du client sur la progression (niveau de couverture). La traçabilité permet de reporter en terme de couverture

La traçabilité est un lien entre la base de test et un produit d’exécution

Test ware est l’ensemble de tout ce qui est produit par l’activité de test (test work product)

Test manager/leader travail main dans la main avec le chef de projet

Planification prévisionnelle, plan de test évolue tout le long du projet

Suivi et contrôle, LE suivi est la récupération des métriques, donc toutes les données pour qualifier et comprendre l’avancement de l’activité de test. Le contrôle va être les décisions et les actions prises proactivement (eg. coaching d’un tester)

Test d’acceptation est réalisé sur un environnement de préproduction par le client

différents modèles de développement

- Modèle en cascade (ancien modèle, cloisonement)
- Modèle en V
- Modèle Agile (itératif)

**1.2.1 K2 : Expliquer comment et pourquoi le moment et le niveau d’implication de l’Analyse de test varient en fonction des différents modèles de cycle de vie de développement logiciel en place**

**1.3 Analyse des tests**

L’analyse de test est une phase dont le but est de déterminer ce qu’il faut tester

L’oracle de test, est le résultat anticipé du test

Condition de test, faux amis, est un livrable, c’est des choses qui précisent ce qui est à tester

Critère de test = critère de sortie pour arrêter l’intégralité des activités de tests

1. BDD (Behaviour Driven Development), itératif, écrivent des classes de test (commencer les atelier de travail)
2. TDD (Test Driven Development),

ATDD (acceptance test-driven development)

**1.3.1 K2 : Résumer les tâches adéquates pour l’Analyste de test lors des activités d’analyse**

**1.4 Conception des tests**

Phase consistant à adapter l’effort de test au contexte, en déterminant le niveau des cas de test, puis en les rédigeant

  

**1.4.1 K2 : Expliquer pourquoi les conditions de tests doivent être comprises par les parties prenantes**

**1.4.2 K4 : Pour un scénario de projet donné, sélectionner le niveau de conception adapté pour les cas de test (haut niveau ou bas niveau) > p18**

Abstrait = haut niveau

Concret = bas niveau

INVEST (I,N,V,E,S,Testable)

Adapter l’effort au contexte , les partitions d’équivalence = plus de cas de test, les valeurs limites= moins de cas de test

- Cas de test concret/ de bas niveau
    
    |   |   |
    |---|---|
    |Avantages|Inconvénients potentiels|
    |Mode opératoire précis|Maintenance pour tout changement|
    |Données indiquées||
    |Reproductibilité|Autonomie limité des exécutants|
    |pas besoin d’expérience||
    |Accessibilité à toute personne||
    
- Cas de test Logique/ de haut niveau
    
    |   |   |
    |---|---|
    |Avantages|inconvénients potentiels|
    |Directives de haut niveau||
    |Procédure adaptable|Besoin d’expérience|
    |Données non figées||
    |Couverture plus large du fait de ces variable|Non reproductible|
    |Créable très tôt en amont|La première étape avant les cas de test concrets?|
    |Créable syr des spécifications changeantes||
    

  

  

**1.4.3 K2 : Expliquer les problèmes à aborder lors de la conception des tests**

**1.5 Implémentation des tests**

Se focaliser sur les procédures, les données, les calendriers d’exécution, les environnements et la traçabilité

passage de cas de test de haut niveau en bas niveau

  

**1.5.1 K2 : Résumer les tâches adéquates pour l’Analyste de Test lors des activités d’implémentation des tests**

**1.6 Exécution des tests**

**1.6.1 K2 : Résumer les tâches adéquates pour l’Analyste de Test lors des activités d’exécution des tests**

# Chapitre 2 : Les tâches de l'Analyste de Test dans le test basé sur les risques

#### Lexique

|Mot|Word|Définition|source|
|---|---|---|---|
|[[Analyse des risques]]|Risk Analysis|Le processus général d'identification et d'évaluation des risques.|ISTQB - Advanced 02, Testing|
|[[Atténuation des risques]]||Le processus par lequel des décisions sont prises et des mesures de protection sont mises en œuvre pour réduire ou maintenir les risques à des niveaux spécifiés.|ISTQB - Advanced 02, Testing|
|[[Évaluation des risques]]||Le processus d’examen des risques identifiés et de détermination du niveau de risque.|ISTQB - Advanced 02, Testing|
|[[Identification des risques]]||Le processus consistant à trouver, reconnaître et décrire les risques.|ISTQB - Advanced 02|
|[[Niveau de risque 2]]||La mesure qualitative ou quantitative d'un risque défini par l'impact et la probabilité.|ISTQB - Advanced 02|
|[[Réduction des risques]]||Le processus par lequel les décisions sont prises et les mesures de protection sont mises en  <br>oeuvre pour réduire ou maintenir les risques à des niveaux spécifiés.  <br>Synonyme : Contrôle des risques|ISTQB - Advanced 02|
|[[Risque]]|risk|Un facteur qui pourrait avoir des conséquences négatives à l'avenir. généralement exprimé comme un impact et une probabilité.|ISTQB - Advanced 02, ISTQB - Fondation 05, Testing|
|[[Risque produit]]|product risk|Un risque directement lié à l’objet de test. Voir aussi : Risque|ISTQB - Advanced 02, ISTQB - Fondation 05, Testing|
|[[Risque projet]]|project risk|Un risque qui a une incidence sur la réussite du projet.  <br>Voir aussi : Risque|ISTQB - Advanced 02, ISTQB - Fondation 05, Testing|
|[[Risque qualité]]|Quality Risk|Un risque Produit lié à une caractéristique de qualité. Voir aussi : Caractéristique de qualité, Risque  <br>produit.|ISTQB - Advanced 02, Testing|
|[[Robustesse]]||le degré pour lequel un composant ou système peut fonctionner correctement en présence de données  <br>  <br>d’entrée invalides ou de conditions environnementales stressantes [IEEE 610],  <br>  <br>voir aussi tolérance aux erreurs, tolérance aux défauts.|ISTQB - Advanced 02, Testing|
|[[Sécurité]]||La mesure selon laquelle une composante ou un système protège l'information et les données afin que les  <br>personnes ou d'autres composantes ou systèmes aient le degré d'accès approprié à leurs types et niveaux  <br>d'autorisation. (ISO 25010)|ISTQB - Advanced 02, Testing|
|[[Sûreté]]||La capacité qu'un système ne pourra pas, dans des conditions définies, conduire à un état dans lequel la vie  <br>humaine, la santé, la sécurité des personnes et des biens ou l'environnement est en danger. (ISO 24765)|ISTQB - Advanced 02, Testing|
|[[Test basé sur les risques]]|RBT (risk-based testing)|Tests pour lesquels la gestion, la sélection, la priorisation et l'utilisation des activités et des ressources de test sont basées sur les types de risque et les niveaux de risque correspondants.|ISTQB - Advanced 02, ISTQB - Fondation 05, Testing|

  
  

## 2.1 Introduction

Les tests managers ont la responsabilité d’établir et de gérer une stratégie de test basée sur les risques. Les analystes de test les assistent dans cette tâche via une méthode itérative structurée en 3 étapes (Identification, Analyse/Évaluation et Atténuation/Mitigation). maintenue tout au long du cycle de vie du développement.

### 2.1.1 K3 Pour une situation donnée, participer à l’identification des risques, effectuer une évaluation des risques et proposer une atténuation des risques appropriés

## 2.2 Identification des risques

  

## 2.3 Évaluation des risques

Un risque se définit par une probabilité d’apparition et un impact, donc l’effet produit sur l’objet de test et les utilisateurs.

## 2.4 Atténuation des risques

2 manières de structurés le test basé sur le risque

- En profondeur d’abord  
      
    _Les test sont exécutés du plus risqués au moins risqués_
- En largeur d’abord  
      
    _Les tests sont exécutés afin de tester chaque type de risque au moins une fois, pondéré en fonction de leur gravité, pour offrir une couverture minimale, avant de continuer l’exécution des tests restant en fonction de leur gravité._

# Chapitre 3 : Techniques de test

#### Lexique

|Mot|Word|Définition|source|
|---|---|---|---|
|[[Analyse des causes racines]]||Une technique d’analyse au but d’identifier les causes premières de défauts. En  <br>dirigeant les mesures correctives sur les causes premières, on espère que la probabilité de réapparition des défauts  <br>soit minimisée.  <br>Synonyme : Analyse causale  <br>Analyse causale: L'analyse des défauts afin de déterminer leur cause racine. [CMMI]|ISTQB - Advanced 03|
|[[Analyse des valeurs limites]]|boundary value analysis|une technique de conception de tests boîte noire dans laquelle les cas de tests sont conçus sur la base des valeurs limites.  <br>Voir aussi : Valeur limite|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[Anomalie-]]||toute condition qui dévie des attentes basées sur les exigences de spécifications, documents de  <br>conception, documents utilisateurs, standards etc, ou des perceptions ou expériences de quelqu’un. Les anomalies  <br>peuvent être trouvées pendant, mais pas uniquement, les revues, tests, analyses, compilations ou utilisation des  <br>produits logiciels ou de la documentation applicable (IEEE 1044)  <br>Voir aussi : défauts, déviation, erreur, faute, défaillance, incident, problème|ISTQB - Advanced 03|
|[[Attaque]]||Tentative dirigée et ciblée d’évaluer la qualité, en particulier la fiabilité, d’un objet de test en essayant de  <br>provoquer l’apparition de défaillances spécifiques.  <br>Voir Tests négatifs.|ISTQB - Advanced 03|
|[[Cas d’utilisation]]|Use case|Séquence de transactions dans un dialogue entre un acteur et un composant ou un système avec  <br>un résultat concret. L'acteur peut être un utilisateur ou tout ce qui peut échanger des informations avec le système.|ISTQB - Advanced 03|
|[[Cause racine]]|root cause|Une source de défaut telle que si elle est retirée, l’apparition de ce type de défaut est diminuée ou  <br>supprimée. (CMMI)|ISTQB - Advanced 03, ISTQB - Fondation 01, Testing|
|[[charte de test]]|test charter|Documentation du but ou de l'objectif d'une session de test exploratoire.|ISTQB - Advanced 03, Testing|
|[[Classification arborescente]]||Une arborescence montrant l'équivalence des partitions, triée de manière hiérarchique.  <br>Elle est utilisée pour concevoir les cas de test dans le cadre de la méthode de classification arborescente|ISTQB - Advanced 03|
|[[Défaillance]]|failure|Événement dans lequel un composant ou un système n'exécute pas une fonction requise dans les limites spécifiées|ISTQB - Advanced 03, ISTQB - Fondation 01, Testing|
|[[Défaut]]|defect|Une imperfection ou une déficience d'un produit d’activités lorsqu’il ne répond pas à ses exigences ou à ses  <br>spécifications. (IEEE 1044)  <br>Synonymes : bug, faute|ISTQB - Advanced 03, ISTQB - Fondation 01, Testing|
|[[Densité de défauts]]||Le nombre de défauts par unité de mesure d'un produit d’activités. (ISO 24765)  <br>Synonyme : densité de fautes|ISTQB - Advanced 03|
|[[Error]]||action humaine produisant un résultat incorrect. (ISO 24765)  <br>Synonyme : confusion|ISTQB - Advanced 03|
|[[Estimation des erreurs]]||Une technique de test selon laquelle les tests sont dérivés sur la base de la connaissance du testeur, des échecs passés, ou de la connaissance générale des modes de défaillance.|ISTQB - Advanced 03, Testing|
|[[Exigence]]||Une stipulation qui énonce des critères à satisfaire. (ISO 24765)|ISTQB - Advanced 03, Testing|
|[[Exigence fonctionnelle]]||une exigence qui spécifie une fonction qu’un composant ou système doit être capable de  <br>remplir. (ISO 24765)|ISTQB - Advanced 03, Testing|
|[[Exigence non-fonctionnelle]]||Exigence qui décrit comment le composant ou le système réalisera ce qu'il est censé  <br>faire. (ISO 24765)|ISTQB - Advanced 03, ISTQB - Advanced 04|
|[[Exigence Testable]]||Exigence exprimée en des termes permettant le démarrage de la conception des tests (et  <br>ultérieurement des cas de test) et l'exécution des tests pour déterminer si l'exigence a été satisfaite. (IEEE 610)|ISTQB - Advanced 03, Testing|
|[[Partition d’équivalence]]|equivalence partitioning|une portion d’un domaine d’entrée ou de sortie pour laquelle le comportement d’un composant ou système est supposé être le même, basé sur ces spécifications.  <br>Synonyme : classe d'équivalence|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[Partitionnement d'équivalence]]||Technique de test boîte-noire dans laquelle les cas de test sont conçus pour exercer  <br>des partitions d'équivalence en utilisant un élément représentatif de chaque partition. (ISO 29119)  <br>Synonyme : tests de partitions|ISTQB - Advanced 03|
|[[Postcondition]]||L'état attendu d'un élément de test et de son environnement à la fin de l'exécution d'un cas de test.|ISTQB - Advanced 03|
|[[Précondition]]||L'état requis d'un élément de test et de son environnement avant l'exécution d'un cas de test.|ISTQB - Advanced 03|
|[[Session de test]]||Laps de temps continu passé à exécuter des tests. En test exploratoire, chaque session de test se  <br>focalise sur une charte, mais les testeurs peuvent aussi explorer de nouvelles opportunités ou problèmes durant une  <br>session. Le testeur crée et exécute des cas de test à la volée et enregistre leurs évolutions.  <br>Voir aussi : Test exploratoire|ISTQB - Advanced 03|
|[[Spécification]]||Un document qui spécifie, idéalement de façon complète, précise et vérifiable, les exigences,  <br>conceptions, comportements et autres caractéristiques d’un composant ou système, et souvent, les procédures pour  <br>déterminer si ces stipulations ont été satisfaites. (IEEE 610)|ISTQB - Advanced 03, Testing|
|[[Table de décision]]|||ISTQB - Advanced 03, Testing|
|[[Taux de défaillance]]||Rapport entre le nombre de défaillances d'une catégorie donnée et une unité de mesure  <br>donnée. (ISO 24765)|ISTQB - Advanced 03|
|[[taxonomie des défauts]]||Une liste de catégories conçues pour identifier et classer les défauts.|ISTQB - Advanced 03, Testing|
|[[Technique de classification arborescente]]||une technique de conception de tests boîte noire selon laquelle les cas de  <br>tests, décrits par le biais d’une arborescence, sont conçus pour exécuter des combinaisons de domaines  <br>représentatifs d’entrées ou de sorties [Grochtmann]|ISTQB - Advanced 03, Testing|
|[[Technique de conception basée sur les défauts]]||Une procédure de dérivation et/ou sélection des cas de tests  <br>appliquée à une ou plusieurs catégories de défauts, avec un développement des tests à partir de ce qui est  <br>connu de la catégorie de défaut spécifique.  <br>Voir aussi taxonomie des défauts.|ISTQB - Advanced 03, Testing|
|[[Technique de test basée sur l'expérience]]|experience-based test technique|Procédure pour obtenir et/ou sélectionner des cas de test basée sur l'expérience du testeur, sa connaissance et son intuition.  <br>Synonyme : technique basée sur l'expérience|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[technique de test basée sur les défauts]]||Une technique de test selon laquelle les cas de test sont développés à partir de ce qui est connu sur un type de défaut spécifique.|ISTQB - Advanced 03, Testing|
|[[Technique de test boîte-noire]]|black-box test technique|procédure documentée pour élaborer et sélectionner des cas de tests basés sur une analyse des spécifications, soit fonctionnelles soit non-fonctionnelles, d’un composant ou système, sans faire référence à ses structures internes.  <br>Synonymes : Technique boîte noire, technique basée sur les spécifications, technique de test basée sur les spécifications|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[Test Ad-hoc]]||test effectué de manière informelle ; sans préparation formelle des tests, pas d’utilisation de technique  <br>de conception de tests reconnue, il n’y a pas d’attente spécifique de résultats et le hasard guide les activités  <br>d’exécution de tests.|ISTQB - Advanced 03|
|[[Test basé sur des sessions]]||approche du test dans laquelle des activités de test sont planifiées comme les  <br>sessions ininterrompues de conception de tests et d'exécution. Elle est souvent utilisée en conjonction avec le test  <br>exploratoire.|ISTQB - Advanced 03|
|[[Test basé sur l'attaque]]||une technique de test basée sur l'expérience qui utilise l'attaque de logiciels pour provoquer  <br>des défaillances, en particulier les failles de sécurité|ISTQB - Advanced 03|
|[[Test basé sur une checklist]]|checklist-based testing|Une technique de conception de tests basée sur l'expérience selon laquelle le testeur expérimenté utilise une liste de haut niveau d'éléments à noter, à vérifier, ou à se rappeler, ou un ensemble de règles ou de critères en fonction desquels un produit doit être vérifié.|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[Test de cas d’utilisation]]|use case testing|Technique de test boîte noire selon laquelle les cas de tests sont conçus pour exécuter des scénarios de cas d’utilisation.  <br>Synonymes : tests de scénarios, tests de scénarios utilisateurs|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[Test des transitions d’état]]|state transition testing|Une technique de test de boîte-noire utilisant un diagramme états-transitions ou une table d'état pour dériver des cas de test afin d'évaluer si l'élément de test exécute avec succès des transitions valides et bloque les transitions invalides.  <br>Voir aussi : Test N-switch  <br>Synonyme : Test de machines à états finis|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[Test méthodique]]||test basé sur un ensemble de tests standard, par exemple, un standard qualité, ou un ensemble de  <br>cas de tests généralisés|ISTQB - Advanced 03|
|[[test par paires]]||Une technique de test boîte noire selon laquelle les cas de test sont conçus pour exercer des paires de paramètres-valeurs.|ISTQB - Advanced 03|
|[[Test par tables de décisions]]|decision table testing|une technique de conception des tests boîte noire dans laquelle les cas de tests sont conçus pour exécuter les combinaisons d’entrées et/ou de stimuli (causes) présentes dans une table de décision.  <br>Voir aussi : Table de décision|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[tests basés sur l'expérience]]||Test basé sur l'expérience, les connaissances et l'intuition du testeur.|ISTQB - Advanced 03, Testing|
|[[Tests exploratoires]]|exploratory testing|Une approche des tests par laquelle les testeurs conçoivent et exécutent dynamiquement des tests en fonction de leurs connaissances, de l'exploration de l'élément testé et des résultats des tests précédents|ISTQB - Advanced 03, ISTQB - Fondation 04, Testing|
|[[User Story]]|Userstory|Changement (fonctionnalité) centré l'utilisateur final et son expérience. Une exigence d'utilisateur ou métier de haut niveau communément utilisée dans le développement de  <br>logiciels Agile, qui consiste généralement en une phrase dans le langage courant ou le langage métier capturant la  <br>fonctionnalité dont un utilisateur a besoin et la raison de ce besoin, les critères non fonctionnels, ainsi que les  <br>critères d'acceptation. Voir aussi : Développement de logiciels Agile, Exigence|ISTQB - Advanced 03, Testing|
|[[Valeur limite 2]]||Une valeur minimale ou maximale d'une partition d'équivalence ordonnée.|ISTQB - Advanced 03|
|[[Validation]]|validation|Confirmation par l’examen et la fourniture de preuves objectives que les exigences, pour un usage ou  <br>une application voulue, ont été satisfaites. [ISO 9000]|ISTQB - Advanced 03, ISTQB - Advanced 04, ISTQB - Fondation 01, Testing|
|[[Vérification 2]]||Confirmation par l’examen et la fourniture de preuves objectives que des exigences spécifiées ont été  <br>satisfaites. [ISO 9000]|ISTQB - Advanced 03|

  
  

## 3.1 Introduction

Les questions qui seront rencontrée à l’examen:

- Cas d’utilisation (cas nominale, exception, erreurs)

## 3.2 Technique de test boite noir

- Exercices
    
    ![[Untitled 6 1.png|Untitled 6 1.png]]
    
    ![[Untitled 1 2 1.png|Untitled 1 2 1.png]]
    
    ![[Untitled 2 2 1.png|Untitled 2 2 1.png]]
    
- **3.2.1 K4 Analyser un ou des éléments d’une spécification donnée et concevoir des cas de test en appliquant** **les partitions d’équivalence**
    
    ![[Untitled 3 2 1.png|Untitled 3 2 1.png]]
    
- **3.2.2 K4 Analyser un ou des éléments d’une spécification donnée et concevoir des cas de test en appliquant l’****analyse des valeurs limites**
    
    Recherche à valider la limite, l’implémentation du comportement par le développeur, non les différentes partitions. Cherche à tester les incréments qui ont un comportement différent de la limite, donc ceux qui produisent un changement de comportement.
    
- **3.2.3 K4 Analyser un ou des éléments d’une spécification donnée et concevoir des cas de test en  
    appliquant le  
    ****test des tables de décision**
    
    ![[Untitled 4 2 1.png|Untitled 4 2 1.png]]
    
- **3.2.4 K4 Analyser un ou des éléments d’une spécification donnée et concevoir des cas de test en  
    appliquant le  
    ****test des transitions d’état**
    
    ![[Untitled 5 2.png|Untitled 5 2.png]]
    
    - 100% de couvereture 0-switch (/ 1-1 switch) : lorsque toutes les séquences valides de longueur 1 ont été parcourrues
    - 100% de couvereture 1-swittch (/ 2-1 switch)) : lorsque toutes les séquences valides de longueur 2 ont été parcourrues
    - 100% de couvereture n-switch : lorsque toutes les séquences valides de longueur n+1 ont été parcourrues
    - 100% de couvereture Aller-retour, applicable uniquement quand les séquences de transitions forment des boucles
    
      
    
- **3.2.5 K2 Expliquer comment les** **diagrammes de classification arborescente** **soutiennent les  
    techniques de test**
    
      
    
- **3.2.6 K4 Analyser un ou des éléments d’une spécification donnée et concevoir des cas de test en  
    appliquant le  
    ****test par paires**
    
    Si nous avons un ensemble de données de 4 conditions, dont, la première à 2 variables, la deuxième 3 varialbe, la troisième 4 variable et la quatrième 5 variable.
    
    Dans le cas de test par paire:
    
    - 1-wise (Singleton) : test une condition ayant le plus de condition, donc 5 TCs dans notre exemple
    - 2-wise (pairwise) : test 2 conditions ayant le plus de valeurs, donc 20 TCs dans notre exemple
    - 3-wise (triplé) : test 3 conditions ayant le plus de valeurs, donc 60 TCs dans notre exemple
    - 4-wise (quadruplé) : Test 4 conditions ayant le plus de valeurs, donc 120 Tcs dans notre exemple
    
    La combinatoire globale est la table de décision étendue, donc l’ensemble des combinaisons possilbes, donc le produit de l’ensemlbe de combinaison, ce qui veut dire 120 TCs dans notre exemple.
    
- **3.2.7 K4 Analyser un ou des éléments d’une spécification donnée et concevoir des cas de test en  
    appliquant le  
    ****test des cas d’utilisation**
    
    **_Orsys (p 73- ), Manuel ()_**
    
    _Les cas d’utilisation reprennent le comportement de base (happy path), ainsi que les comportements alternatifs et la gestion des erreurs. Ils permettent d’en dériver les cas d’utilisation._
    
- **3.2.8 K4 Analyser un système, ou sa spécification des exigences, afin de déterminer les types de  
    défauts les plus probables et sélectionner la ou les technique(s) de test boîte noire appropriée(s)  
    **
    
    Principes de tests:
    
    1. Les tests montrent la présence des défauts  
          
        _non, l’absence de défauts_
    2. Les tests exhaustifs sont impossibles.
    3. Tester tôt
    4. Regroupement des défauts
    5. Paradoxe du pesticide
    6. Les tests dépendent du contexte
    7. L’illusion de l’absence d’erreurs
    
      
    
    Combiner les techniques permet une couverture plus complète, en fonction de l’effort de test prévu (temps, compétences)
    
    |   |   |
    |---|---|
    |Technique|Type de défaut potentiel|
    |Partitions d’équivalence|Mauvais traitements des valeurs des données|
    |Valeurs limites|déviation ou omission des limites, détection de limites additionnelles, défauts non fonctionnels|
    |Tables de décision||
    |Transitions d’état||
    |Classification arborescente||
    |Tests par paires||
    |Cas d’utilisation||
    
      
    

## 3.3 Technique de test basées sur l’expérience

Il y a 3 techniques basées sur l’expérience:

- L’estimation d’erreur  
    Test basé sur une t  
    _axonomies de défauts, liste de faiblessses courantes du système ou d’attaques réussies, méthode de “chasses aux bogues”_
    - Peut être standardisée (cf. Technique de test basées sur les défauts)
- Test basé sur une checklist  
      
    _test basé sur des listes de contrôles ou d’autres sources_
- le test exploratoire  
      
    _Test basé sur une charte, avec des sessions de test, débriefing_

  

## 3.4 Appliquer les techniques de tests les plus appropriées

# Chapitre 4 : Test des caractéristiques qualité du logiciel

- Lexique
    
    #### Lexique
    
    |Mot|Word|Définition|source|
    |---|---|---|---|
    |[[Accessibility]]||La mesure de la façon dont un composant ou un système peut être utilisé par des personnes couvrant  <br>le plus grand nombre de caractéristiques et de capacités pour atteindre un but précis dans un contexte d'utilisation  <br>précis. (ISO 25010)|ISTQB - Advanced 04|
    |[[Adéquation fonctionnelle]]||Degré auquel les fonctions facilitent l'accomplissement des tâches et des objectifs  <br>spécifiés. (ISO 25000)|ISTQB - Advanced 04|
    |[[Aptitude à l’usage]]||la capacité d’un produit système à fournir un ensemble approprié de fonctions pour une tâche et  <br>des objectifs utilisateurs spécifiés. [ISO 9126]|ISTQB - Advanced 04|
    |[[Complétude fonctionnelle]]||Degré auquel l'ensemble des fonctions couvre toutes les tâches spécifiées et les objectifs  <br>de l'utilisateur. (ISO 25000)|ISTQB - Advanced 04|
    |[[Esthétique de l’interface utilisateur]]||Degré auquel une interface utilisateur permet une interaction agréable et  <br>satisfaisante pour l'utilisateur. (ISO 25010)|ISTQB - Advanced 04|
    |[[Exactitude]]||Mesure dans laquelle un produit ou un système fournit les bons résultats avec le degré de précision  <br>nécessaire. [ISO 25000]|ISTQB - Advanced 04|
    |[[Exigence non-fonctionnelle]]||Exigence qui décrit comment le composant ou le système réalisera ce qu'il est censé  <br>faire. (ISO 24765)|ISTQB - Advanced 03, ISTQB - Advanced 04|
    |[[Facilité d’adaptation]]||degré auquel un produit ou un système peut être adapté de manière efficace et efficiente à des environnements opérationnels ou d'utilisation différents ou évolutifs (matériel, logiciel, etc.). (ISO 25010)|ISTQB - Advanced 04|
    |[[Facilité d’apprentissage]]||Degré auquel un produit ou un système peut être utilisé par des utilisateurs spécifiques pour atteindre des objectifs spécifiques d'apprentissage de l'utilisation du produit ou du système avec efficacité, efficience, absence de risque et satisfaction dans un contexte d'utilisation spécifique. (ISO 25010)|ISTQB - Advanced 04|
    |[[Facilité d’installation-]]||degré d'efficacité et d'efficience avec lequel un produit ou un système peut être installé et/ou désinstallé avec succès dans un environnement spécifié. (ISO 25010)|ISTQB - Advanced 04|
    |[[Facilité de remplacement]]||degré auquel un produit peut remplacer un autre produit logiciel spécifié pour le même usage dans le même environnement.(ISO 25010)|ISTQB - Advanced 04|
    |[[Interopérabilité]]||La mesure selon laquelle deux ou plusieurs composants ou systèmes peuvent échanger de  <br>l'information et utiliser l'information qui a été échangée. [ISO 25010]|ISTQB - Advanced 04|
    |[[Opérabilité]]||Degré auquel un produit ou un système possède des attributs qui le rendent  <br>facile à utiliser et à contrôler.(ISO 25010). Voir aussi : Facilité d’opération|ISTQB - Advanced 04|
    |[[Portabilité]]||facilité avec laquelle un produit logiciel peut être transféré d’un environnement matériel ou logiciel vers un  <br>autre. (ISO 25010)|ISTQB - Advanced 04|
    |[[Processus de validation]]||Le processus de validation est un processus qui permet de déterminer si les exigences et le système ou le produit  <br>logiciel finaux satisfont un emploi spécifique visé. (ISO 12207)|ISTQB - Advanced 04|
    |[[processus de vérification]]||Le processus de vérification est un processus qui permet de déterminer si les produits logiciels d’une activité  <br>satisfont les exigences ou les conditions que les activités précédentes leur imposent. (ISO 12207)|ISTQB - Advanced 04|
    |[[Protection contre les erreurs de l’utilisateur]]||Degré auquel un système protège les utilisateurs contre les erreurs.  <br>(ISO 25010)|ISTQB - Advanced 04|
    |[[Qualité]]|quality|degré par lequel un composant, système ou processus atteint des exigences spécifiées et/ou des besoins  <br>ou attentes des clients ou utilisateurs (ISO 24765)|ISTQB - Advanced 04, ISTQB - Fondation 01, Testing|
    |[[Qualité des données]]||un attribut qui indique l'exactitude d'une donnée par rapport à, par exemple, des attentes  <br>métier, des exigences d'intégrité ou de consistance des données.|ISTQB - Advanced 04|
    |[[Qualité logicielle]]||La totalité des fonctionnalités et caractéristiques d’un produit logiciel qui influent sur sa capacité  <br>à satisfaire des besoins déclarés ou implicites. (ISO 25010)|ISTQB - Advanced 04|
    |[[Reconnaissance de la pertinence]]||Degré auquel les utilisateurs peuvent reconnaître si un produit ou  <br>un système est approprié à leurs besoins. (ISO 25010), voir aussi : Identification de la pertinence|ISTQB - Advanced 04|
    |[[test dos à dos]]||test où deux ou plus variantes d’un composant ou d’un système sont exécutés avec les mêmes  <br>entrées, les sorties étant comparées, et analysées en cas de divergences. [IEEE 610]|ISTQB - Advanced 04|
    |[[Test fonctionnel]]|functional testing|Test réalisé pour évaluer la conformité d'un composant ou d'un système aux exigences. Voir aussi : test boîte-noire  <br>fonctionnelles. (ISO 24765)|ISTQB - Advanced 04, ISTQB - Fondation 02, Testing|
    |[[Test non-fonctionnel]]|non-functional testing|Test effectué pour évaluer la conformité d'un composant ou d'un système avec les exigences non fonctionnelles.|ISTQB - Advanced 04, ISTQB - Fondation 02, Testing|
    |[[Utilisabilité]]||La mesure selon laquelle un composant ou un système peut être utilisé par des utilisateurs spécifiques  <br>pour atteindre des objectifs spécifiques dans un contexte d'utilisation spécifique. (ISO 25010)|ISTQB - Advanced 04|
    |[[Validation]]|validation|Confirmation par l’examen et la fourniture de preuves objectives que les exigences, pour un usage ou  <br>une application voulue, ont été satisfaites. [ISO 9000]|ISTQB - Advanced 03, ISTQB - Advanced 04, ISTQB - Fondation 01, Testing|
    |[[Vérification]]|verification|Confirmation par l’examen et la fourniture de preuves objectives que des exigences spécifiées ont été satisfaites.|ISTQB - Advanced 04, ISTQB - Fondation 01, Testing|
    
      
      
    

## 4.1 Introduction

![[Untitled 6 2.png|Untitled 6 2.png]]

L’analyste de test intervient sur

1. La fonctionnalité
    1. complétude
    2. adéquation
    3. exactitude
2. l’utilisabilité
    1. Utilisabilité
    2. expérience
    3. accessibilité
3. la portabilité (environnement matériel)
    1. adaptabilité
    2. installabilité
    3. remplaçabilité
4. la compatibilité (environnement logiciel)
    1. interopérabilité

Séquence lors d’une livraison

1. Complétude - _Est-ce que ce qui m’a été livré répond à l’entièreté des exigences? Y a-t-il des fonctions manquantes_ ?
2. Adéquation - _Est-ce que ce qui m’a été livré répond-t-il au besoin exprimé_ ?
3. Exactitude - _Est-ce que ce qui m’a été livré fournit un résultat correct_?

## 4.2 Caractéristiques de qualité pour les tests de domaine métier

### 4.2.1 Test d’exactitude fonctionnelle

**Orsys (), Manuel ()**.

### 4.2.2 Test d’adéquation fonctionnelle

**Orsys (), Manuel ()**.

### 4.2.3 Test de complétude fonctionnelle

**Orsys (), Manuel ()**.

  

### 4.2.4 Test d’interopérabilité

**Orsys (), Manuel ()**.

Test vérifiant l’interopérabilité entre l’objet du test et les autres logiciels/systèmes, donc vérifier l’échange d’informations

### 4.2.5 Test d’utilisabilité

**Orsys (), Manuel ()**.

Le logiciel est-il facilement utilisable ? Caractérisée par:

- Utilisabilité - Facilité d’utilisation, basé sur des exigences
- Expérience Utilisateur (UX) - Expérience vécue par l’utilisateur, qui est recueillie, analysée et vecteur d’évolution
- Accessibilité - Sous famille de l’utilisabilité orientée pour les déficiences/handicapes que l’utilisateur peut présenter (mal voyant, Daltonien)

Ces caractéristiques peuvent être toutes les trois évaluées par les approches suivantes :

- Test d’utilisabilité  
    Qui mesure l’efficacité, l’efficience et la satisfaction  
    
- Revue d’utilisabilité
- Enquêtes et questionnaires d’utilisabilité  
      
    _Recueil l’information via différentes typologies_.

  

### 4.2.6 Test de portabilité

**Orsys (p. 117-), Manuel ()**.

Test touche l’installabilité, l’adaptabilité et la remplaçabilité d’un système.

Ces caractéristiques sont testables par les méthodes suivantes:

- Test de facilité d’installation
- Test d’adaptabilité
- Test de facilité de remplacement

# Chapitre 5 : Revues

## 5.1 Introduction

Les revues sont des test statiques, donc qui n’implique aucune exécution. On trouve donc des défauts dans la base de test, et non des défaillances. Deux grandes faimilles, les revues formelles et les revues informelles. Les revues informelle est une revue non-préparé et qui peut être une discussion entre deux professionnels

Dans le cas d’une revue formelle

1. Planification
2. Lancement
3. Préparation individuelle
4. Communication et analyse des problèmes
5. Correction des défauts détectés et production de rapports

## 5.2 Utiliser des checklists dans les revues

Les principes des checklists:

- Pense-bête -
- Neutralité
- Garde fou

### 5.2.1 Revues des exigences

  

### 5.2.2 Revues de User Stories

### 5.2.3 Adapter les checklissts

# Chapitre 6 : Outils de test et automatisation

## 6.1 Introduction

6 familles d’outils

1. Outils pour la gestion des tests et du testware
2. Outils pour les tests statiques
3. Outils pour la conception et l’implémentation des tests
4. Outils pour l’exécution et les logs des tests
5. Outils pour la mesure de la performance et l’analyse dynamique
6. Outils pour des besoins de test spécialisés

## 6.2 Automatisation dirigée par les mots clés

  

## 6.3 Types d’outils de test

### 6.3.1 Outils de conception des tests

Outils qui génère des tests

MBT (Model based testing)

  

### 6.3.2 Outils de préparation des données de tests

### 6.3.3 Outils d’exécution automatisée des tests

backoffice.france@gasq.org