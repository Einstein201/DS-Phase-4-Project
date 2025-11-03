# DS Phase 4 Project – NLP Sentiment Analysis

Ce projet a pour objectif de construire un modèle NLP capable d’analyser le `sentiment des Tweets` liés aux produits Apple et Google.

## Contenu du dépôt
- `data_exploration.ipynb` ---> Notebook principal (préparation, modélisation, évaluation)
- `tweet_product_company.csv` --->Jeu de données utilisé
- `model_linearSVC.joblib`  ---> Modèle entraîné sauvegardé
- `reports/figures/`  ---> Visualisations exportées

## Auteur
**Brunine Einstein Pointe-Jour**

## Institution
Projet réalisé dans le cadre du Bootcamp Akademi – Data Science, Phase 4.


# Problématique métier
Les entreprises technologiques comme Apple et Google doivent surveiller en continu les retours de leurs utilisateurs 
afin de comprendre la perception de leurs produits sur les réseaux sociaux.
L’analyse des Tweets permet d’identifier les tendances d’opinion, de repérer les sources d’insatisfaction et d’orienter les décisions marketing et produits.

# Solution proposée

Ce projet met en place un modèle de traitement automatique du langage naturel (NLP) capable de classifier les Tweets concernant les produits Apple 
et Google selon trois catégories de sentiment :

- Positif : satisfaction, éloges
- Négatif : plaintes, critiques ou mécontentement
- Neutre : informations ou opinions sans émotion claire

L’objectif est d’automatiser l’analyse du ressenti client pour aider les entreprises à suivre l’évolution de leur image en temps réel.

## Aperçu du jeu de données

- Source : CrowdFlower / Data.world
- Nombre total de Tweets : 9 093
- Colonnes principales :
   - tweet_text → texte du Tweet
   - emotion_in_tweet_is_directed_at → produit ou marque mentionné
   - is_there_an_emotion_directed_at_a_brand_or_product → sentiment associé

- Répartition des classes :
  -Neutre : ~60 %
  -Positif : ~30 %
  -Négatif : ~10 %

Le jeu de données est déséquilibré, ce qui a nécessité un échantillonnage stratifié et un ajustement des pondérations lors de l’entraînement.

## Statistiques clés
## Mesure	                                Valeur
- Modèle choisi                         	LinearSVC (class_weight='balanced', optimisé par GridSearchCV)
- Précision globale (Accuracy)	           ≈ 68 %
- Rappel – Neutre                          0.77
- Rappel – Positif                         0.56
- Rappel – Négatif	                       0.49
- Vectorisation	                           TF-IDF (bigrams, min_df = 3)
- Mots les plus positifs	                  cool, awesome, great, love, wow
- Mots les plus négatifs                    fail, hate, sucks, headache, stuck


## Perspectives et améliorations futures
- Intégrer un modèle de langage plus avancé (BERT, RoBERTa) pour mieux comprendre le contexte.
- Enrichir le dataset avec de nouveaux Tweets récents.
- Créer une interface web simple permettant à un utilisateur de soumettre un Tweet et d’obtenir le sentiment prédictif.

## Conclusion
Le modèle LinearSVC fournit une preuve de concept solide pour la classification automatique du sentiment sur Twitter.
Il distingue efficacement les Tweets neutres et positifs, mais les messages négatifs restent plus difficiles à identifier, 
probablement en raison de leur faible proportion dans les données.









