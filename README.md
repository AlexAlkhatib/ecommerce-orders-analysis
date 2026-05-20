# 🛒 **E-commerce Orders Data Analysis — Nettoyage, Fusion et Visualisation**

Ce projet analyse un ensemble de données e-commerce comprenant **les commandes**, **les paiements** et **les clients**.
L’objectif est d’extraire des insights utiles sur les comportements d’achat, les modes de paiement, les revenus mensuels et les tendances clients.

Réalisé dans un cadre **personnel d’apprentissage**, ce projet met en pratique des compétences essentielles en **Python**, **pandas**, **data cleaning**, **data merging** et **visualisation** avec *Matplotlib* et *Seaborn*.


## 🎯 Objectifs du projet

* Nettoyer et préparer trois datasets liés (orders, payments, customers)
* Gérer les valeurs manquantes et les doublons
* Explorer et filtrer les données pour répondre à des questions spécifiques
* Fusionner les datasets pour créer un modèle d’analyse complet
* Créer des visualisations : courbes temporelles, scatter plots, bar charts, box plots
* Dégager des insights sur les habitudes d’achat et les revenus


## 🧰 Stack technique

* **Python 3**
* **pandas** (nettoyage, transformation, fusion de données)
* **Matplotlib** (visualisations)
* **Seaborn** (visualisations avancées)
* **Excel / CSV** comme sources de données
* **OS module** pour gestion du répertoire courant


## 📊 Données utilisées

Le projet exploite **trois fichiers Excel** :

* `orders.xlsx` → infos sur les commandes (dates, statut, valeur…)
* `order_payment.xlsx` → méthodes de paiement et montants
* `customers.xlsx` → informations clients (localisation, ID, etc.)

Ces données sont fusionnées pour obtenir une table riche permettant une analyse complète du pipeline e-commerce.


## 🧹 Étapes d’analyse

### 1. **Chargement & inspection**

* `df.info()`, `df.describe()`, affichage des colonnes
* Identification des types et premières incohérences

### 2. **Nettoyage**

* Traitement des valeurs manquantes (`fillna`, `dropna`)
* Suppression des doublons
* Vérifications post-cleaning

### 3. **Filtrage ciblé**

* Commandes avec statut *invoiced*
* Paiements par carte bancaire > 1000
* Clients localisés dans un état particulier (ex : `SP`)

### 4. **Merging / Joining**

Fusion des datasets via `merge` sur :

* `order_id` (orders ↔ payments)
* `customer_id` (merged ↔ customers)

### 5. **Feature engineering**

* Extraction du mois, semaine et année :

  ```python
  joined_data['month_year'] = joined_data['order_purchase_timestamp'].dt.to_period('M')
  ```


## 📈 Visualisations produites

### 📌 Courbe des revenus mensuels

Évolution des `payment_value` par mois (tendance générale du chiffre d’affaires).

### 📌 Scatter plot

Comparaison :

* valeur des paiements
* nombre d’installments par client

Permet d’identifier des comportements d’achat.

### 📌 Bar chart empilé

Analyse des revenus par type de paiement **et** par mois.

### 📌 Box plots par type de paiement

Distribution statistique des valeurs payées en fonction du mode de paiement.

### 📌 Subplots (3-en-1)

Un graphique combinant :

* boxplot
* bar chart
* scatter plot

Le fichier final est exporté en image : `my_plot.png`.


## 📂 Structure du projet

```
ecommerce_orders_analysis/
 ├── orders.xlsx
 ├── order_payment.xlsx
 ├── customers.xlsx
 ├── ecommerce_analysis.py        # ton script principal
 ├── my_plot.png                  # figure générée
 └── README.md
```


## 🧠 Compétences démontrées

- ✔ Manipulation avancée de pandas (merge, groupby, filtering)
- ✔ Nettoyage de données réel (missing values, duplicates)
- ✔ Feature engineering (création de champs temporels)
- ✔ Visualisation professionnelle (courbes, bar charts empilés, subplot, scatter)
- ✔ Analyse des comportements d’achat
- ✔ Construction d’un dataset consolidé multi-sources
- ✔ Préparation des données pour BI / machine learning


## 🔧 Pistes d’amélioration

* Ajouter des visualisations avancées (heatmaps, distributions)
* Développer un dashboard Power BI / Tableau alimenté par les outputs
* Intégrer des modèles prédictifs (prévision du CA mensuel)
* Automatiser le pipeline (Python CLI ou notebook propre)
* Ajouter une analyse géographique des clients


## 👤 À propos

Projet réalisé par **Alex Alkhatib**, passionné par la data, l’analyse et la visualisation.


## 📄 Licence
MIT License
Copyright (c) 2025 Alex Alkhatib
