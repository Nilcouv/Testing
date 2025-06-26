# Robot Framework - Flashcards

## Qu'est-ce que Robot Framework ?
Framework de test d'acceptation et d'automatisation RPA utilisant une syntaxe keyword-driven lisible par les non-programmeurs.

## Comment installer Robot Framework ?
```bash
pip install robotframework
pip install robotframework-seleniumlibrary
```

## Quelles sont les 4 sections principales d'un fichier Robot Framework ?
- `*** Settings ***` : Configuration et imports
- `*** Variables ***` : Définition des variables
- `*** Test Cases ***` : Cas de test
- `*** Keywords ***` : Mots-clés personnalisés

## Comment définir une variable dans Robot Framework ?
```robot
*** Variables ***
${URL}    https://example.com
${BROWSER}    chrome
```

## Comment créer un keyword personnalisé ?
```robot
*** Keywords ***
Mon Keyword Personnalisé
    [Arguments]    ${argument}
    Log    ${argument}
```

## Comment exécuter des tests Robot Framework ?
```bash
robot tests/
robot --variable BROWSER:firefox tests/
```

## Quelle est la syntaxe pour ouvrir un navigateur ?
```robot
Open Browser    ${URL}    ${BROWSER}
```

## Comment générer des rapports avec Robot Framework ?
Les rapports sont générés automatiquement :
- `report.html` : Rapport détaillé
- `log.html` : Log d'exécution
- `output.xml` : Données XML

## Comment utiliser des conditions dans Robot Framework ?
```robot
Run Keyword If    ${condition}    Log    Condition vraie
```

## Quelle est la différence entre Library et Resource ?
- `Library` : Import de librairies Python/Java
- `Resource` : Import de fichiers .robot contenant des keywords

---
*Compatible avec l'extension "Anki for VSCode"* 