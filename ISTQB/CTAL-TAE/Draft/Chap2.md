# Syllabus

## 2 Se préparer à l'Automatisation des tests – 180 minutes (K4)

### Mots clés

Tests d'API, tests de l'interface graphique, testabilité

### Objectifs d'apprentissage pour le chapitre 2

- **2.1** Comprendre la configuration d'une infrastructure permettant l'Automatisation des tests
  - **TAE-2.1.1** (K2) Décrire les besoins de configuration d'une infrastructure permettant l'implémentation de l'Automatisation des tests.
  - **TAE-2.1.2** (K2) Expliquer comment l'Automatisation des tests est exploitée dans différents environnements.
- **2.2** Processus d'évaluation pour sélectionner les bons outils et les bonnes stratégies
  - **TAE-2.2.1** (K4) Analyser un système sous test pour déterminer la solution d'Automatisation des tests appropriée.
  - **TAE-2.2.2** (K4) Illustrer les constatations techniques d'une évaluation d'outil.

## 2.1 Comprendre la configuration d'une infrastructure permettant l'Automatisation des tests

### 2.1.1 Décrire les besoins de configuration d'une infrastructure permettant l'implémentation de l'Automatisation des tests

La testabilité du SUT (c'est-à-dire la disponibilité d'interfaces logicielles qui soutiennent les tests, par exemple pour permettre le contrôle et l'observabilité du SUT) devrait être conçue et implémentée parallèlement à la conception et à l'implémentation des autres caractéristiques du SUT. Ce travail est généralement effectué par un architecte logiciel car la testabilité est une exigence non fonctionnelle du système. Il est souvent accompagné d'un TAE pour identifier les domaines spécifiques où des améliorations peuvent être apportées.

Pour une meilleure testabilité du SUT, il existe différentes solutions qui peuvent être utilisées et qui ont des besoins de configuration différents, par exemple :

- **Identifiants d'accessibilité**
  - Les différents frameworks de développement peuvent générer ces identifiants automatiquement ou les développeurs peuvent les définir manuellement.
- **Variables d'environnement du système**
  - Certains paramètres de l'application peuvent être modifiés pour permettre de tester plus facilement l'application par le biais de l'administration.
- **Variables de déploiement**
  - Similaires aux variables du système, mais qui peuvent être définies avant de commencer le déploiement.

La conception de la testabilité d'un SUT comprend les aspects suivants :

- **Observabilité** : Le SUT doit fournir des interfaces qui donnent un aperçu du SUT. Les cas de test peuvent alors utiliser ces interfaces pour déterminer si les résultats réels correspondent aux résultats attendus.
- **Contrôlabilité** : Le SUT doit fournir des interfaces qui peuvent être utilisées pour effectuer des actions sur celui-ci. Il peut s'agir d'éléments d'interface utilisateur, d'appels de fonction, d'éléments de communication (par exemple, protocole de contrôle de transmission/protocole Internet (TCP/IP) et protocoles de bus série universel (USB)) ou de signaux électroniques pour des commutateurs physiques ou logiques sur les différentes variables d'environnement.
- **Transparence de l'architecture** : La documentation d'une architecture doit fournir des composants et des interfaces clairs et compréhensibles qui donnent une observabilité et un contrôle à tous les niveaux de test et favorisent la qualité.

### 2.1.2 Expliquer comment l'Automatisation des tests est exploitée au sein de différents environnements

Différents types de tests automatisés peuvent être exécutés dans différents environnements. Ces environnements peuvent différer selon les projets et les méthodologies, et la plupart des projets disposent d'un ou plusieurs environnements utilisés pour tester. D'un point de vue technique, ces environnements peuvent être créés à partir de conteneurs, de logiciels de virtualisation et d'autres approches.

Voici une série d'environnements possibles à prendre en considération :

#### Environnement de développement local

L'environnement de développement local est l'endroit où le logiciel est initialement créé et où les composants sont testés par automatisation pour vérifier leur aptitude fonctionnelle. Plusieurs types de tests peuvent être effectués dans l'environnement de développement local, notamment des tests de composants, des tests d'interface graphique et des tests d'interface de programmation d'applications (API).

Il est également important de noter qu'en utilisant un environnement de développement intégré (IDE) sur l'ordinateur donné, des tests boîte blanche peuvent être effectués afin d'identifier le plus tôt possible les problèmes de codage et de qualité médiocre.

#### Environnement de Build

Son objectif principal est de construire le logiciel (NDT: build) et d'exécuter des tests qui vérifient l'exactitude de la construction résultante dans un écosystème DevOps. Cet environnement peut être soit un environnement de développement local, soit un agent d'intégration continue/de livraison continue (CI/CD) où les tests de bas niveau (c'est-à-dire les tests de composants et les tests d'intégration continue des composants) et l'analyse statique peuvent être effectués sans déploiement réel dans d'autres environnements.

#### Environnement d'intégration

Après les tests de bas niveau et l'analyse statique, l'étape suivante est un environnement d'intégration des systèmes. Il s'agit d'un candidat à la release du SUT qui est entièrement intégré à d'autres systèmes pouvant être testés. Dans cet environnement, une suite de tests entièrement automatisée, soit des tests d'interface utilisateur, soit des tests d'API, peut être exécutée. Dans cet environnement, il n'y a pas de tests boîte blanche, mais uniquement des tests boîte noire (c'est-à-dire des tests d'intégration des systèmes et/ou des tests d'acceptation). Il est important de noter qu'il s'agit du premier environnement où une surveillance (NDT : monitoring) devrait être présente pour voir ce qui se passe en arrière-plan pendant l'utilisation du SUT afin de permettre une investigation efficiente des défauts/défaillances.

#### Environnement de préproduction

Un environnement de préproduction est utilisé principalement pour auditer les caractéristiques de qualité non fonctionnelles (par exemple, l'efficience de la performance). Bien que les tests non fonctionnels puissent être réalisés dans n'importe quel environnement, l'accent est mis sur la préproduction parce qu'elle ressemble le plus possible à la production. Souvent, les tests d'acceptation des utilisateurs peuvent être effectués par les parties prenantes Métier pour vérifier le produit final et il est possible d'exécuter la suite automatisée de tests existante ici aussi, si nécessaire. Cet environnement est également surveillé.

#### Environnement de production/d'exploitation

Un environnement de production peut être utilisé pour évaluer les caractéristiques de qualité fonctionnelles et non fonctionnelles en temps réel pendant que les utilisateurs interagissent avec un système déployé grâce au suivi et à certaines meilleures pratiques qui permettent les tests en production (par exemple, la release canari, le déploiement bleu/vert et les tests A/B).

## 2.2 Processus d'évaluation pour sélectionner les bons outils et stratégies

### 2.2.1 Analyser un système sous test pour déterminer la solution d'Automatisation des tests appropriée

Chaque SUT peut être différent d'un autre, mais il y a plusieurs facteurs et caractéristiques qui peuvent être analysés pour avoir une solution d'Automatisation des tests (TAS) réussie. Au cours de l'étude d'un SUT, les TAE doivent rassembler les exigences en tenant compte de son périmètre et de ses capacités données. Différents types d'applications (par exemple, service Web, mobile et Web) nécessitent différents types d'Automatisation des tests d'un point de vue technique. L'enquête peut être effectuée - c'est recommandé - en collaboration avec d'autres parties prenantes (par exemple, les testeurs manuels, les parties prenantes métier et les analystes métier) pour identifier autant de risques et leurs atténuations que possible afin d'avoir une solution d'Automatisation des tests bénéfique pour l'avenir.

Les exigences d'une approche d'Automatisation des tests et d'une architecture d'Automatisation des tests doivent prendre en compte les éléments suivants :

- Quelles activités du processus de test doivent être automatisées, (par exemple, la gestion des tests, la conception des tests, la génération des tests et l'exécution des tests).
- Quels niveaux de test doivent être soutenus ?
- Quels types de tests doivent être soutenus ?
- Quels rôles et compétences en matière de tests doivent être soutenus ?
- Quels produits, lignes de produits et familles de logiciels doivent être soutenus (par exemple, pour définir l'étendue et la durée de vie du SAE implémenté ?
- Quels types de SUT doivent être compatibles avec la TAS ?
- Quelle est la disponibilité des données de test et quelle est leur qualité ?
- Quelles sont les méthodes possibles et les moyens d'émuler des cas inaccessibles (par exemple, les applications tierces concernées) ?

### 2.2.2 Illustrer les constatations techniques d'une évaluation d'outil

Après l'analyse du SUT et la collecte des exigences auprès de toutes les parties prenantes, il est probable que des outils d'Automatisation des tests répondant à ces exigences puissent être envisagés. Il se peut qu'il n'y ait pas un seul outil qui réponde à toutes les exigences identifiées, et les parties prenantes devraient reconnaître cette possibilité.

Il est utile de rassembler les constatations sur les outils possibles et de réfléchir aux diverses exigences directes et indirectes dans un tableau comparatif. L'objectif du tableau de comparaison est de permettre aux parties prenantes de voir les différences entre les outils sur la base d'exigences spécifiques. Le tableau de comparaison présente les outils dans les colonnes et les exigences dans les lignes. Les cellules contiennent des informations sur les propriétés de chaque outil par rapport à chaque exigence ainsi que sur les priorités.

En général, les outils d'Automatisation des tests doivent être évalués pour déterminer s'ils répondent à l'exigence identifiée dans la section précédente (2.2.1). Les exigences à prendre en compte lors de l'évaluation et de la comparaison des outils comprennent :

- Le langage/la technologie de l'outil et les outils IDE.
- La capacité à configurer un outil, qu'il soutienne différents environnements de test, qu'il exécute des configurations et qu'il utilise des valeurs de configuration dynamiques ou statiques.
- La capacité à gérer les données de test au sein de l'outil. La gestion des données de test pourrait être intégrée à un référentiel central pour le contrôle des versions.
- La nécessité éventuelle de devoir sélectionner différents outils d'Automatisation des tests pour différents types de tests.
- La capacité à fournir des fonctionnalités de reporting. Ceci est important pour s'aligner sur les exigences du projet en matière de reporting des tests.
- La capacité à s'intégrer à d'autres outils utilisés sur un projet ou dans l'organisation, tels que CI/CD, le suivi des tâches, la gestion des tests, le reporting ou d'autres outils.
- La capacité d'étendre l'architecture de test globale et d'évaluer l'évolutivité, la maintenabilité, la facilité de modification, la compatibilité et la fiabilité des outils.

Ce tableau de comparaison est une bonne source pour déterminer une proposition d'outil ou d'ensemble d'outils à utiliser pour l'Automatisation des tests du SUT.

Le processus peut varier quant à la manière dont la décision est prise sur le(s) outil(s) à utiliser, mais la proposition doit être présentée aux parties prenantes appropriées pour approbation.

# Notes

## Describe the configuration needs of an infrastructure that enable implemantion of test automation

### Understandind testability in the SUT

Key concepts:

- Testability = availability of software interfaces that support testing. 
- Provides control and observability in the SUT. 
- not something to add after, but should be designed alongside system features. 
- responsability of SA (software architect), with input from TAE (test automation engineer)

### Solution for better testability

several options possibles:

- Accessibility Identifiers
  - Unique ID for UI elements (make it easily findable by automated test)  
  Ex. project with no accessibility identifiers. have to rely on XPath selector breaking constantly. make the project a nightmare. After accessibility identifier, testability improved dramatically
  - Accessibility identifier can be generated automatically by a developpement framework or set manually by developpers (more reliable)
- System Variables
  - Paramaters changed through adminsitration to enable easier testing (ex. enable "test mode" of an application making certain features more accessible or predictable)
- Deployment variables
  - similar to System variable, but can be set before deployment  
  EX. setting the application to use a test database instead of the production database for automated test runs

### Key Aspects of designing for Testability

3 main aspects:

- **Observability**
  - SUT must provide interfaces giving insight into internal behavior (like putting windows on a black boxe as you need to see whats going on inside)
  - TC (Test cases) use thoses interface to determine the actual result match the expected results  
  Ex. Banking App, logging endpoints were added allowing to monitor transactions process behind the scene, make easier to verify if test are working properly
- **Controlability**
  - SUT must provide interface to perform actions
  - Includes UI interactions (ex. clickable/interractive UI element), functions calls (can be triggered), communications protocols (ex. TCPIP or USB protocole, electronic signals for physical or logical switches), etc.
  - Otherwise, can observe the system but can not test it properly
- (Architecture) **Transparency**
  - Clear documentation of components and interfaces (providing observability and controlabilty for all test level on the system. Foster quality throughtout the testing process)  
  Feedback : poor documentation lead to confusion on testing process for certain feature, while transparent architecture, allow good understanding of how the system work and effective testing

### Why testability is important ?
configuring infrastructure for testability is essential for effective test automation.

| without testability | with testability |
|--------------------|------------------|
| Automated tests are fragile, unreliable, and hard to maintain | Good testability = reliable tests + meaningful results + less manual work |
| Test break frequently due to application changes<br> (Spend more time fixing test than finding defects) | Investing in testability early saves time later ("pay now, or pay muchh more later" situation) |

### Conclusion
1. testability must be designed and implemented alongside other features
2. Solution for better testability:
  - Accessbility identifiers
  - System environment variables
  - Deployment variables
3. Key aspects of designing for testability:
  - Observability
  - Controlability
  - Architecture Transparency

## Explain how test automation is leveraged within different environments

Important because:
- Understanding test environments is crucial for designing effective automation strategies
- "Environnement" = different setups or configurations where tests runs (like different stages in the software pipeline wiht specific purposes)
- Examples : containers, virtual machines, cloud platforms, etc.

### What are test environments ?

- environments existing to verify sofware before production (reaching end users)
- May vary by projects and methodologies
- Ex. of technical setups : 
  - Containers (Docker, Kubernetes)
  - Virtualization (VMware, VirtualBox)
  - Cloud platforms (AWS, Azure, Google Cloud)
  - On-premise servers
  - etc.
- Real world ex. : 5 different environments, each with specific purpose (Dev, QA, UAT, Staging, Production), managing test in each environment was challenging at first, but make test automation more efffective, once good understanding of the purpose of each environment.

### Local Development Environment

- Is on the developers own machine
- used to create and runs automated tests, such as Component testing, GUI testing, API testing, etc. (frist line of defence against bugs)
- enable white box testing using IDEs (e.g?, Visual studio, Intellij)
- developpers can steps throught the code , line by line, and run unit tests) (ex. discount validation)

### Build Environment

- is a local environment or part of a CI/CD pipeline (ex. jenkins, gitlab, bitbucket, etc.)
- Part of DevOps pipeline (CI/CD)
- used to build the software
- Runs low-level automated tests
  - Component tests
  - Integration tests
  - Static analysis (analyzing code before execution)
- Ex. previous company, used Bitbucket as CI/CD tool (every push on repo > auto-builds code > runs unit tests, if failed tests, email notification to developers)

### Integration Environment

- is a deployment environment
- runs a fully integrated release candidate of the SUT (ex. new app version)
- Executes UI and API tests as users would
- Black-box testing only
- Introduces monitoring for test investigation:
  - logs,
  - API calls,
  - DB queries,
- Ex. logs help identify test failures or real bugs

### Pre-production/ Staging/ UAT Environment

- is a deployment environment
- resembles production environment as closely as possible
- runs non-functional tests
  - performance tests
  - load tests
  - security tests
  - usability tests
  - etc.
- runs acceptance tests (stakeholders performs user acceptance testing )
- Automated tests suites may be reused here
- monitoring is critical for analysis (for troubleshooting and analysis)

### Production/ Operational Environment

- Final environment (where users interact with the System)
- runs functional and non functional testing in real time:
  - Canary releases (roll out a new feature to a small subset of users)
  - Blue/Green deployments (two environments are maintened in parallel, but only one is live (PRD). The other one is the staging environment. the deployement consists in deploying on the non-live envrironment the new features, then redirecting DNS to this environment. The staging environment become the production environment, and vice versa)
  - A/B testing (deploy two versions of a same feature on production environment, to monitor which version performs better). Ex. deploy search feature to 5% of users and monitor feedback.

### real world example

- Developping a new recommandation feature for a e-commerce website
- Local environment : developpers writes code for recommandation algorithm, and creates unit tests to verify the expected product is returned based on use's purchase history
- Build environment : When code pushed to repository, the CI/CD system build the application and runs all unit tests ensuring code doesn't break existing functionality
- Integration environment : features is deployed there, and automated tests verify the recommandations appear on the product page, clicking on the recommanded product redirect the user to the product page, and API that serves the recommandation, returns the correct data format.
- Pre-production environment : performance tests verify loading recommandation doesn't slow down the page, Business stakeholders check the recommandation make sense from a business perspective.
- Production environment : feature roll out to 10% users, metrics are collected to measure user engagement with and without the new recommandation. Based on positive results, it is gradualy rolled out to all users.

### Conclusion
1. test automation can be leveraged in multiple environments
2. each environment serves a specific purpose :
  - Local : early testing
  - Build : Code validation
  - Integration : Full system test
  - Pre-production : Final non-functional checks
  - Production : Real-world validation
3. understanding environment purpose helps design effective automation strategies to catch defects early and save time
4. common mistakes : no clear plan for where test should run

## Analyse a system under test to determine the appropriate test automation solution

### Understanding the uniqueness of systems

- **Every system is unique** — Each SUT has its own specificities and constraints that differ from other systems (e.g. web vs mobile vs API).
- **System specificities must guide the decision** — The test automation solution must be derived from the system’s specificities and constraints, not the other way around (no one-size-fits-all).
- **Analyse system factors and characteristics** — Identify what matters for automation: type of application, technical stack, interfaces (UI, API), testability, integration points, risks.
- **Gather requirements considering scope and capabilities** — Scope = what to automate, which products/lifecycle; capabilities = what the SUT and organisation can support (skills, data, environments, tools).

### Real world example : Different systems, different tools

Few years ago, works on two project simultaneously. Two different approaches were used to implement test automation for each system : 
1. A Web Service Backend system (no UI) - required API focused testing tools
2. A Mobile banking application - required tools which could interact (tools simulating touchscreens interaction, and supporting mobile features)

### Collaborative Analysis is Crucial

- Don't work alone (this investigation must not be done in silo) - collaborate with other stakeholders:
  - Manual testers (know testing challenges)
  - Business stakeholders (understand business risk)
  - Business analysts (deep understanding of requirements)
- Collaboration helps identify risks and improve solutions
- Ex. Project were critical business logic were missed due to not involving the business analyst in the test automation planning. A significant portion of the framework had to be rewritten later (loss of time and ressources).

### Requirements to consider

- **test process activities** : Which test process activities should be automated ?
  - Test management - tracking what tests exist and their results
  - Test design - creating test cases and data
  - Test generation - Automatically creating test casses based on models or other inputs
  - Test execution - Running tests and collecting results
  - Ex. regulated industry like healthcare vs Startup - Needs of robust test automation management to provide compliance for healthcare industry, while a fast moving startup will prioritize automated test case for fast execution and feedback.
- **Test levels** : Which test levels should be supported ?
  - Component testing - testing individual pieces of code
  - integration testing - testing how components works together
  - system testing - testing the entire system
  - acceptance testing - testing wether the system meets business requirements
  - Ex. project where automation test effort was focused on system level automation because most regression issues were there. Other projects, automation effort was focused on component level to get faster feedback.

- **Test types** : Which test types should be supported ?
  - Functional testing - Does it work as expected ?
  - Performance testing - Is it fast enough ?
  - Security testing - Is it secure ?
  - Usability testing - Is it easy to use ?
  - /!\ Different test types require different approaches and tools

- **Test roles and Skill sets** :
  - Who will be creating and maintaining the automated test ?
  - What programming skills do they have ?
  - How familiar are they with the test automation concepts ?
  - ex. A team has invested in a complex code automation framework, while most testers had limited programming experience. Framework was impressive but practically useless as no one could maintain it.

- **Product considerations** :
  - Which software products, products lines, and families should be supported ?
  - What is the expected lifespan of the implemented TAS ?
  - Will it need to support multiple versions of the software ?

- **SUT compatibility** : What kind of SUTs must be compatible with your TAS ?
  - Is a web application, a mobile application, a desktop application, or something else ?
  - Does it have a graphical user interface (GUI), application programming interface (API), or both ?
  - what technologies is it built with ?
  - each type of application requires different automation approach.
  Ex. Web application may use Playright, while API may use Karate DSL.

- **Test Data Availability** :
  - Is test data readily available ?
  - Whats the quality of the test data ?
  - Can you generate test data as needed ?
  - Are there privacy or security concerns with the test data ?
  - Ex. Health care project, almost same work load for creating realistic but anonymized test data, than automation itself.

- **Edge cases and Third-Party Applications** : How will you handle situations ?
  - How will you emulate unreachable cases ?
  - How will you handle third-party application that you can't control ?
  - What about external systems that might not be available in a test environment ?
  - Ex. Payment processor integration in the system, may need to run real credit card transactions during test automation. So have to figure out how to simulate or mock those interactions

### Practical approach
  1. Document the system architecture : Get a clear understanding of all components, interfaces and technologies used in the SUT.
  2. Map out user journey : identify the key workflows that users will follow through the system.
  3. Identify high-risk areas : Which parts of the system would cause the biggest problems if they failed ?
  4. Assess technical feasibility : For each part of the system, determine how easily it can be automated.
  5. Consider ressource constraints : What budget, time, and expertise do you have available ?
  6. Create a prioritized automation roadmap : Based on risk, feasibility, and constraints, decide what to automate first.

ex. automation of a Retail point sale system having a touch screen interface connected to inventory system and process payment.

- Analysis revealed : 
  - payment processing present the highed business risk but was complex to automate. 
  - Inventory management had APIs that were straitforward to test
  - The touchscreen UI used custom framework with limited automation support.
- Decision taken : 
  - Start with API automation for the inventory management (easy wins)
  - Build simulations for the payment processing (adressing high risk)
  - Create a limited set of UI tests for critical paths only (managing the technical challenges)

Prioritize approach is the best ROI for automation investment.

### Conclusion
Analysis SUT to determine the TAS involves :

1. Understanding each system is unique and requires careful analysis (understanding system specificities and constraints, and require a comprehensive analysis)
2. Collaborating with various stakeholders to identify risks and requirements
3. Considering multiple factors including:
  - Test process activities to automate
  - test levels to support
  - test types to include
  - Test roles and skill sets available
  - Product considerations and lifespan
  - SUT compatibility requirements
  - Test data availability and quality
  - Strategies for handling edge cases and third party applications
4.  Creating a prioritized approach based on risk, feasibility, and constraints

/!\ Goal != not automate everything , == Automate the right thing and the right way to provide the most value.
A well thought out analysis is the foundation of a successfull test automation.

## Illustrate the technical findings of a tool evaluation

### 

### The comparison Table Approach

#### Sample comparison table
| Requirement (priority)      | Tool A | Tool B | Tool C |
|-----------------------------|--------|--------|--------|
| Javascript support (high)   | Excellent     | Good     | Limited     |
| Cross-browser testing (high)          | All major browsers     | Chrome & Firefox only     | All major browsers     |
| Mobile testing (high)          | Limited     | Excellent     | Good     |
| Reporting capabilities (high)  | Basic     | Comprehensive     | Customizable     |
| Learning curve (medium)       | Steep     | Moderate     | Gentle     |
| Cost (High)     | $$$     | $$     | Free/Open Source     |

#### Key Requirements to Assess

- Language and technology compatibility
  - Matching tool supported language with team expertise - Consider the programming language and the technology stack of both tools and IDE. ex. creating a skill gap due to a java team and a javascript tool.
  - Checking IDE compatibility - Verify if tool have integration with team IDE. ex. Tool having a VS code integration are a great plus for team using VS code.
  - Ex. Project stalled for months due to a Python team selection C# tool (steep learning curve). Situation resolved by switching to a Python tool.
- Configuration Flexibility - How flexible the tool configuration is ?
  - Multiple environments support ?
  - Easily running different configurations?
  - Static and dynamic values handling ?
  - ex. Tool supporting YAML config files made changes easy and fast.
- Test data management - How the tool handles test data ?
  - Support data import from external sources ?
  - Support Data-driven testing ?
  - Versionning support ? (can integrate with a central repository for version control)
  - ex. Ecommerce project with hundreds different products scenario for testing. Tool support Test data in CSV files easily updated by business analysts without editing code. (huge win for collaboration)
- Support for Different Test Types
  - Functional testing support ?
  - Performance testing support ?
  - Security testing support ?
  - Accessibility testing support ?
  - May need a suite of tools rather than a single solution. Ok for multiple tools with integrate well together.
  - ex. Healthcare application. Functional UI testing used WebdriverIO, Performance testing used Jmeter, Security testing used OWASP ZAP. each tools specialized in its domain.
- Reporting capabilities
   - Critical : capabilities to provide clear informative reports
   - Automated reports generation ?
   - Report customization ? (to adapt to team needs)
   - Report Non-tech accessibility ? (easy to understand by non-tech stakeholders)
   - Good reporting make visible the value of automation for all the organization.
   - ex. Tool generating beautiful HTML reports with screenshots of failures, timing information, and trends analysis. PMs could instantly assess app health without asking testing team.
- Integration with Other Tools - How well the tool integrates with existing tools chain ?
  - Working with CI/CD Tools ? (github actions, jenkins, gitlab, etc.)
  - Task tracking tools ? (Jira, Azure DevOps, etc.)
  - Test management tools ? (TestRail, QTest, etc.)
  - Seamless integration reduces workflow friction
  - ex. Project with Github Actions as CI/CD, choose specific tools with good github actions integration. Allow automatic test run on pull request, providing immediate feedback to developers.
- Overall Architecture Assessment - Evaluate the big picture aspect of the tool
  - Scalability : Can he handle the growing test suite ?
  - Maintenance : How easy is it to update test when application changes ?
  - Modifiability : Can you extend or customaze to meet specific needs ?
  - Compatibility : Will it work with the current and future systems ?
  - Reliability : Does it produce consistent results ?
  Critical aspects, not immediately apparent, on the long term.

### Creating an Effective Comparison Table

Tips :
- Objective Assessment - Use facts, not personal bias/preferences
- Clear reading usage - Such as "Excellent", "Good", "Fair", "Poor" or 1-5 scale.
- Contextualize - Add context to ratings to help stakeholders understand the meaning (why is good, and in which context).
- Weighted requirements - Weight requirements by importance to help priorization.
- Futur needs evaluation - Consider future (1-2 years) needs and potential growth, not just current.
Ex. Choose tool for immediate needs on a project, but with limited extensibility. requirements evolve six months later forcing to switch to a new tool, unable to adapt the work on the previous tool (lost time and ressources).

### Decision making process

- "Must-have" requirements filter - Exclude tools not meeting non-negociable needs.
- Score remaining tools - Assign points to each remaining tool for each requirement multiplied by the weight (importance).
- Calculate total score - Sum of all points for each tool.
- Consider intangible factors - vendor relationship, community support, futur roadmap can tip the scale when score are close
- Create a proposal - Recommande a tool or a tools set to use based on your analysis.
- Present findings to stakeholders - Demonstrate your findings to stakeholders for approval.

Ex. Choices narrowed down to 2 tools on a project, both well scored. Deciding factor was one had more active open source community, more frequent updates, suggesting better long term support.

### Use a proof of concept

Running a POC (proof of concept) before final decision, by:

- Implementing sample test casses
- Running in actual environment
- evaluating outcomes (based on criteria)

Reveal non-apparent issues or benefits from documentation alone.

Ex. POC rejected first chosen tool, because handling poorly custom javascript, while the second tool handled the custom javascript beautifully, saving team from a poor decision.

### Real-world Case Study

- Needed automated testing for a Web app: Angular frontend + REST API backend.
- Key requirements :
  - UI + API testing support (High)
  - non-coders learning accessibility (High) - Easy to learn for non-coders
  - Management reporting (Medium) - good reporting for management
  - Azure DevOps CI/CD Integration (High)
  - Cost (Medium) - Cost effective for a team of 10

| Requirement (priority) | Selenium + RestAssured | Cypress | TestComplete |
|-----------------------------|--------|--------|--------|
| UI + API testing support (High) | Good (seperate tiks but work well together) | Excellent (integrated solution) | Fair (UI-focused, limited API support) |
| Learning curve (High) |  Steep (requires solid java knowledge) | Moderate (Javascript, knowledge helpful but not required) | Gentle (Low-code approach) |
| Reporting (Medium) | Basic (needs custom extensions) | Good (built-in dashboard) | Excellent (Comprehensive visual reports) |
| Azure DevOps CI/CD Integration (High) | Excellent (native support) | Good (requires some configuration) | Good (requires some configuration) |
| Cost (Medium) | Free (open source) | Free for basic use | Expensive (per-seat licensing) |

Select Cypress (after requirements application and team discussion).
Selenium was excluded due to the steep learning curve and significant training investment.
Testcomplete was excluded being too expensive and lacking API testing capabilities.

### Conclusion

1. Use comparison table to vizualize evaluation result
2. Evaluate tools on :
    - Tech compatibility, flexibility, data handling
    - Test types support, reporting, integration
    - Architectural fit
3. Weight requirements realistically
4. Use POC (proof of concept) for top contenders
5. Present findings to stakeholders for approval - no perfect tool

## Q&A

### Question 1 - TAE-2.1.1 (K2) Describe the configuration needs of an infrastructure that enable implemantion of test automation

> [!question] Which of the following is NOT considered a key aspect of designing for testability in SUT (System Under Test) ?

- A) Observability - providing interfaces that give insight into SUT
- B) Controlability - providing interfaces that can be used to perform actions on the SUT
- C) Scalability - ensuring the SUT can handle increasing numbers of test executions.
- D) Achitecture transparency - providing clear, understandable components and interfaces.

> [!answer] C)

### Question 2 - TAE-2.1.2 (K2) Explain how test automation is leveraged within different environments

> [!question] In which enionment would it be most appropriate to perform white box testing using an IDE (Integrated Development Environment) ?

- A) Production environment
- B) Local development environment
- C) Pre-production environment
- D) Integration environment

> [!answer] B)

### Question 3 - TAE-2.2.1 (K4) Analyze a system under test to determine the appropriate test automation solution

> [!question] When analyzing a SUT to determine the appropriate test automation solution, which of the following is NOT mentioned as a consideration in the requierments gathering process ?

- A) Which test roles and skill sets should be supported ?
- B) Which test level should be supported ?
- C) Which programming language should be used for implementation ?
- D) Availability of test data and its quality ?

> [!answer] C)

### Question 4 - TAE-2.2.2 (K4) Illustrate the technical findings of a tool evaluation

> [!question] When creating a comparison table to illustrate the technical finding of a tool evaluation, which approach would be LEAST effective ?

- A) Listing the tools in the columns and the requirements in the rows
- B) Including information about the properties of each tool regarding each requirement
- C) Providing only the best-performing tool for each requierment with comparison.
- D) Including information about priorities of requirements.

> [!answer] C)