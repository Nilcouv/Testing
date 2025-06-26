# Robot Framework - Notes

## Vue d'ensemble
- Framework de test d'acceptation et d'automatisation RPA
- Syntaxe keyword-driven lisible
- Extensible via des librairies Python et Java

## Points clés à retenir

### Installation
```bash
pip install robotframework
pip install robotframework-seleniumlibrary
```

### Structure de base
```robot
*** Settings ***
Library    SeleniumLibrary

*** Test Cases ***
Mon Premier Test
    Open Browser    https://example.com    chrome
    Close Browser
```

### Concepts importants
- Keywords : Mots-clés réutilisables
- Variables : Stockage de données
- Libraries : Extensions fonctionnelles

## Notes personnelles

<!-- Ajouter vos notes et observations ici -->

---
*Dernière mise à jour : [Date]* 