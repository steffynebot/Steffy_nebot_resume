---
title: Nettoyer et exporter ses données API avec Python
summary: Apprenez à importer, nettoyer et exporter vos données à partir d'une API avec Python en quelques étapes.
date: 2025-04-22
type: docs
tags:
  - Python
  - API
  - Pandas
  - Nettoyage de données
image:
  caption: 'Nettoyez et structurez vos données comme un pro avec Jupyter et Python'
---

Vous travaillez avec des données issues d’une API ? Vous souhaitez apprendre à les transformer et les exporter dans un format exploitable ? Ce tutoriel vous guide pas à pas à l’aide d’un notebook Python.

## 📡 Connexion à une API

Tout commence par une requête HTTP pour récupérer les données. Voici un exemple simple avec l’API JSONPlaceholder :

```python
import requests

url = "https://jsonplaceholder.typicode.com/posts"
response = requests.get(url)
data = response.json()  # On transforme la réponse en liste de dictionnaires

📊 Chargement dans un DataFrame
Utilisons Pandas pour charger ces données dans une structure tabulaire :

import pandas as pd

df = pd.DataFrame(data)
df.head()

 🧹 Nettoyage des données
Quelques étapes classiques de nettoyage :

# Renommer les colonnes pour plus de clarté
df.rename(columns={{'userId': 'user_id', 'id': 'post_id'}}, inplace=True)

# Vérifier les valeurs manquantes
print(df.isnull().sum())

# Supprimer les doublons si nécessaire
df.drop_duplicates(inplace=True)

# Exemple : supprimer les lignes où le titre est vide
df = df[df['title'].str.strip() != '']
