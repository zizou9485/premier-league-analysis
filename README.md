# Premier League Analysis — Saison 2021-2022

Analyse exploratoire des résultats de la Premier League sur la saison 2021-2022, avec un modèle de prédiction entraîné sur 10 ans de données (2013-2023).

## Contexte

Ce projet est né d'une question simple : est-ce qu'on peut vraiment prédire le résultat d'un match de foot à partir des données historiques ? Pour y répondre, j'ai d'abord fait une analyse descriptive de la saison 2021-2022, puis j'ai entraîné un modèle Random Forest sur 3 800 matchs pour tester la chose.

## Ce que j'ai analysé

- La répartition domicile / extérieur / nul sur toute la saison
- Le classement offensif et défensif de chaque équipe
- La corrélation entre solidité défensive et place au classement
- Les points gagnés à domicile vs à l'extérieur par équipe

## Résultats principaux

L'avantage du terrain est réel : 42,9% de victoires à domicile contre 33,9% à l'extérieur sur la saison. Man City et Liverpool se distinguent sur les deux plans — meilleure attaque et meilleure défense en même temps, ce qui explique leur domination au classement. Chelsea est troisième mais avec un écart significatif.

Sur la prédiction, le modèle atteint 45% de précision. C'est mieux que le hasard (33% sur 3 issues possibles), mais ça reste limité — les features utilisées sont uniquement les identités des équipes, sans forme récente ni contexte.

## Fichiers

```
## Fichiers

├── analysis.ipynb                  # Analyse exploratoire de la saison 2021-2022
├── prediction.ipynb                # Modèle de prédiction (Random Forest, 10 ans de données)
├── E0.csv                          # Données brutes saison 2021-2022 (source : football-data.co.uk)
├── PL_10_ans.csv                   # Données agrégées 2013-2023
├── classement_final_complet.csv    # Bilan attaque/défense par équipe
├── bilan_attaque_defense.png       # Graphique attaque vs défense (toutes les équipes)
├── top_10_performances.png         # Graphique top 10 attaque vs défense
├── Rapport_Analyse_PremierLeague.pdf
├── Storytelling.txt                # Synthèse narrative des résultats
├── README.md
├── requirements.txt
└── .gitignore
```

## Installation

```bash
git clone https://github.com/zizou9485/premier-league-analysis.git
cd premier-league-analysis
pip install -r requirements.txt
jupyter notebook analysis.ipynb
```

## Dépendances

```
pandas
matplotlib
scikit-learn
jupyter
```

## Source des données

[football-data.co.uk](https://www.football-data.co.uk/englandm.php) — données libres d'accès, mises à jour chaque saison.

## Pistes d'amélioration

Le modèle de prédiction est volontairement simple pour un premier jet. Les axes naturels pour aller plus loin : intégrer la forme récente des équipes (5 derniers matchs), les stats de possession/tirs, ou passer à un gradient boosting.