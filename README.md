# DSA210 Term Project 
**Alp Erdal Çetinalp — 35795**

## Does Transfer Spending Buy Success in La Liga?

This project looks at whether clubs that spend more in the transfer market actually finish higher in La Liga. The idea came from noticing that some clubs consistently outperform their budgets while others underperform despite heavy investment.

## Data
- Transfer records from [d2ski/football-transfers-data](https://github.com/d2ski/football-transfers-data) — covers La Liga clubs from 2009 to 2021 (fees, market values, transfer direction)
- Team performance stats (xG, xGA, possession, points) from [FBref.com](https://fbref.com/en/comps/12/history/La-Liga-Seasons), scraped using Python

The datasets are merged by club and season, giving around 200 observations. Target variable is final points total.

## Hypothesis
H₀: There is no correlation between net transfer spend and final points (ρ = 0)

H₁: Clubs that spend more finish with significantly more points (ρ ≠ 0)

## Plan
- EDA: spending patterns, scatter plots, correlation matrix, outliers
- Hypothesis testing: Spearman correlation, Mann-Whitney U test
- ML: Random Forest and Ridge Regression to predict points, with feature importance
