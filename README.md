# Analyse et Sélection des Top-K Produits

## Description
Ce notebook Jupyter effectue une analyse approfondie d'un ensemble de données de produits e-commerce extraits via web scraping. L'objectif principal est d'identifier les produits les plus attractifs en fonction de critères tels que le prix, la note moyenne, la disponibilité et les ventes estimées. Le notebook utilise des techniques de prétraitement des données, de normalisation, de scoring composite, ainsi que des analyses avancées comme l'ACP (Analyse en Composantes Principales), le clustering K-Means et un modèle prédictif Random Forest.

## Fonctionnalités
1. **Chargement et Exploration des Données** : Importation des données à partir d'un fichier CSV (`produits_scrapy.csv`) et affichage des informations générales (dimensions, types de colonnes, aperçu des données, valeurs manquantes).
2. **Nettoyage des Données** :
   - Remplacement des valeurs manquantes numériques par la moyenne.
   - Remplacement des valeurs manquantes textuelles par des valeurs par défaut.
   - Suppression des doublons.
3. **Préparation des Données** :
   - Création d'une variable `ventes_estimees` basée sur la note moyenne et la disponibilité (simulation via distribution de Poisson).
   - Transformation de la disponibilité en score numérique (`dispo_score`).
4. **Normalisation** : Normalisation des critères numériques (prix, note moyenne, ventes estimées, disponibilité) à l'aide de `MinMaxScaler`. Inversion du prix pour favoriser les prix bas.
5. **Scoring Composite** : Calcul d'un score global pour chaque produit basé sur une combinaison pondérée des critères normalisés (note moyenne, prix inversé, ventes estimées, disponibilité).
6. **Sélection des Top-K Produits** : Identification des 5 produits les plus attractifs selon le score global.
7. **Visualisations** :
   - Distribution des scores globaux avec seuil pour les Top-5.
   - Nuage de points Prix vs Note avec mise en évidence des Top-5.
   - Classement des vendeurs par score moyen.
   - Score moyen par catégorie de produits.
8. **Analyse par Vendeur** : Statistiques agrégées par vendeur (score moyen, nombre de produits, meilleur score, prix moyen, note moyenne).
9. **Analyses Avancées** :
   - **ACP** : Réduction de dimensionnalité pour visualiser les produits dans un espace à 2 dimensions.
   - **Clustering K-Means** : Regroupement des produits en 5 clusters et analyse des caractéristiques des clusters.
   - **Random Forest** : Modèle prédictif pour estimer le score global et évaluation de l'importance des caractéristiques.
10. **Résultats** : Génération d'un tableau récapitulatif des Top-5 produits et sauvegarde dans un fichier CSV (`top_produits_attractifs.csv`).

## Prérequis
Pour exécuter ce notebook, les dépendances suivantes doivent être installées :
```bash
pip install pandas numpy matplotlib seaborn scikit-learn plotly
