# 📚 Glossaire Testing - Vue.js

## 🎯 Description

Application web de gestion de glossaire technique développée avec Vue.js 3. Permet de consulter, ajouter, modifier et supprimer des termes techniques avec leurs définitions en français et anglais.

## ✨ Fonctionnalités

### **Gestion des termes**
- ✅ Ajout de nouveaux termes avec définitions FR/EN
- ✅ Modification des termes existants
- ✅ Suppression de termes
- ✅ Recherche en temps réel
- ✅ Filtrage par catégorie et source
- ✅ Support des abréviations et acronymes

### **Interface utilisateur**
- ✅ Interface réactive avec Vue.js 3
- ✅ Recherche avec debouncing (300ms)
- ✅ Tri des colonnes (ascendant/descendant)
- ✅ Modal d'ajout/modification
- ✅ Notifications en temps réel
- ✅ Design responsive

### **Gestion des données**
- ✅ Chargement depuis `data/glossaire.json`
- ✅ Sauvegarde automatique en localStorage
- ✅ Import/export CSV
- ✅ Catégories et sources dynamiques
- ✅ Structure JSON optimisée

### **Personnalisation**
- ✅ Options d'affichage configurables
- ✅ Ordre des termes (FR→EN / EN→FR)
- ✅ Séparateurs personnalisables
- ✅ Colonnes visibles/ masquées
- ✅ Paramètres persistants

## 🚀 Installation et utilisation

### **Prérequis**
- Navigateur web moderne
- Serveur web local (pour le chargement des fichiers JSON)

### **Installation**
1. Cloner le repository
2. Ouvrir `viewer.html` dans un navigateur
3. Ou utiliser un serveur local :
   ```bash
   # Avec Python
   python -m http.server 8000
   
   # Avec Node.js
   npx serve .
   ```

### **Structure des fichiers**
```
glossaire-viewer/
├── viewer.html              # Application principale
├── data/
│   ├── glossaire.json       # Données du glossaire
│   ├── categories.json      # Catégories disponibles
│   └── sources.json         # Sources disponibles
├── TODO.md                  # Suivi du projet
└── README.md               # Ce fichier
```

## 🛠️ Technologies utilisées

- **Vue.js 3** : Framework JavaScript réactif
- **HTML5/CSS3** : Interface utilisateur
- **JavaScript ES6+** : Logique métier
- **localStorage** : Persistance des données
- **Fetch API** : Chargement des données JSON

## 📊 Données

### **Format des termes**
```json
{
  "id": "unique_id",
  "term_en": "English term",
  "term_fr": "Terme français",
  "definition_en": "English definition",
  "definition_fr": "Définition française",
  "source": "Source",
  "category": "Catégorie"
}
```

### **Support des abréviations**
Le glossaire supporte les abréviations et acronymes avec :
- **Recherche intelligente** : Trouve les termes par abréviation ou nom complet
- **Affichage contextuel** : Montre l'abréviation et sa signification
- **Filtrage automatique** : Identifie les termes contenant des abréviations

### **Sources de données**
- **ISTQB** : Termes de certification testing
- **General Testing** : Termes généraux
- **Agile Testing** : Méthodologies agiles
- **DevOps** : Pratiques DevOps
- **API Testing** : Tests d'API

## 🎨 Interface

### **Composants principaux**
- **Header** : Titre et statistiques
- **SearchFilters** : Recherche et filtres
- **GlossaryTable** : Tableau des termes
- **TermModal** : Formulaire d'ajout/modification
- **DisplaySettingsModal** : Options d'affichage

### **Fonctionnalités clés**
- **Recherche temps réel** : Filtrage automatique
- **Tri interactif** : Clic sur en-têtes de colonnes
- **Notifications** : Feedback utilisateur
- **Responsive** : Adaptation mobile/desktop
- **Recherche d'abréviations** : Support des acronymes

## 🔧 Configuration

### **Paramètres d'affichage**
- Ordre des termes (FR→EN / EN→FR)
- Séparateurs (/, |, -, :)
- Colonnes visibles (Terme, Définition, Catégorie, Source)

### **Persistance**
- Paramètres sauvegardés en localStorage
- Données synchronisées automatiquement
- Fallback vers localStorage si erreur de chargement

## 📝 Utilisation

### **Ajouter un terme**
1. Cliquer sur "➕ Ajouter"
2. Remplir le formulaire
3. Cliquer sur "Ajouter"

### **Modifier un terme**
1. Cliquer sur "✏️" dans la ligne du terme
2. Modifier les champs
3. Cliquer sur "Modifier"

### **Supprimer un terme**
1. Cliquer sur "🗑️" dans la ligne du terme
2. Confirmer la suppression

### **Rechercher**
- Saisir dans le champ de recherche
- Utiliser les filtres catégorie/source
- Cliquer sur "🗑️ Effacer" pour réinitialiser
- **Recherche d'abréviations** : Saisir l'acronyme ou le nom complet

### **Personnaliser l'affichage**
1. Cliquer sur "⚙️ Affichage"
2. Modifier les paramètres
3. Cliquer sur "💾 OK"

## 🐛 Résolution de problèmes

### **Page blanche**
- Vérifier que Vue.js CDN est accessible
- Ouvrir la console pour les erreurs JavaScript

### **Données non chargées**
- Vérifier que les fichiers JSON sont présents
- Utiliser un serveur web local

### **Fonctionnalités non disponibles**
- Vérifier la compatibilité du navigateur
- Recharger la page

## 📈 Évolutions futures

- [ ] Interface d'administration
- [ ] Gestion des utilisateurs
- [ ] API REST
- [ ] Base de données
- [ ] Export PDF
- [ ] Recherche avancée
- [ ] Tags et métadonnées

## 🤝 Contribution

1. Fork le projet
2. Créer une branche feature
3. Commiter les changements
4. Pousser vers la branche
5. Ouvrir une Pull Request

## 📄 Licence

Ce projet est sous licence MIT.

---

**Développé avec ❤️ pour la communauté testing**


