# Base de Connaissances ISTQB

Base de connaissances structurée pour étudier et préparer les certifications ISTQB (International Software Testing Qualifications Board) et autres formations en testing logiciel.

## 📋 Contenu

- **Documentation ISTQB** : Informations officielles, liens et processus de certification
- **Dossiers par certification** : Matériel d'étude organisé par formation (CTFL, CTAL-TA, CTAL-TM, CTAL-TAE, CT-AI, CTAL-ATT)
- **Frameworks de test** : Documentation des outils et frameworks (Playwright, Robot Framework, Selenium, Katalon Studio, JMeter, SOAP UI, LambdaTest)
- **Templates** : Modèles de documents réutilisables
- **Glossaire** : Terminologie technique bilingue avec interface web de consultation (268+ termes)
- **Notes** : Ressources d'apprentissage et références

## 🎯 Public cible

- Professionnels préparant les certifications ISTQB
- Étudiants en testing logiciel
- Équipes cherchant des ressources de formation structurées

## 📁 Structure

```text
├── ISTQB/                  # Documentation centrale ISTQB
│   ├── CTFL/              # Foundation Level
│   ├── CTFL-AT/           # Foundation Level - Agile Tester
│   ├── CTAL-TA/           # Advanced Level Test Analyst
│   ├── CTAL-TM/           # Advanced Level Test Management
│   ├── CTAL-TAE/          # Advanced Level Test Automation Engineering
│   ├── CTAL-ATT/          # Advanced Level Agile Technical Tester
│   ├── CT-AI/             # Specialist AI Testing
│   └── ISTQB.md           # Vue d'ensemble des certifications
├── Framework/             # Documentation des frameworks de test
│   ├── Playwright/        # Framework Playwright
│   ├── RobotFramework/    # Framework Robot Framework
│   ├── Selenium/          # Framework Selenium
│   ├── Katalon Studio/    # Plateforme Katalon Studio
│   ├── JMeter/            # Outil de test de performance
│   ├── SOAP UI/           # Outil de test d'API SOAP
│   └── LambdaTest/        # Plateforme de test cloud
├── Glossary/              # Glossaire dynamique
│   ├── glossaire.csv      # Base de données CSV (268+ termes)
│   ├── glossaire.json     # Format JSON structuré
│   ├── categories.json    # Catégories de termes
│   ├── sources.json       # Sources de référence
│   ├── glossaire-viewer/  # Interface web interactive
│   └── glossaire-viewer.html # Interface web principale
├── Template/              # Modèles de documents
├── Notes/                 # Ressources d'apprentissage
├── Documents/             # Documentation générale
└── TODO.md                # Suivi des formations
```

## 🚀 Utilisation

1. **Documentation** : Consulter `ISTQB/ISTQB.md` pour vue d'ensemble des certifications
2. **Explorer** les dossiers spécifiques selon vos objectifs  
3. **Templates** : Utiliser les modèles pour créer vos propres documents
4. **Glossaire** : Interface web avec recherche et filtres

   ```bash
   cd Glossary/
   python -m http.server 8000
   # Ouvrir: http://localhost:8000/glossaire-viewer.html
   ```

5. **Suivi** : Progression via le fichier TODO

## 📚 Ressources

### ISTQB

- [Site officiel ISTQB](https://www.istqb.org/)
- [Glossaire ISTQB](https://glossary.istqb.org/)
- [Organismes de certification français](https://cftl.fr/)

### Frameworks de test

- [Playwright](https://playwright.dev/) - Framework de test end-to-end moderne
- [Robot Framework](https://robotframework.org/) - Framework d'automatisation générique
- [Selenium](https://selenium.dev/) - Framework d'automatisation web
- [Katalon Studio](https://katalon.com/) - Plateforme de test automatisé
- [JMeter](https://jmeter.apache.org/) - Outil de test de performance
- [SOAP UI](https://www.soapui.org/) - Outil de test d'API SOAP
- [LambdaTest](https://www.lambdatest.com/) - Plateforme de test cloud

## 🤝 Contribution

- **Fork** le repository et proposer des Pull Requests
- **Éditer** directement `Glossary/glossaire.csv` pour modifier le glossaire (instructions intégrées)
- **Suggérer** de nouveaux termes via Issues GitHub

## 📝 Licence

Contenu éducatif à des fins d'apprentissage. Les références ISTQB appartiennent à leurs propriétaires respectifs.
Code source du glossaire dynamique sous licence MIT.