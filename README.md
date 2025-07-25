# Oman Rentals Project

This repository encompasses the end-to-end pipeline for scraping, cleaning, feature engineering, modeling, and deploying a rental listings analysis app for Oman.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Requirements](#requirements)
3. [Setup Instructions](#setup-instructions)
4. [Data Scraping](#data-scraping)
5. [Data Cleaning & Integration](#data-cleaning--integration)
6. [Feature Engineering](#feature-engineering)
7. [Predictive Modeling](#predictive-modeling)
8. [Visualization](#visualization)
---

## Project Overview

`Oman Rentals` gathers rental listings from Dubizzle and Mawa, cleans and merges the datasets, engineers predictive features, trains baseline regression models to estimate rental prices, visualizes insights

---


## Requirements

- Python 3.8+  
- Jupyter Notebook or JupyterLab  
- Dependencies (install via pip):  
  ```bash
  pip install -r requirements.txt
  ```
  **requirements.txt** includes:
  ```text
  pandas
  numpy
  requests
  beautifulsoup4
  scikit-learn
  matplotlib
  nbformat
  ```

---

## Setup Instructions

1. Clone the repository:  
   ```bash
   git clone https://github.com/Duaa3/Real-Estate-Data-Collection-and-Cleaning-Project.git
   cd oman-rentals
   ```
2. Install dependencies (see [Requirements](#requirements)).  
3. Launch Jupyter:  
   ```bash
   jupyter lab
   ```

---

## Data Scraping

- **Notebook:** `apps/DubizzleScraping.ipynb`,`apps/Mawa.ipynb` 
- **Description:** Step-by-step scraping of Dubizzle rental listings using `requests` + `BeautifulSoup`.  
- **Output CSVs:** `data/dubizzle_properties_for_rent.csv`, `data/mawa_rent_listings.csv`.

---

## Data Cleaning & Integration

- **Notebook:** `notebooks/data_cleaning.ipynb`  
- **Steps:**
  1. Load raw CSVs.  
  2. Standardize column names.  
  3. Parse and clean `price`, `area`.  
  4. Coerce numeric fields.  
  5. Drop duplicates.  
  6. Merge and dedupe into `data/cleaned_combined_listings.csv`.

---

## Feature Engineering

- **Notebook:** `notebooks/feature_engineering.ipynb`  
- **Derived Features:**  
  - `price_per_sqm`  
  - `total_rooms` (bedrooms + bathrooms)  
  - `district` (parsed from `location`)  
  - `district_encoded` (label encoding)  
- **Scaling:** MinMaxScaler & StandardScaler applied to key numeric columns.  
- **Output:** `data/engineered_listings.csv`

---

## Predictive Modeling

- **Notebook:** `notebooks/predictive_modeling.ipynb`  
- **Objective:** Predict rental **price**.  
- **Features:** `area`, `total_rooms`, `district_encoded`.  
- **Models:** Linear Regression, Decision Tree, Random Forest.  
- **Metrics:** RMSE, R².  
- **Insights:** Baseline R² ~0.2; next steps include richer features and hyperparameter tuning.

---

## Visualization

- **Notebooks:**
  - `notebooks/enhanced_visualizations.ipynb`  
  - `notebooks/final_data_cleaning.ipynb`  
- **Charts:** Histograms, boxplots, scatter plots, bar charts—explore `price`, `area`, `price_per_sqm`, and distributions by bedrooms/district.



