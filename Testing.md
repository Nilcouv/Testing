---
tags:
  - Wiki/Professional/TestAnalyst
---
#### Test Type

|Name|Test Manuel|Test automatique|
|---|---|---|
|[[Test exploratif]]|✔ Capable de déduire le résultat attendu|❌ ==incapable de déduire le résultat attendu==|
|[[Test aléatoire]]|✔ Capable de déduire le résultat attendu|❌ Incapable d'introduire de réponses aléatoires|
|[[Test d'interface]]|✔ Capable de déduire le résultat attendu|✔ ==Mais Nécessite de changer le script à chaque changement==|
|[[Test de fiabilité]]|❌ ==l'humain n'est pas suffisamment fiable==|✔ Haut niveau de précision|
|[[Test de ressources]]|✔ ==Mais nécessite un nombre important de testeurs==|✔ Capable de produire de multiple instance|
|[[Test de performences]]|==❌ Incapable d'évaluer les performences==|✔ Capable d'évaluer la charge|

  
  

#### Testing tools

|Name|Tags|
|---|---|
|[[SOAP UI]]||
|[[Selenium]]||
|[[Jira]]||
|[[Jmeter]]||
|[[Confluence]]||
|[[LambdaTesting]]||

  
  

  

Testing manuel

- Ne requière aucune connaissance en programmation
- Flexible et rapide à mettre en place
- Coûteux et lent à réaliser
- Est adapté pour les philisophies de test AdHoc ou exploratoire et pour les applications subissant des changements importants et fréquents
- Est inadatpé pour les applications volumineuses nécessitant de réaliser ou répéter de nombreux tests

## Testing automatique

- En résumé
    - Requière des connaissances en programmation
    - Rigide et long à mettre en place
    - économe et rapide à réaliser
    - s'intègre bien à cycle de DevOps
    - Est adapté aux tests répétitif présentant des résultats attendus et quantitatif, telle que des tests fonctionnels. Il est donc adapté pour des applications volumineuses nécessitant de réaliser ou répéter de nombreux tests.
    - Outils : Selenium
- Type de tests
    
    - Test unitaire (Unit testing)  
          
        _Test un morceau de code en particulier, telle qu'un composant, une classe, une fonction, etc. Ce qui peut impliquer de vérifier l'aspect du composant, les données, etc._
    - Test d'intégration (intergration testing)  
          
        _Test plusieurs unités ensembles pour s'assurer quelles fonctionnent ensemble,_
    - Test de bout en bout (End-to-End testing)  
          
        _Test un scénario d'utilisation, simulant le comportement de l'utilisateur, pour s'assurer que l'application marche globallement. Il peut donc tester le processus de d'inscription et de validation du compte, etc. Ce type de test est plus difficile à maintenir car cassé facilement en cas de changements_
    
      
    
    Afin de garder un process de testing facilement maintenable, il est recommandé de répartir ses scripts entre 70% d'unitaire, 20% d'intégration et 10% de bout-en-bout
    

## Software

- Selenium
- LambdaTesting - permet de tester des 100ènes de configuration de support (version de chrome, d'android, de windows, etc.)

## Lexique

  

![[Untitled 5 1.png|Untitled 5 1.png]]

## Sources:

[https://www.youtube.com/watch?v=rhE45ihB26E](https://www.youtube.com/watch?v=rhE45ihB26E)

test