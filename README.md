# Urban Extreme Rainfall Prediction — Cross-City ML Generalization

BSc Thesis | AI and Sustainable Technologies
Tomorrow University of Applied Sciences | 2026
Author: Jana Aly Mohamed Deghidy

---

## Overview
This repository contains all code, notebooks, and results for my BSc thesis:

**"Evaluating the Generalization of Machine Learning Models for Urban Extreme Rainfall Prediction"**

The study investigates whether supervised ML models trained on one city generalize 
to predict extreme rainfall in a different city. Four cities were evaluated — 
Singapore, Tokyo, London, and New York — across 102 experiments in three phases.

---

## Key Findings
- Within-city evaluation significantly overestimates cross-city performance (p = 0.0004)
- Climate regime similarity drives generalization more than urban structural similarity
- LCZ and building density features do not significantly improve cross-city transfer (p = 0.670)
- Rainfall memory features significantly improve cross-city performance (p = 0.021)
- Multi-city training provides modest improvement, particularly for forecasting models

---

## Repository Structure

UrbanRainfall-ML-Thesis/
│
│
├── Code/
│   ├── Notebooks/                # Within-city evaluation scripts
│   │   ├── Single city
│   │   ├── cross-city
│   │   ├── data exploration
│   │   ├── feature engineering
│   │   └── data cleaning
│  
│
├── Results/
│   ├── tables.txt               # All numerical results and statistical tests
│   ├── cross_city_results.csv   # Cross-city AUC results table
│   ├── week15_results.csv       # Multi-city results table
│   └── figures/                 # All generated plots (PNG)
│       ├── heatmap_A_Full_RF.png
│       ├── heatmap_B_Full_XGB.png
│       ├── heatmap_B_NoLags_XGB.png
│       ├── auc_drop_barchart.png
│       ├── lcz_urban_benefit_Q1.png
│       ├── rainfall_memory_benefit_Q2.png
│       ├── grouped_bar_all_models_pairs.png
│       ├── roc_curves_best_pairs.png
│       ├── density_vs_auc_drop_Q3.png
│       └── week15_*.png
│
└── README.md

---

## Models Used
| Model | Description |
|-------|-------------|
| A_Full_RF | Random Forest — full rainfall + weather features, no LCZ |
| B_Full_XGB | XGBoost — full features including LCZ and building density |
| B_NoLags_XGB | XGBoost — weather + LCZ only, no rainfall (forecasting scenario) |

---

## Cities
| City | Climate Type | Dataset Size |
|------|-------------|-------------|
| Singapore | Tropical monsoon | 657,120 rows |
| Tokyo | Typhoon-influenced | 4,408,180 rows |
| London | Temperate maritime | 651,644 rows |
| New York | Continental | 525,696 rows |

---

## Requirements

pip install pandas numpy scikit-learn xgboost scipy matplotlib seaborn joblib

---

## Data Sources
- **ERA5** — Copernicus Climate Change Service (weather data)
- **OpenStreetMap** — Building footprints and urban structure
- **WUDAPT** — Local Climate Zone classifications

---

## Citation
If you use this work, please cite:
Deghidy, J. A. M. (2026). Evaluating the Generalization of Machine Learning Models 
for Urban Extreme Rainfall Prediction. BSc Thesis, Tomorrow University of Applied Sciences.
