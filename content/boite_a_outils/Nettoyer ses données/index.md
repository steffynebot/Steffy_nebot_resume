---
title: Nettoyer et visualiser les données FAO avec Python
summary: Utilisez Pandas et Matplotlib pour explorer, nettoyer et visualiser des données issues de la FAO.
date: 2025-04-22
type: docs
tags:
  - Python
  - Pandas
  - Matplotlib
  - Nettoyage de données
  - Visualisation
image:
  caption: 'Exploration et nettoyage des données FAO avec Pandas et Matplotlib'
---

## 🌍 Objectif

Dans ce tutoriel, nous allons :

- Importer des données issues de la FAO (Organisation des Nations Unies pour l'alimentation et l'agriculture)
- Nettoyer les données avec Pandas
- Réaliser une visualisation simple avec Matplotlib et NumPy

## 📥 Chargement des données

Téléchargez les données depuis Kaggle ou utilisez une version locale :

```python
import pandas as pd

# Exemple de chargement depuis un fichier local
df = pd.read_csv("FAO.csv", encoding="latin1")
df.head()
```

## 🧹 Étapes de nettoyage avec Pandas

```python
# Renommer des colonnes
df.rename(columns={"Area": "Pays", "Item": "Produit", "Element": "Type_donnée"}, inplace=True)

# Vérifier les valeurs manquantes
print(df.isnull().sum())

# Supprimer les colonnes inutiles
df.drop(columns=["Domain Code", "Area Code", "Item Code", "Element Code"], inplace=True)

# Garder uniquement les données de production
df = df[df["Type_donnée"] == "Production"]

# Supprimer les lignes sans valeur
df = df[df["Value"].notnull()]
```

## 📊 Transformation avec Pandas

```python
# Agréger la production moyenne par pays
prod_pays = df.groupby("Pays")["Value"].mean().sort_values(ascending=False).head(10)
prod_pays
```

## 📈 Visualisation avec Matplotlib et NumPy

```python
import matplotlib.pyplot as plt
import numpy as np

# Préparation des données
pays = prod_pays.index
valeurs = prod_pays.values

# Création du graphique
plt.figure(figsize=(12, 6))
bars = plt.bar(pays, valeurs, color="skyblue")

# Ajouter des étiquettes
plt.xticks(rotation=45)
plt.title("Top 10 des pays producteurs (en moyenne)")
plt.ylabel("Production moyenne")
plt.xlabel("Pays")
plt.tight_layout()
plt.show()
```

## 🎯 Résultat

Ce graphique permet d'identifier les pays ayant les plus hauts niveaux moyens de production parmi les données FAO analysées.

## 📁 Export des données nettoyées

```python
df.to_csv("fao_donnees_nettoyees.csv", index=False)
```

## 🎥 Inspiration vidéo

{< youtube VqCkCDFLSsc >}

## 🧪 Astuce

{< spoiler text="👉 Cliquez pour une astuce NumPy" >}
Utilisez `np.where()` pour créer des colonnes conditionnelles dans un DataFrame Pandas !
{< /spoiler >}

## 📚 Ressources utiles

- [Pandas Documentation](https://pandas.pydata.org/)
- [Matplotlib Documentation](https://matplotlib.org/stable/index.html)
- [Dataset FAO sur Kaggle](https://www.kaggle.com/datasets/)

---

{< icon name="python" >} Laissez parler vos données avec Python 🐍 !
