## Chapitre 5 : Stratégies d'implémentation et de déploiement (90 minutes - K3)

### Objectifs

En apprendre plus sur :

- Les pipelines CI/CD et l'éxécution des tests dans les différents niveaux de test
- La gestion de la configuration pour les composants de l'automatisation (testware)
- les dépendances liées aux tests d'API et aux tests de contrat

### Mots-clés

| **Mot** | **Définition** |
|---------|----------------|
| **test de contrat** | Type de test d'intégration vérifiant que les interfaces sont utilisées comme spécifié dans leurs contrats. |

### Introduction

Quand le produit croît, la complexité explose tandis que les ressources restent finies: la qualité manuelle ne tient pas. La solution est un système d'automatisation autonome, maintenable, ancré dans les pipelines CI/CD, qui contrôle la qualité à chaque changement de façon traçable et reproductible. 

Ce chapitre traite trois aspects stratégiques de ce déploiement: le **placement** des tests dans le flux CI/CD (5.1.1), la **configuration** permettant de tourner sur tout environnement (5.1.2), et la **maîtrise des dépendances** en infrastructure API (5.1.3).

### 5.1 Intégration aux pipelines CI/CD

Les tests automatisés s'exécutent sans surveillance: on peut donc les intégrer aux pipelines CI/CD ou les planifier périodiquement. Le défi est de déterminer **où** les exécuter (à quelle étape du pipeline), **comment** les déclencher (sur chaque push, merge, ou déploiement), et **avec quelle politique de blocage** (point de contrôle bloquant ou informatif). La réponse à ces trois questions transforme un ensemble de scripts en garde‑fou opérationnel.

### **5.1.1 (K3) : Appliquer l'automatisation à différents niveaux de test dans les pipelines**

Principes
- Exécuter chaque niveau de test à l’étape du pipeline où il apporte le meilleur rapport «contrôle qualité / coût et délai».
- Utiliser des points de contrôle bloquants là où un échec doit empêcher la progression (merge ou déploiement).

Intégration par niveau

| **Niveau** | **Étape du pipeline** | **Point de contrôle (bloquant)** | **Déclencheur** | **Objectif** |
|------------|-----------------------|-------------------------------|------------------|-------------|
| Config TAF/TAS | Build | Oui | à chaque push/PR | Fail‑fast (chemins/fichiers/configs valides) |
| Composant | Build | Oui | à chaque push/PR | Qualité des unités/bibliothèques |
| Intégration composant | Build/Intégration | Oui (si bas niveau) | à chaque push/merge | Interfaces entre composants |
| Système | Déploiement (CD) | Oui (si bloque release) | au déploiement | Dernier garde‑fou du SUT |
| Intégration système / Acceptation | Livraison | Oui/Non (contexte) | à la livraison | Fonctionnement bout‑à‑bout |

Modes d’intégration des tests système/acceptation
1) En phase de déploiement (bloquant): échec ⇒ déploiement annulé/rollback; limite: relancer implique redéployer.
2) Pipeline séparé (non bloquant): utile si suites longues/variées; prévoir une procédure de rollback/feature‑flag.

Exécutions périodiques
- Régression nocturne (suites longues) pour fournir un état de santé chaque matin.
- Non‑fonctionnels (ex. performance) en continu ou en pipeline dédié pour la surveillance.

À retenir
- Placer les tests là où ils protègent au meilleur coût; rendre bloquants ceux qui doivent empêcher la progression.
- Choisir déploiement (bloquant) vs pipeline séparé (non bloquant) selon l’enjeu et la durée.
- Programmer des exécutions périodiques pour la régression longue et les non‑fonctionnels.

Bonnes pratiques (5.1.1)
- Tests rapides en build; lents/longs hors chemin critique (mais référencés).
- Quality gates explicites (seuils, critères d’échec, ownership).
- Environnements éphémères, artefacts immuables, données seed contrôlées.

Anti‑patterns (5.1.1)
- Tout miser sur des E2E lents et fragiles.
- Absence de gates (tests “informés” mais non bloquants par erreur).
- Flaky non traités, envs partagés et non isolés.

**→ Transition :** Une fois le placement défini, il faut garantir que l’automatisation tourne partout: place à la **gestion de la configuration**.

### **5.1.2 (K2) : Expliquer la gestion de configuration pour les testware**

Contexte/Problème/Objectif/Solution
- Contexte: mêmes tests, environnements et versions multiples.
- Problème: dérive de config/données → échecs non reproductibles.
- Objectif: portabilité et traçabilité du testware.
- Solution: checklists Env/Données/Suites + versioning.

Checklists de configuration

Environnements
- URLs, credentials et secrets externalisés (pas dans le code)
- Conventions de nommage, variables standardisées, stockage versionné
- Environnements éphémères quand possible

Données de test
- Jeux par environnement/release, stratégie seed/refresh
- Anonymisation/pseudonymisation si données réelles
- Ownership clair et traçabilité des datasets

Suites de tests
- Suites taggées par objectif: smoke, régression, acceptation, non‑fonctionnels
- Mapping suites ↔ étapes du pipeline
- Temps cible par suite (rapide vs longue)

Stratégies de versioning
- Feature toggles: pour activer/neutraliser des features selon release/env
- Versioning aligné SUT↔testware via tags/branches quand compatibilité stricte

**→ Transition :** La configuration étant en place, la fiabilité en architectures API dépend des **dépendances**: contrats, auth, données et observabilité.

### **5.1.3 (K2) : Expliquer les dépendances pour une infrastructure API**

Contexte/Problème/Objectif/Solution
- Contexte: microservices, interfaces inter‑équipes, fournisseurs.
- Problème: intégrations instables sans contrats/données/observabilité.
- Objectif: fiabilité mesurable des tests API.
- Solution: checklist dépendances + contract testing opérationnel.

Checklist dépendances API
- Contrats (OpenAPI/AsyncAPI) versionnés et partagés
- Authentification/autorisation (modes, scopes) documentées
- Idempotence, limites, timeouts, ordonnancement d’appels
- Mocks/stubs/virtualisation disponibles pour intégration
- Données seed de référence et jeux contrôlés
- Observabilité: logs corrélables, métriques, traces

Contract testing (quand/comment)
- Quand: microservices, interfaces inter‑équipes, fournisseurs externes, SLA stricts.
- Consumer‑driven: besoins client priment; Provider‑driven: surface stable, forte réutilisation.
- “Done”: contrat versionné + vérifié en CI; rupture de contrat = gate fail.

Exemple end‑to‑end (compact)
- PR: unit + config (gate < 10 min).
- Merge: intégration composant (gate < 15 min).
- Deploy: smoke système (gate), rollback auto si échec.
- Nuit: régression longue + perf (non‑gate), rapports au matin.

Mini‑glossaire (chapitre)
- Gate: test bloquant qui empêche merge/déploiement s’il échoue.
- Delivery vs Deploy: livraison (release) vs déploiement (mise en env).
- Éphémère: environnement recréé à chaque exécution.
- Artefact immuable: build signé, non modifié après création.
- Seed: initialisation contrôlée des données de test.
- Contract testing: vérifie qu’un service respecte les interactions convenues.