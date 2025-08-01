---
tags:
  - "#Wiki/Professional/TestAnalyst/ISTQB"
Type: "[[Training]]"
aliases:
  - CT-TAE
  - ISTQB - Niveau Avancé - Ingénieur de Test Automatisé
Link: "[[ISTQB_TestAutomationIngeneerAvance_CT-TAE_V1.0-FR-2016.pdf]]"
---

>[!video] [🎬 Playlist ISTQB training ](https://www.youtube.com/watch?v=eVbkxT4I54k&list=PLj5VKaW115t34PmSb5e1C2_fANeqGvDDN)
## 0. Introduction à ce Syllabus
**Durée** : *N/A*
**Périmètre**: *Document à destination des ingénieur en automatisation de test (TAE) et se concentre sur les concepts, méthodes, outils et processus pour des tests automatisés fonctionnels.*
**Glossaire :**
```dataview
TABLE WITHOUT ID file.link AS "Words", aliases AS "Aliases", frDescr AS "Description"
FROM #Wiki/Glossary 
WHERE contains(Chapters, "TC-TAE-0") AND !contains(file.name, "Template")
SORT file.name ASC
```

**Examination** :
Prerequisite : *Foundation level certified*
Number of questions : *40 ( 75 marks)*
Duration : *90 min*
Passing Score : *65% (49 marks)*

## 1. Introduction et objectifs pour l'automation de test
**Durée** : *30 mins*
**Objectifs** : 
- ALTA-E-1.1.1 (K2) Expliquer les objectifs, avantages et limites de l'automatisation de test
- ALTA-E-1.2.1 (K2) Identifier les facteurs techniques de succès d'un projet d'automatisation de test
**Glossaire** : 
```dataview
TABLE WITHOUT ID file.link AS "Words", aliases AS "Aliases", frDescr AS "Description"
FROM #Wiki/Glossary 
WHERE contains(Chapters, "TC-TAE-1") AND !contains(file.name, "Template")
SORT file.name ASC
```

**Anki Link** : 
### 1.1 But de l'automatisation de test
 > [!video] [Vidéo explicative - eng](https://youtu.be/ZB0xxLWlQN4?si=I0pObr61rj7TdQ0J)

> [!question] Quelle est la différence entre le test manuel et automatisé ?
> L'automatisation de test diffère du test manuel dans son écriture et son exécution, dans le sens où à la place d'écrire des [[Test case|cas de test]], vous écrivez des [[Wiki/Glossary/Test script|Scripts de test]], et au lieu d'éxécuter vous même les [[Test case|cas de test]], vous utilisez un [[Test Tool|Outil de test]].

> [!question] Quelle est le but de l'automatisation ?
L'[[Test Automation|Automatisation de test]] aide à exécuter de nombreux tests de manière répétée et cohérente sur différentes version du [[SUT]] et/ou environnements. Mais l'automatisation est plus qu'un mécanisme d'exécution sans intervention humaine, il implique aussi la conception du [[Testware]], ce qui inclus :
  > * Les logiciels utilisés
  > * La documentation
  > * Les cas de test
  > * Les environments de test
  > * Les sets de données
  
  > [!question] Quelle est l'utilité du [[Testware| testware]] pour l' [[Test Automation|automatisation]]?
Le [[Testware]] est nécessaire pour les [[Test activity|activités de test]], telle que :
> - L'implémentation des cas de test automatisés
> - Le suivi et le contrôle de l'éxécution des test automatisés
> - L'interprétation, le reporting et l'enregistrement des résultats des tests

- #### Tâches de l'automation des tests
	1. Utilisation d'outils logiciels spéciaux pour contrôler et configurer les conditions préalables de test
	2. Exécuter des tests
	3. Comparer les résultats réels aux résultats prévus

> [!info] Recommandations
>  *Séparer le [[Test Tool]] (logiciel utilisé), du [[SUT]] (Système sous test), pour minimiser les interferences, sauf exceptions (ex. systèmes embarqués ou logiciel de test embarqué dans le [[SUT]])*

- #### Approches d'automatisation de test pour tester un SUT
	1. Test par les interfaces publiques des classes, modules ou librairies du SUT (ex. [[Test d'API]])
	2. Test par l'interface utilisateur du SUT
		1. [[Test d'IHM]]
		2. [[Test de CLI]]
	3. Test à travers le protocole réseau
- #### Objectif de l'automatisation des tests
	1. Améliorer l’efficacité du test
	2. Fournir une couverture plus large
	3. Réduire le cout total du test
	4. Réaliser des tests non réalisables par un humain
	5. Réduire la période de test 
	6. Augmenter la fréquence/réduire le temps requis pour les cycles de test
- #### Avantage de l'automatisation des tests
	1. Plus de tests exécutés par Build
	2. Les tests ne pouvant pas être réalisés manuellement sont possibles (tests en temps réel, à distance, en parallèle)
	3. Les tests peuvent être plus complexes
	4. L'exécution de test est plus rapide
	5. Les tests sont moins sujets à des erreurs des opérateurs
	6. Utilisation plus économe et efficace des ressources de test 
	7. Feedback plus rapide sur la qualité du logiciel
	8. Fiabilité des systèmes améliorées (ex. cohérence, répétabilité, etc.)
	9. Amélioration de la cohérence des tests
- #### Désavantages de l'automatisation des tests
	1. Implique des coûts additionnels
	2. Coût initial pour la mise à place du [[TAS]]
	3. Requière des technologies additionnelles
	4. L'équipe requière des compétences en développement et en automatisation
	5. Nécessite une maintenance continue du [[TAS]]
	6. Peut détourner des objectifs de test
	   *ex. Se concentrer sur l'automatisation des cas de test aux dépends de l'exécution des tests*
	7. Les tests peuvent devenir plus complexes
	8. Des erreurs additionnelles peuvent être introduites par l'automatisation.
- #### Limite de l'automatisation des tests
	1. Tous les tests manuels ne peuvent pas être automatisés
	2. L’automatisation peut uniquement vérifier des résultats interprétables par une machine
	3. L’automatisation peut uniquement vérifier des résultats obtenus qui peuvent être vérifiés par un oracle de test automatisé
	4. Ne remplace pas les tests exploratoires
### 1.2 Facteurs de succès dans l'automatisation de test 
> [!video] *[🎬 Vidéo explicative - eng](https://youtu.be/7Go-ZuHLbdQ?si=0DuVQ-GJsGPNurlZ)*

- #### Facteurs jouant un rôle dans le succès d'un projet d'automatisation de test
	- Présence d'une [[TAA| TAA (Architecture d'Automatisation de Test)]]
		  *La conception de la [[TAA]] doit être aligné sur l'architecture du produit logiciel, avec des spécifications claires sur les exigences fonctionnelles et non-fonctionnelles à supporter. Et doit être réalisée dans un but de maintenabilité, de performance et apprenabilité. à ces fins, impliqués des ingénieurs logiciels, comprenant l'achritecture du [[SUT]] est recommandée.*
	- Analyse de la [[Testability|Testabilité]] du [[SUT]]
		  *[[SUT]] doit être conçus pour être testable via des scripts de test automatisés, et ces scripts doivent être facilement implémentable. Pour ce faire, une preuve réussie de concept doit être réablisable. Pour se faire, le [[TAE]] doit identifier les modules et composant du [[SUT]] facilement testable automatiquement, et commencer par là.*
	- [[TASt|TASt (Stratégie d'Automatisation de Test)]]
		  *La [[TASt]] doit être pratique et cohérente en prenant en compte la maintenabilité et la cohérence du [[SUT]]. Elle doit prendre en compte les coûts, les bénéfices et les risques qui s'appliquent aux différentes parties du code, et s'adapter aux évolution du système, une ancienne et nouvelle partie du [[SUT]] pouvant ne pas être testable de la même manière. En conséquence, il doit être considéré de tester autant [[GUI]] que l'[[API]] pour vérifier la cohérence des résultats.*
	- [[TAF|TAF (Framework d'Automatisation de Test)]]
		  *Le [[TAF]] sélectionné doit être facile d'utilisation, bien documenté et maintenable, supportant une approche cohérence de l'automatisation des tests.
		  Pour ce faire, les éléments suivants doivent être mis en oeuvre:*
		* Implémentation de dispositifs de rapport
			  *Implémenter un dispositifs générant des rapports sur la qualité du [[SUT]] (Passé, échec, erreur, non-exécuté, etc.), afin de fournir des informations sur la capacité fonctionnelle du [[SUT]] et , aux différents parties prenantes (testeur, test manager, développeurs, gestionnaires de projet, etc.)*
		* Permettre un dépannage facile
			  *Le [[TAF]] doit fournir des outils facilitant le dépannage des tests défaillants, en plus d'outils d'exécution et de journalisation des tests., afin d'identifier facilement les raisons de l'échec (défaillance dans le [[SUT]], ou le [[TAS]], ou des problèmes propres aux tests ou à l'environnement de tests).*
		* Mise en place d'un l'environnement de test contrôlé, cohérent avec les exigences de qualité
			  *Mettre en place un environnement contrôlé, dédié au test, répliquant les conditions de l'environnement de production, et qui soit cohérent avec les exigences business, de la [[TASt]], etc. Sans quoi les résultats de l'exécution des tests peuvent être erronés.*
		* Documenter les cas de test automatisés
			  *Clarifier et documenter les objectifs de l'automatisation des tests (quelles parties, quel degré et quels attributs (Fonctionnel et non-fonctionnel) doivent être testés)*
		* Tracer le test automatisé
			  *Le [[TAF]] doit inclure une fonctionnalité de traçage des tests, afin de permettre tracer les étapes individuelles des cas de tests.*
		* Faciliter la maintenance
			  *Les cas de test automatisé doivent être conçus pour être aisément maintenable, en étant facilement analysable, modifiable et extensibles. De plus, le [[testware]] automatisé doit être hautement réutilisable. Ceci, afin que les efforts de tests nécessaire dédié à la maintenant soit réduit, et restent proportionnel aux changements apportés au [[SUT]].*
		* Maintenir à jour les tests automatisés
			  *Maintenez à jour les cas et suites de tests existantes, en cohérence avec les modification ou l'introduction de nouvelles exigences.*
		* Planification des déploiements
			  *Assurez-vous que les scripts de test sont facilement déployable, modifiable et redéployable.*
		* Retrait des tests au besoin
			  *Assurez-vous que les scripts de tests sont facilement retirable si devenu inutile/ dispensable.*
		* Suivre et restaurer le [[SUT]]
			  *Afin de garantir une exécution continu des cas ou des ensembles de cas de test, le [[TAF]] doit être capable de suivre et restaurer le [[SUT]] en cas d'erreur fatale (ex. plantage), en passant le cas de test actuel et en reprenant l'exécution au cas de test suivant.*

> [!video] [🎬 Exemple de questions - Chap 1 - eng](https://youtu.be/J-MxD8d-upU?si=326S-Z29BNVkHTDA)
## 2. Préparation pour l'automatisation de test
> [!video] [Vidéo explicative (eng)]()

 > Si hypothétiquement 

**Durée** : *165 mins*
**Objectifs** : 
* ALTA-E-2.1.1 (K4) Analyser un [[SUT]] pour déterminer la solution d’automatisation appropriée
* ALTA-E-2.2.1 (K4) Analyser les outils d'automatisation de test pour un projet donné et signalez les constatations et recommandations techniques
* ALTA-E-2.3.1 (K2) Comprendre les méthodes de “conception pour la testabilité” et de “conception pour l’automatisation de test” applicables au [[SUT]]
**Glossaire** :
```dataview
TABLE WITHOUT ID file.link AS "Words", aliases AS "Aliases", frDescr AS "Description"
FROM #Wiki/Glossary 
WHERE contains(Chapters, "TC-TAE-2") AND !contains(file.name, "Template")
SORT file.name ASC
```

### 2.1 Facteur du SUT influençant l'automatisation de test

- **Interface du SUT**
- **Logiciel tiers**
- **Selection des tests à automatiser**
- **Niveau d'intrusion**
- **Différentes architectures de SUT**
- **Taille et complexité du SUT**



## 3. L'architecture d'automation de test générique
**Durée** : *270 mins* 
**Objectifs** : 
## 4. Risques et contingences liés au déploiement
**Durée** : *150 mins*
**Objectifs** : 
## 5. Métriques et reporting sur l'automation des test
**Durée**: *165 mins*
**Objectifs** : 
## 6. Transition du test manuel vers un environnement automatisé
**Durée** : *120 mins*
**Objectifs** : 
## 7. Vérification de la TAS
**Durée** : *120 mins*
**Objectifs** : 
## 8. Amélioration continue
**Durée** : *150 mins*
**Objectifs** : 
