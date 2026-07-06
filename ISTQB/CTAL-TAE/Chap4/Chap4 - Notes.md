## Chapitre 4 : Implémentation de l'Automatisation des tests (150 minutes - K4)

### Objectifs

En apprendre plus sur :

- La planification et le déploiement d'un projet pilote d'Automatisation des tests
- Les risques de déploiement et les stratégies d'atténuation
- Les facteurs qui améliorent la maintenabilité du code d'Automatisation des tests

### **Mots-clés**

| **Mot** | **Définition** |
|---------|----------------|
| **risque** | A factor that could result in future negative consequences. |
| **contexte de test** | Environnement dans lequel un test est exécuté, incluant les préconditions, les données de test et les configurations nécessaires. |

### 4.1 Développement de l'Automatisation des tests

#### **TAE-4.1.1 (K3)** : Appliquer des lignes directrices qui soutiennent des activités efficaces de pilotage et de déploiement de l'Automatisation des tests

**Définition du périmètre du projet pilote**

Un projet pilote d'Automatisation des tests ne prend pas beaucoup de temps à mener, mais le résultat peut avoir un impact significatif sur la direction que prend le projet. Il est crucial de définir clairement le périmètre de validation.

**Évaluation des éléments clés pour les lignes directrices :**

| **Élément** | **Description** | **Impact sur la stratégie** |
|-------------|-----------------|----------------------------|
| **Langage(s) de programmation** | Choix des technologies de développement | Alignement avec l'équipe technique et le SUT |
| **Outils commerciaux clé en main/Open-source** | Sélection des outils d'automatisation | Budget, support, flexibilité d'implémentation |
| **Niveaux de test à couvrir** | Unitaires, intégration, système, acceptation | Architecture en couches du TAF |
| **Cas de test sélectionnés** | Priorisation des tests à automatiser | ROI et validation de l'approche |
| **Approche de développement** | TDD, DDT, KDT, BDD, etc. | Maintenabilité et collaboration équipe |

**Définition de l'approche initiale :**

Sur la base des points énumérés ci-dessus, les TAE peuvent définir une approche initiale à suivre. Plusieurs prototypes initiaux différents peuvent être créés pour montrer les avantages et inconvénients des différentes approches. À partir de là, les TAE peuvent décider du chemin à suivre.

**Planification et suivi du projet pilote :**

- **Définition d'un calendrier** : Élément important pour respecter les délais et garantir le succès du projet pilote
- **Vérification périodique** : Recommandation courante de vérifier périodiquement l'avancement du projet pilote afin d'identifier les risques éventuels et de les atténuer

**Intégration CI/CD pendant le pilote :**

Il est recommandé d'essayer d'intégrer la solution et le code déjà implémenté dans le CI/CD. Cela peut mettre en évidence des problèmes précoces, soit dans le SUT, soit dans la TAS, soit dans l'intégration globale des différents outils au sein de l'organisation.

Au fur et à mesure que le nombre de cas de test augmente, les TAE peuvent penser à modifier la configuration initiale du CI/CD pour exécuter les tests de différentes manières et à différents temps de réflexion.

**Évaluation des aspects non-techniques :**

Au cours du projet pilote, il est nécessaire d'évaluer d'autres aspects non-techniques :

| **Aspect** | **Description** | **Impact sur le projet** |
|------------|-----------------|--------------------------|
| **Connaissances et expérience** | Niveau technique des membres de l'équipe | Formation et support requis |
| **Structure de l'équipe** | Organisation et rôles | Collaboration et communication |
| **Règles de licence et d'organisation** | Contraintes légales et politiques | Conformité et gouvernance |
| **Plan de test** | Type de plan de test et niveaux de test ciblés à couvrir pendant l'automatisation des cas de test | Couverture et stratégie d'automatisation |

**Évaluation finale :**

Une fois le projet pilote terminé, l'effort doit être évalué par les TAE et les Test Managers afin d'évaluer la réussite ou la défaillance et de prendre une décision appropriée.

### 4.2 Risques associés au développement de l'Automatisation des tests

#### **TAE-4.2.1 (K4)** : Analyser les risques liés au déploiement et planifier des stratégies d'atténuation des risques pour l'Automatisation des tests

**Considérations architecturales initiales :**

L'interface entre le TAF et le SUT doit être prise en compte dans le cadre de la conception architecturale. Cette interface détermine la façon dont l'automatisation interagit avec le système testé et influence directement la sélection des outils de :

- **Packaging** : Gestion des versions et distribution du testware
- **Logging des tests** : Capture des informations d'exécution et de débogage
- **Harnais de test** : Infrastructure d'exécution des tests automatisés

**Facteurs critiques d'évaluation du pilote :**

Au cours de l'implémentation du projet pilote, l'expansion et la maintenance du code d'Automatisation des tests doivent être prises en compte. Ce sont des facteurs cruciaux de la phase d'évaluation du pilote et ils peuvent sérieusement affecter la décision finale.

| **Facteur** | **Description** | **Impact sur la décision** |
|-------------|-----------------|----------------------------|
| **Évolutivité** | Capacité à étendre le code de la solution d'automatisation | Évolutivité et viabilité long terme |
| **Maintenabilité** | Facilité de maintenance à long terme | Coûts opérationnels et durabilité |

**🌐 Risques d'infrastructure et stratégies d'atténuation :**

Différents risques liés au déploiement peuvent être identifiés à partir du pilote. Il faut se préparer aux risques liés au déploiement, tels que les problèmes de pare-feu, l'utilisation des ressources, la connexion au réseau et la fiabilité. Ces éléments ne sont pas strictement liés à l'Automatisation des tests, mais les TAE doivent s'assurer que toutes les conditions sont réunies pour fournir des points de contrôle de qualité fiables et bénéfiques dans leur processus de développement.

| **Catégorie de risque** | **Description** | **Impact** | **Stratégie d'atténuation** | **Implémentation** |
|------------------------|-----------------|------------|----------------------------|-------------------|
| **Configuration** | • Pare-feu bloquant les communications<br>• Ports réseau fermés<br>• Règles de sécurité restrictives<br>• Configuration DNS incorrecte | Tests indisponibles | Configuration réseau appropriée | • Ouverture des ports nécessaires<br>• Règles de pare-feu spécifiques<br>• Tests de connectivité automatisés<br>• Validation de la configuration |
| **Performance** | • Consommation excessive CPU/RAM<br>• Concurrence entre tests<br>• Timeouts d'exécution<br>• Ressources partagées insuffisantes | Tests lents ou échecs | Monitoring et optimisation | • Monitoring en temps réel<br>• Limitation des ressources par test<br>• Optimisation des scripts<br>• Planification des exécutions |
| **Stabilité** | • Services SUT indisponibles<br>• Instabilité des connexions réseau<br>• Pannes système intermittentes<br>• Défaillances des composants | Tests intermittents ou impossibles | Redondance et monitoring | • Health checks automatisés<br>• Services de backup<br>• Connexions multiples<br>• Retry automatique |

**📱 Risques spécifiques (mobile) et stratégies d'atténuation :**

L'utilisation d'appareils réels pour l'Automatisation des tests mobiles en est un exemple. Les appareils mobiles doivent être mis sous tension, disposer d'une autonomie de batterie suffisante pour fonctionner pendant le test, être connectés à un réseau et avoir accès au SUT.

| **Catégorie de risque** | **Description** | **Impact** | **Stratégie d'atténuation** | **Implémentation** |
|------------------------|-----------------|------------|----------------------------|-------------------|
| **Alimentation** | • Appareils éteints ou en veille<br>• Batterie insuffisante pour la durée du test<br>• Coupures de courant<br>• Recharge incomplète | Tests non exécutables ou interrompus | Alimentation continue et monitoring | • Alimentations de secours (UPS)<br>• Scripts de réveil automatique<br>• Alertes de batterie faible<br>• Recharge automatique |
| **Connectivité** | • Perte de connectivité réseau<br>• SUT inaccessible depuis l'appareil<br>• Configuration réseau incorrecte<br>• Problèmes de sécurité réseau | Tests échoués ou impossibles | Redondance et configuration | • Connexions multiples (WiFi/4G)<br>• Tests de connectivité<br>• Configuration réseau appropriée<br>• Basculement automatique |

**⚙️ Risques techniques de déploiement et stratégies d'atténuation :**

Les risques techniques liés au déploiement peuvent inclure le packaging, le logging, la structuration des tests et la mise à jour. Chaque aspect présente des défis spécifiques qui peuvent compromettre la réussite du déploiement.

| **Catégorie de risque** | **Description** | **Impact** | **Stratégie d'atténuation** | **Implémentation** |
|------------------------|-----------------|------------|----------------------------|-------------------|
| **Versioning** | **Packaging** : Perte de versions, distribution complexe, incompatibilité entre versions<br><br>**Mise à jour** : Mises à jour automatiques non contrôlées, changements de version des appareils | Tests instables ou impossibles | Contrôle de version et compatibilité | • Git/SVN avec tags de version<br>• Repository centralisé<br>• Pipeline de validation<br>• Lock files et environnements virtuels |
| **Observabilité** | **Journalisation** : Logs insuffisants, trop verbeux, perte de logs critiques<br><br>**Monitoring** : Manque de visibilité sur l'état des systèmes | Difficulté d'investigation | Journalisation structurée et monitoring | • Configuration des niveaux de log<br>• Stockage centralisé et backup<br>• Health checks automatisés<br>• Rotation et archivage |
| **Architecture** | **Structuration des tests** : Harnais instable, dispositifs défaillants, tests non atomiques, organisation chaotique du code | Tests non reproductibles | Infrastructure robuste et organisation | • Monitoring du harnais<br>• Scripts de setup/teardown<br>• Isolation des tests<br>• Structure logique et documentation |

**📝 Notes contextuelles :**

- **Packaging** : Il s'agit de "conditionner" le code d'automatisation des tests pour le distribuer et le déployer. Comme le SUT, l'automatisation doit être versionnée, compilée et déployée. Sans packaging approprié, les tests ne peuvent pas être exécutés sur différents environnements (dev, test, prod).

- **Logging** : La journalisation capture les informations pendant l'exécution des tests. Sans logs, impossible de savoir pourquoi un test a échoué : était-ce un vrai bug du SUT ou un problème d'automatisation ? Les logs permettent de diagnostiquer et déboguer les échecs.

- **Test structuring** : Il s'agit d'organiser l'architecture des tests (harnais, dispositifs, suites). Une mauvaise structuration rend les tests fragiles et difficiles à maintenir. Par exemple, si les tests partagent des données, un échec peut en causer d'autres.

- **Updating** : Les mises à jour automatiques peuvent casser l'automatisation. Par exemple, une mise à jour de Selenium peut rendre les tests incompatibles, ou un changement d'OS sur un appareil mobile peut faire échouer les tests.

**Journalisation - Typologie recommandée :**

Les types suivants permettent d'avoir une vision exhaustive de l'ensemble des événements rencontrés dans les entrées du journal. Et permettent de les hiérarchiser et catégoriser rapidement afin de diagnotiquer efficacement les échecs de tests.

| **Type** | **Usage** | **Exemple d'utilisation** | **Contexte d'utilisation** |
|------------|-----------|---------------------------|----------------------------|
| **Fatal** | Événements d'erreur conduisant à l'abandon de l'exécution | Erreur critique système | Arrêt immédiat requis |
| **Erreur** | Condition/interaction échouée, cas de test échoué | Assertion échouée | Échec de test à signaler |
| **Avertissement** | Condition/action inattendue sans interruption | Valeur par défaut utilisée | Situation anormale mais récupérable |
| **Info** | Informations de base sur l'exécution | Début/fin de test | Suivi du flux d'exécution |
| **Débogage** | Détails spécifiques pour investigation | Variables intermédiaires | Analyse des problèmes |
| **Trace** | Informations maximales d'exécution | Flux complet d'exécution | Investigation approfondie |

### 4.3 Maintenabilité de la solution d'Automatisation des tests

#### **TAE-4.3.1 (K2)** : Expliquer quels sont les facteurs qui soutiennent et affectent la maintenabilité de la solution d'Automatisation des tests

**Facteurs influençant la maintenabilité :**

La maintenabilité est fortement influencée par les normes de programmation et les attentes des TAE les uns envers les autres.

### **A. Problèmes qui AFFECTENT la maintenabilité :**

**1. Codage en dur :**
Valeurs intégrées directement dans le code sans possibilité de modification externe (ex. `password123` vs `user.password`), ce qui:

- contraint à réaliser des modifications manuelles du code à chaque changement,
- rend les tests non portables,
- rend la maintenance coûteuse.

**2. Manque de standards :**
Absence de conventions et de règles communes pour l'écriture du code (ex. `btnLogin` vs `login_button`), ce qui:

- complique la compréhension du code par l'équipe
- augmente le temps de formation des nouveaux développeurs
- rend le code difficile à déboguer et maintenir

**3. Outils inadéquats :**
Absence ou utilisation inappropriée d'outils de développement et de qualité (ex. pas d'analyseurs statiques, branches Git désorganisées), ce qui:

- retarde la détection des problèmes de qualité
- produit un code peu lisible et mal formaté
- complique la collaboration avec risque de perte de code

### **B. Solutions qui SOUTIENNENT la maintenabilité :**

**1. Principes "Clean Code" (Robert C. Martin, 2008) :**

Le "Clean Code" est une approche de programmation qui vise à écrire du code lisible, maintenable et de qualité. Ces principes permettent d'établir des standard partagés au sein de l'équipe, rendant le code compréhensible et modifiable par tous.

| **Principe** | **Application** | **Bénéfice** |
|--------------|-----------------|--------------|
| **Convention de nommage** | Noms significatifs (`loginButton`, `resetPasswordButton`) | Identification claire des composants |
| **Structure de projet** | Organisation logique et commune | Navigation facilitée |
| **Éviter le codage en dur** | Variables d'environnement, configuration | Flexibilité |
| **Paramètres limités** | 3-4 paramètres maximum | Lisibilité |
| **Méthodes courtes** | Une méthode = une responsabilité | Compréhension |
| **Logging approprié** | Niveaux adaptés selon le contexte | Diagnostic |
| **Patterns de conception** | Page Object Model, Façade, Singleton | Code structuré |
| **Testabilité** | Séparation des responsabilités | Qualité |

**2. Stratégies anti-codage en dur :**

Le codage en dur (voir A.1) consiste à intégrer des valeurs directement dans le code sans pouvoir les modifier. La solution consiste à créer des "alias" (références) vers des sources externes :

| **Solution** | **Méthode** | **Bénéfice** |
|--------------|-------------|-------------|
| **Tests pilotés par les données** | Créer des alias vers des sources de données externes (CSV, base) | Données maintenues dans une source commune, modification facile |
| **Constantes centralisées** | Créer des alias vers des constantes dans un fichier de configuration | Réduction des sources à maintenir, modification en un seul endroit |
| **Configuration externalisée** | Créer des alias vers des variables d'environnement | Adaptation sans recompilation, maintenance simplifiée |

**3. Outils de qualité :**

| **Outil** | **Fonction** |
|-----------|--------------|
| **Analyseurs statiques** | Vérification automatique du code |
| **Formateurs de code** | Mise en forme automatique |
| **IDE intégrés** | Outils de développement |

**4. Gestion de version :**

- **Branches de fonctionnalités** : Développement de nouvelles features
- **Branches de versions** : Gestion des releases  
- **Branches de corrections** : Fixes de bugs
- **Structure de projet** : Organisation logique

**5. Patterns de conception :**

L'utilisation de canevas de conception est fortement recommandée. Les patterns - tels que décrits au point 3.1.5 - permettent d'implémenter un code d'Automatisation des tests structuré et correctement maintenable, à condition qu'ils soient utilisés correctement.