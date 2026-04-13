# DSA210 Term Project — Alp Erdal Çetinalp (35795)
## Relation Between Transfer Spending and League Success in La Liga

## Project Overview
This project investigates whether transfer market spending is a statistically significant predictor of sporting success in La Liga. Clubs across La Liga operate with very different financial resources, and it is not always clear whether the teams that spend the most end up finishing at the top, or whether on-pitch performance matters more than transfer investment.

## Datasets

**Primary Dataset — Transfer Records**
- Source: [d2ski/football-transfers-data](https://github.com/d2ski/football-transfers-data)
- Contains Transfermarkt-scraped transfer records for La Liga clubs from 2009 to 2021
- Key variables: transfer fees (EUR), player market values, transfer direction (in/out), loan vs. permanent

**Enrichment Dataset — Team Performance Statistics**
- Source: [FBref.com — La Liga Seasons](https://fbref.com/en/comps/12/history/La-Liga-Seasons)
- Contains per-season, per-club statistics including xG, xGA, possession %, and final points total
- Accessed via `pd.read_html()` in Python

The two datasets are merged by club name and season. Observations with missing or inconsistent data are removed before analysis. The final dataset is expected to contain approximately 200 club-season observations.

**Target variable:** Final points total per club per season

## Hypothesis

**H₀:** There is no statistically significant correlation between a club's net transfer spend and its final points total in La Liga (ρ = 0).

**H₁:** Clubs with higher net transfer spend achieve significantly more points (ρ ≠ 0).

Net transfer spend is defined as:

Net Spend = Σ Fees Paid − Σ Fees Received

## Analysis Plan

### Stage 1 — Exploratory Data Analysis (EDA)
- Distribution of net transfer spend across clubs and seasons
- Scatter plots of net spend vs. final points
- Correlation matrix of all numerical features
- Trend analysis of spending and performance over time
- Identification of outliers (e.g. clubs that overperformed or underperformed relative to spend)

### Stage 2 — Hypothesis Testing
- **Spearman rank correlation test** between net transfer spend and final points total
- **Mann-Whitney U test** comparing points distributions of top vs. bottom spending halves of clubs

### Stage 3 — Machine Learning
- **Random Forest Regressor** to predict final points from spending and performance features
- **Ridge Regression** as a baseline model
- Feature importance analysis to determine whether financial or on-pitch variables are stronger predictors

## Repository Structure
