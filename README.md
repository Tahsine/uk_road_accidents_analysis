# 🚗 UK Road Accidents: Geospatial Risk Prediction Model

## 📋 Présentation du Projet

Ce projet développe un pipeline complet de Machine Learning pour évaluer le risque d'accidents de la route au Royaume-Uni. En s'appuyant sur 45 ans de données historiques (1979-2024), le modèle prédit la gravité des accidents en fonction de facteurs géospatiaux, temporels et environnementaux.

L'objectif principal est de fournir un outil d'aide à la décision pour le calcul des primes d'assurance et l'identification des zones à haut risque.

### 🎯 Objectifs Clés

* **Prédire la gravité des accidents** : Classification multi-classe (Léger, Grave, Fatal).
* **Analyse Géospatiale** : Création d'une grille de score de risque pour visualisation cartographique.
* **Engineering de Données** : Transformation de codes numériques bruts en labels compréhensibles et création de plus de 50 caractéristiques (features).
* **Déploiement** : Exportation des modèles et des données traitées pour une intégration facile (ex: React).

## 📊 Source des Données

Les données utilisées proviennent du **UK Department for Transport (DfT)**. Il s'agit du jeu de données ouvert "STATS19", référence officielle pour la sécurité routière au Royaume-Uni.

* **Lien de téléchargement** : [Road Safety Open Dataset (data.gov.uk)](https://www.google.com/search?q=https://www.data.gov.uk/dataset/cb7ae6c0-06fd-4db2-a795-3919b6655021/road-safety-data)
* **Description** : Le dataset comprend trois tables liées : Collisions (Accidents), Casualties (Victimes) et Vehicles (Véhicules).

## 🛠️ Technologies Utilisées

Le projet est développé en Python avec les bibliothèques suivantes :

* **Analyse & Manipulation** : `pandas`, `numpy`
* **Visualisation** : `matplotlib`, `seaborn`, `plotly`
* **Machine Learning** : `scikit-learn`, `xgboost`, `lightgbm`
* **Persistance du modèle** : `joblib`, `json`

## 🚀 Installation et Utilisation

### 1. Cloner le dépôt

```bash
git clone https://github.com/votre-username/uk-road-accidents-risk.git
cd uk-road-accidents-risk

```

### 2. Installer les dépendances

```bash
# Recommander de créer un environnement virtuel selon son OS
# Pour eviter des conflits eventuels

pip install -r requirements.txt

```

### 3. Structure des fichiers

* `notebook.ipynb` : Le pipeline complet de l'analyse exploratoire à l'entraînement du modèle.
* `requirements.txt` : Liste des dépendances nécessaires.
* `data/` : Dossier à créer pour stocker les fichiers CSV du DfT (à télécharger via le lien ci-dessus).

## 🧠 Méthodologie

1. **Chargement optimisé** : Filtrage des données (2018-2024) et utilisation de types de données économes en mémoire pour gérer plus de 700 000 enregistrements.
2. **Nettoyage** : Gestion des valeurs manquantes, filtrage des coordonnées GPS hors UK et encodage des variables catégorielles.
3. **Jointures complexes** : Agrégation des données des victimes et des véhicules par collision.
4. **Entraînement** : Comparaison de plusieurs modèles (Random Forest, XGBoost, LightGBM) pour sélectionner le plus performant.

## 📈 Résultats et Livrables

Le pipeline génère plusieurs fichiers prêts pour la production :

* `best_accident_model.pkl` : Le modèle de classification final.
* `scaler.pkl` & `severity_map.pkl` : Préprocesseurs et dictionnaires de mapping.
* `accident_risk_grid.json` : Données de grille pour générer une Heatmap.
* `summary_statistics.json` : Statistiques clés du dataset.

## 👤 Auteur

**Tahsine Kajola SALAMI**

* Date de mise à jour : Janvier 2026

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

---

*Ce projet a été réalisé dans le cadre d'une étude sur l'évaluation des risques pour le secteur de l'assurance.*